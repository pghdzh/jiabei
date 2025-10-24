<template>
  <main class="home">
    <canvas ref="canvasEl" class="rose-canvas" aria-hidden="true"></canvas>

    <!-- 背景轮播（两组用于桌面/移动不同裁切） -->
    <div class="carousel carousel1" aria-hidden="true">
      <img
        v-for="(src, idx) in randomFive"
        :key="idx"
        :src="src"
        class="carousel-image"
        :class="{ active: idx === currentIndex }"
      />
    </div>
    <div class="carousel carousel2" aria-hidden="true">
      <img
        v-for="(src, idx) in randomFive2"
        :key="idx"
        :src="src"
        class="carousel-image"
        :class="{ active: idx === currentIndex }"
      />
    </div>

    <section class="center" role="main">
      <h1 class="title">写作安吉尔读作天使 · 嘉贝莉娜</h1>

      <div class="subtitle" aria-live="polite">
        <span class="typed">{{ typed }}</span
        ><span class="cursor" aria-hidden="true">▍</span>
      </div>
    </section>

    <footer
      class="shore-footer-simple"
      role="contentinfo"
      aria-label="页面页脚"
    >
      <div class="inner container">
        <div class="center">
          <div class="slogan">穿越炼狱，终抵安宁。</div>
          <div class="meta">
            © <span>{{ year }}</span> 嘉贝莉娜电子设定集 · 制作：霜落天亦
          </div>
        </div>
      </div>
    </footer>
  </main>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";
import violet from "@/assets/violet.png"; // 若希望更贴合风格，可替换为“贝壳/羽毛/萤光点”贴图
const year = new Date().getFullYear();
const canvasEl = ref<HTMLCanvasElement | null>(null);
let ctx: CanvasRenderingContext2D;
let animationId = 0;
let lastTime = 0;
let elapsed = 0;

interface Rose {
  baseX: number;
  y: number;
  size: number;
  speed: number;
  swayAmp: number;
  swayFreq: number;
  phase: number;
  angle: number;
  angularSpeed: number;
}

const roses: Rose[] = [];
const ROSE_COUNT_DESKTOP = 18;
const ROSE_COUNT_MOBILE = 6;
const ROSE_IMG = new Image();
ROSE_IMG.src = violet;

function initRoses(count: number) {
  roses.length = 0;
  const canvas = canvasEl.value!;
  const w = canvas.width / (window.devicePixelRatio || 1);
  const h = canvas.height / (window.devicePixelRatio || 1);

  for (let i = 0; i < count; i++) {
    const baseX = Math.random() * w;
    roses.push({
      baseX,
      y: Math.random() * -h,
      size: 18 + Math.random() * 38, // 稍微精简尺寸
      speed: 12 + Math.random() * 36, // 速度更缓
      swayAmp: 12 + Math.random() * 26,
      swayFreq: 0.15 + Math.random() * 0.7,
      phase: Math.random() * Math.PI * 2,
      angle: Math.random() * Math.PI * 2,
      angularSpeed: (Math.random() - 0.5) * 1.2,
    });
  }
  elapsed = 0;
}

let resizeTimeout: number;
function resizeCanvas() {
  window.clearTimeout(resizeTimeout);
  resizeTimeout = window.setTimeout(() => {
    cancelAnimationFrame(animationId);
    const canvas = canvasEl.value!;
    const parent = canvas.parentElement!;
    const dpr = window.devicePixelRatio || 1;
    const w = parent.clientWidth;
    const h = Math.max(parent.clientHeight, 420); // 给个最小高度，避免太窄时粒子不明显

    canvas.style.width = w + "px";
    canvas.style.height = h + "px";
    canvas.width = w * dpr;
    canvas.height = h * dpr;

    ctx.setTransform(1, 0, 0, 1, 0, 0);
    ctx.scale(dpr, dpr);

    const isMobile = w < 768;
    initRoses(isMobile ? ROSE_COUNT_MOBILE : ROSE_COUNT_DESKTOP);
    lastTime = 0;
    animationId = requestAnimationFrame(tickCanvas);
  }, 160);
}

function tickCanvas(now: number) {
  if (!lastTime) lastTime = now;
  const dt = (now - lastTime) / 1000;
  lastTime = now;
  elapsed += dt;

  const canvas = canvasEl.value!;
  const w = canvas.clientWidth;
  const h = canvas.clientHeight;

  ctx.clearRect(0, 0, w, h);

  // 轻微整体雾层，增强深度（透明度低，避免影响可读性）
  ctx.fillStyle = "rgba(2,8,14,0.08)";
  ctx.fillRect(0, 0, w, h);

  roses.forEach((r) => {
    r.y += r.speed * dt;
    const sway = r.swayAmp * Math.sin(r.phase + elapsed * r.swayFreq);
    const x = r.baseX + sway;
    r.angle += r.angularSpeed * dt;

    if (r.y > h + r.size) {
      r.y = -r.size * 0.6;
      r.baseX = Math.random() * w;
      r.phase = Math.random() * Math.PI * 2;
    }

    if (x > w + r.size || x < -r.size) return;

    // 计算透明度：越远看上去越淡
    const alpha = Math.max(0, Math.min(1, 1 - (r.y / h) * 0.6));

    ctx.save();
    ctx.globalAlpha = alpha;
    ctx.translate(x, r.y);
    ctx.rotate(r.angle);

    if (ROSE_IMG && ROSE_IMG.complete && ROSE_IMG.naturalWidth > 0) {
      // 使用图片绘制，但加上一层冷色调叠加（globalCompositeOperation 简单处理）
      ctx.drawImage(ROSE_IMG, -r.size / 2, -r.size / 2, r.size, r.size);

      // 轻微冷光叠加，提升风格一致性
      ctx.globalCompositeOperation = "lighter";
      const grad = ctx.createRadialGradient(0, 0, 0, 0, 0, r.size);
      grad.addColorStop(0, `rgba(79,233,223,${0.08 * alpha})`);
      grad.addColorStop(1, "rgba(0,0,0,0)");
      ctx.fillStyle = grad;
      ctx.fillRect(-r.size / 2, -r.size / 2, r.size, r.size);
      ctx.globalCompositeOperation = "source-over";
    }

    ctx.restore();
  });

  animationId = requestAnimationFrame(tickCanvas);
}

// ========== 打字机文案 ==========
// 适合长离风格的副标题（偏长句，已为打字器准备）
const lines = [
  "永火燃尽宿命，猎魔人于此重生",
  "炼狱回响，缔结不朽契约",
  "影羽落处，即是征途起点",
  "穿越冥途的猎魔者，在此刻停驻",
  "以永火为誓，以猎魔为契",
  "炼狱的炽热，照亮前行之路",
  "漆黑羽翼下，藏着真实的温度",
  "猎魔行纪，自此翻开新章",
  "永火不熄，信念长存",
  "在炼狱的尽头，寻找答案",
  "影羽纷飞，奏响命运序曲",
  "冥途的旅人，终抵此间净土",
  "以猎魔人之名，书写永恒",
  "永火灼烧过往，猎魔指向未来",
  "炼狱的低语，是前行的指引",
];

const typed = ref("");
let lineIndex = 0;
let charIndex = 0;
let deleting = false;
let timer: number | null = null;

const TYPING = 120;
const DELETING = 40;
const PAUSE = 1200;

function tick() {
  const cur = lines[lineIndex];
  if (!deleting) {
    typed.value = cur.slice(0, charIndex + 1);
    charIndex++;
    if (charIndex >= cur.length) {
      timer = window.setTimeout(() => {
        deleting = true;
        tick();
      }, PAUSE);
      return;
    }
    timer = window.setTimeout(tick, TYPING);
  } else {
    typed.value = cur.slice(0, charIndex - 1);
    charIndex--;
    if (charIndex <= 0) {
      deleting = false;
      lineIndex = (lineIndex + 1) % lines.length;
      timer = window.setTimeout(tick, 360);
      return;
    }
    timer = window.setTimeout(tick, DELETING);
  }
}

// ========== 背景图片导入与轮播 ==========
const modules = import.meta.glob("@/assets/images1/*.{jpg,png,jpeg,webp}", {
  eager: true,
});
const allSrcs: string[] = Object.values(modules).map((mod: any) => mod.default);

const modules2 = import.meta.glob("@/assets/images2/*.{jpg,png,jpeg,webp}", {
  eager: true,
});
const allSrcs2: string[] = Object.values(modules2).map(
  (mod: any) => mod.default
);

function shuffle<T>(arr: T[]): T[] {
  const a = arr.slice();
  for (let i = a.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [a[i], a[j]] = [a[j], a[i]];
  }
  return a;
}
const randomFive = ref<string[]>(shuffle(allSrcs).slice(0, 5));
const randomFive2 = ref<string[]>(shuffle(allSrcs2).slice(0, 5));

const currentIndex = ref(0);
let Imgtimer: number | undefined;

onMounted(() => {
  timer = window.setTimeout(tick, 420);

  Imgtimer = window.setInterval(() => {
    currentIndex.value =
      (currentIndex.value + 1) % Math.max(1, randomFive.value.length);
  }, 5200);

  const canvas = canvasEl.value!;
  ctx = canvas.getContext("2d")!;

  // 当图片加载或资源就绪后调整 canvas 大小并启动渲染
  ROSE_IMG.onload = () => {
    resizeCanvas();
  };
  // 如果图片已经加载完（缓存情况），也要触发 init
  if (ROSE_IMG.complete && ROSE_IMG.naturalWidth > 0) {
    resizeCanvas();
  }

  window.addEventListener("resize", resizeCanvas);
});

onBeforeUnmount(() => {
  if (Imgtimer) clearInterval(Imgtimer);
  if (timer) window.clearTimeout(timer);

  cancelAnimationFrame(animationId);
  window.removeEventListener("resize", resizeCanvas);
});
</script>

<style lang="scss" scoped>
$bg-deep: #0d1116; // 极深夜黑／墨蓝底色
$deep-2: #141c22; // 深夜蓝黑
$accent-1: #3c9eff; // 冰蓝起始色（渐变起点）
$accent-2: #ff8a3c; // 炽橙终点色（渐变终点）
$muted-text: #dfe6eb; // 微冷灰白文字
$glass: rgba(60, 150, 210, 0.08); // 冷蓝玻璃衬光
$soft-warm: rgba(255, 150, 90, 0.04); // 橙火点缀微光

.home {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background: linear-gradient(180deg, $bg-deep 0%, $deep-2 70%);
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto,
    "PingFang SC", "Noto Sans CJK SC", sans-serif;
  position: relative;
  overflow: hidden;
  color: $muted-text;

  .rose-canvas {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
    pointer-events: none;
    filter: drop-shadow(0 6px 18px rgba(60, 150, 210, 0.02));
  }

  .carousel {
    position: absolute;
    inset: 0;
    z-index: 0;
    pointer-events: none;

    &::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(
        180deg,
        rgba(12, 14, 20, 0.22),
        rgba(14, 18, 24, 0.4)
      );
      pointer-events: none;
      z-index: 1;
      mix-blend-mode: soft-light;
    }

    .carousel-image {
      position: absolute;
      width: 100%;
      height: 100%;
      object-fit: cover;
      opacity: 0;
      transition: opacity 1s ease, transform 10s linear;
      filter: blur(0.6px) saturate(0.88) contrast(0.98);
      transform: scale(1.04);

      &.active {
        opacity: 1;
        transform: scale(1);
      }
    }
  }

  .carousel2 {
    display: none;
  }

  .center {
    position: relative;
    flex: 1 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 34px 20px;
    gap: 12px;
    z-index: 3;

    .title {
      z-index: 9;
      font-size: 4rem;
      margin: 0;
      font-weight: 800;
      line-height: 1;
      background: linear-gradient(90deg, $accent-1 0%, $accent-2 60%);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
      color: $muted-text;
      letter-spacing: 0.4px;
      text-shadow: 0 8px 28px rgba(20, 40, 60, 0.1),
        0 2px 6px rgba(60, 150, 210, 0.03);

      &:hover {
        text-shadow: 0 12px 36px rgba(255, 140, 60, 0.16),
          0 2px 6px rgba(255, 150, 90, 0.04);
        transform: translateY(-2px) scale(1.02);
      }
    }

    .subtitle {
      font-size: 2.02rem;
      min-height: 1.6em;
      color: rgba($muted-text, 0.94);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      z-index: 9;

      .typed {
        display: inline-block;
        letter-spacing: 0.4px;
        font-weight: 600;
        color: rgba($muted-text, 0.96);
      }

      .cursor {
        display: inline-block;
        width: 12px;
        height: 1.05em;
        margin-left: 6px;
        background: linear-gradient(180deg, $accent-1, $accent-2);
        border-radius: 2px;
        animation: blink 1s steps(1) infinite;
        transform: translateY(2px);
        opacity: 0.95;
        filter: drop-shadow(0 4px 10px rgba(60, 150, 210, 0.05));
      }
    }
  }

  .shore-footer-simple {
    background: linear-gradient(
      180deg,
      rgba(14, 20, 22, 0.7),
      rgba(18, 24, 28, 0.88)
    );
    border-top: 1px solid rgba(60, 150, 210, 0.05);
    color: $muted-text;
    font-size: 13px;
    position: relative;
    overflow: visible;

    .inner.container {
      width: min(1100px, 94%);
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
    }

    .center {
      text-align: center;
      flex: 1 1 auto;

      .slogan {
        background: linear-gradient(90deg, $accent-1 0%, $accent-2 60%);
        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;
        display: inline-block;
        line-height: 1;
        font-size: 14px;
        letter-spacing: 0.3px;
        text-shadow: 0 4px 16px rgba(20, 40, 60, 0.08);
      }

      .meta {
        color: rgba($muted-text, 0.68);
        margin-top: 6px;
        font-size: 12px;
      }
    }
  }
}

@keyframes blink {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@media (max-width: 720px) {
  .home {
    .carousel1 {
      display: none;
    }
    .carousel2 {
      display: block;
    }

    .center {
      padding: 18px 14px;

      .title {
        font-size: 2.4rem;
      }

      .subtitle {
        font-size: 1.5rem;
      }
    }
  }
}
</style>

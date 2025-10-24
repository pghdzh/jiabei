<template>
  <header class="app-header">
    <h1 class="title">永火典章：嘉贝莉娜狩契录</h1>
    <!-- 在线人数展示 -->
    <div class="online-count" v-if="onlineCount !== null">
      当前在线：<span class="count">{{ onlineCount }}人</span>
    </div>
    <!-- 移动端汉堡按钮 -->
    <button
      class="hamburger"
      @click="toggleMobileNav"
      aria-label="Toggle navigation"
    >
      <span :class="{ open: mobileNavOpen }"></span>
      <span :class="{ open: mobileNavOpen }"></span>
      <span :class="{ open: mobileNavOpen }"></span>
    </button>

    <!-- 普通导航 & 移动端下拉导航 -->
    <nav :class="['nav-links', { 'mobile-open': mobileNavOpen }]">
      <RouterLink
        v-for="item in navItems"
        :key="item.name"
        :to="item.path"
        class="nav-item"
        active-class="active-link"
        @click="mobileNavOpen = false"
      >
        {{ item.name }}
      </RouterLink>

      <a
        href="http://slty.site/#/redirector"
        target="_blank"
        rel="noopener"
        class="nav-item"
        active-class="active-link"
        @click="mobileNavOpen = false"
      >
        霜落映界
      </a>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";
import { io } from "socket.io-client";

const navItems = [
  { name: "永火序章", path: "/" }, // 首页 —
  { name: "猎魔行纪", path: "/timeLine" }, // 年谱
  { name: "炼狱手札", path: "/message" }, // 留言板
  { name: "影羽绘卷", path: "/gallery" }, // 图集
  { name: "狩契典藏", path: "/resources" }, // 资料库
  { name: "冥途回响", path: "/voice" }, // 语音馆
];

const mobileNavOpen = ref(false);
function toggleMobileNav() {
  mobileNavOpen.value = !mobileNavOpen.value;
}

const siteId = "jiaBei";

const onlineCount = ref<number | null>(null);

// 连接时带上 query.siteId
const socket: any = io("http://1.94.189.79:3000", {
  query: { siteId },
});

onMounted(() => {
  socket.on("onlineCount", (count: number) => {
    onlineCount.value = count;
  });
});

onBeforeUnmount(() => {
  socket.disconnect();
});
</script>

<style scoped lang="scss">
.app-header {
  /* 嘉贝莉娜 — 冷蓝至炽橙渐变猎魔风 */
  --deep-bg: rgba(12, 14, 26, 0.82); // 深夜蓝黑底色
  --glass-accent: rgba(80, 180, 255, 0.1); // 冷蓝玻璃衬光
  --accent: #3c9eff; // 冰蓝起始光
  --accent-2: #ff8a3c; // 炽橙终点光
  --muted-text: #edf4fa; // 微淡冷白文字
  --warm-glow: rgba(255, 150, 90, 0.06); // 橙火点缀微光
  --faint: rgba(80, 180, 255, 0.04); // 微弱冷蓝背景点

  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  height: 64px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 40px;
  background: linear-gradient(
    180deg,
    rgba(12, 14, 26, 0.54),
    rgba(16, 18, 30, 0.46)
  );
  backdrop-filter: blur(4px) saturate(1.1);
  box-shadow: 0 6px 28px rgba(8, 10, 14, 0.52),
    0 0 10px var(--glass-accent) inset;
  border-bottom: 1px solid rgba(80, 180, 255, 0.05);
  animation: fadeInDown 0.6s ease-out both;

  .title {
    font-size: 26px;
    font-weight: 700;
    color: var(--muted-text);
    background: linear-gradient(90deg, var(--accent), var(--accent-2));
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    letter-spacing: 0.4px;
    text-shadow: 0 4px 16px rgba(30, 40, 60, 0.18), 0 1px 0 var(--warm-glow);
    transition: transform 0.28s ease, text-shadow 0.28s ease;
    animation: float-slow 8s ease-in-out infinite;

    &:hover {
      transform: translateY(-2px) scale(1.03);
      text-shadow: 0 8px 28px rgba(255, 140, 60, 0.14), 0 1px 0 var(--warm-glow);
    }
  }

  .online-count {
    position: relative;
    margin-left: 16px;
    padding: 6px 14px;
    font-family: "Cinzel Decorative", serif;
    font-size: 1rem;
    color: var(--muted-text);
    background: linear-gradient(
      135deg,
      rgba(80, 180, 255, 0.03),
      rgba(255, 140, 60, 0.02)
    );
    border: 1px solid rgba(80, 180, 255, 0.12);
    border-radius: 24px;
    backdrop-filter: blur(6px);
    box-shadow: 0 6px 18px rgba(8, 10, 14, 0.48),
      0 0 8px rgba(80, 180, 255, 0.03);
    overflow: hidden;
    cursor: default;
    transition: transform 0.22s ease, box-shadow 0.22s ease;

    &::before {
      content: "";
      position: absolute;
      bottom: -2px;
      left: -40%;
      width: 180%;
      height: 2px;
      background: linear-gradient(
        90deg,
        transparent,
        var(--accent-2),
        transparent
      );
      opacity: 0.9;
      filter: blur(5px);
    }

    &:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 28px rgba(8, 10, 14, 0.54),
        0 0 18px rgba(80, 180, 255, 0.06);
    }

    .count {
      display: inline-block;
      margin-left: 6px;
      font-weight: 700;
      color: var(--accent-2);
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      text-shadow: 0 0 6px rgba(80, 180, 255, 0.04);
    }
  }

  .nav-links {
    display: flex;
    gap: 22px;
    align-items: center;

    .nav-item {
      position: relative;
      color: var(--muted-text);
      font-weight: 500;
      text-decoration: none;
      padding: 6px 4px;
      border-radius: 6px;
      transition: color 0.22s ease, transform 0.16s ease;
      font-family: "STKaiti", "KaiTi", "Songti SC", "Georgia", "PingFang SC",
        "Microsoft YaHei", serif;
      -webkit-font-smoothing: antialiased;
      text-rendering: optimizeLegibility;
      font-style: italic;
      font-size: 18px;
      &::after {
        content: "";
        position: absolute;
        left: 50%;
        bottom: -6px;
        width: 0;
        height: 3px;
        background: linear-gradient(
          90deg,
          rgba(80, 180, 255, 0),
          var(--accent-2),
          rgba(80, 180, 255, 0)
        );
        transition: width 0.36s cubic-bezier(0.2, 0.9, 0.2, 1),
          left 0.36s cubic-bezier(0.2, 0.9, 0.2, 1), opacity 0.24s;
        transform: translateX(-50%);
        opacity: 0.95;
        border-radius: 3px;
        filter: blur(0.6px);
        background-size: 180% 100%;
        animation: flow 7s linear infinite;
      }

      &:hover {
        color: var(--accent-2);
        transform: translateY(-1.8px);
        text-shadow: 0 0 6px rgba(80, 180, 255, 0.02);
      }

      &.active-link {
        color: var(--accent);
        font-weight: 600;

        &::after {
          width: 92%;
          opacity: 1;
        }
      }
    }
  }

  .hamburger {
    display: none;
    flex-direction: column;
    justify-content: space-around;
    width: 28px;
    height: 24px;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0;

    span {
      display: block;
      width: 100%;
      height: 3px;
      background: rgba(237, 244, 250, 0.9);
      border-radius: 2px;
      transition: transform 0.28s ease, opacity 0.28s ease, background 0.28s;
      box-shadow: 0 2px 6px rgba(16, 18, 30, 0.18);
    }

    span.open:nth-child(1) {
      transform: translateY(10px) rotate(45deg);
    }

    span.open:nth-child(2) {
      opacity: 0;
    }

    span.open:nth-child(3) {
      transform: translateY(-10px) rotate(-45deg);
    }
  }

  @media (max-width: 768px) {
    padding: 0 20px;

    .title {
      display: none;
    }
    .hamburger {
      display: flex;
    }

    .nav-links {
      position: absolute;
      top: 64px;
      left: 0;
      right: 0;
      flex-direction: column;
      background: linear-gradient(
        180deg,
        rgba(16, 10, 14, 0.98),
        rgba(12, 8, 12, 0.995)
      );
      backdrop-filter: blur(10px);
      gap: 0;
      overflow: hidden;
      max-height: 0;
      transition: max-height 0.34s ease;
      border-top: 1px solid rgba(255, 140, 60, 0.035);

      &.mobile-open {
        max-height: 520px;
      }

      .nav-item {
        padding: 14px 20px;
        border-bottom: 1px solid rgba(255, 140, 60, 0.03);
      }
    }
  }
}

@keyframes flow {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes float-slow {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-4px);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes fadeInDown {
  0% {
    opacity: 0;
    transform: translateY(-10px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>

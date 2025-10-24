<template>
  <div class="megumi-page" aria-live="polite">
    <main class="container" ref="mainContainer">
      <!-- HERO 区域 -->
      <header class="hero" role="banner">
        <div class="left-col">
          <button class="avatar-card">
            <picture class="avatar-wrap">
              <img
                src="@/assets/images1/slty (12).webp"
                class="avatar"
                loading="lazy"
                decoding="async"
              />
            </picture>
            <div class="avatar-meta">
              <span class="avatar-badge">共鸣能力：炼狱</span>
            </div>
          </button>
        </div>
        <div class="right-col" ref="metaCard">
          <div class="hero-panel">
            <h1 class="name">
              嘉贝莉娜 <span class="jp">（黑海岸的客卿）</span>
            </h1>
            <p class="subtitle">永火的猎魔人，炼狱中的回响</p>
            <p class="lead">
              外表冷峻，杀伐果断，于索拉里斯四处游猎的“猎魔人”，亦是人们口中“永火的恶魔”。如今正作为黑海岸的客卿活跃于世界各地。
            </p>
          </div>
        </div>
      </header>

      <!-- 内容卡片区 -->
      <section id="personality" class="card personality">
        <div class="card-head">
          <h2>核心机制</h2>
        </div>
        <ul class="traits">
          <li>
            阈限状态下，嘉贝莉娜攻击命中目标后，可以积攒【罪火】，当【罪火】达到100点时，短按共鸣技能，可进入恶魔位格。
          </li>
          <li>
            进入恶魔位格时会消耗所有【罪火】并获得100点【净炼火】。恶魔位格期间，【余火】越多，敌人受到各种强化攻击的伤害越高。
          </li>
          <li style="font-weight: bold">输出流程：</li>
          <li>基础流程：Z（长按三段）-EA-AA-R-E-AAAAA-闪-AAA-EQ</li>
          <li>
            技能缩写：普攻 = A，重击 = Z，共鸣技能 = E，共鸣解放 = R，声骸 = Q
          </li>
        </ul>
      </section>

      <section id="overview" class="card overview">
        <div class="card-head">
          <h2>角色背景与形象</h2>
        </div>
        <div class="two-col">
          <div class="text-block">
            <h3>背景</h3>
            <p>
              “以此恶火，狩猎邪魔。”
              嘉贝莉娜，既是“永火的恶魔”，亦是狩魔的猎人。她从无数的生死搏杀和战火余烬中走出，穿行于黑暗与烈狱，从一个猎场，赶赴下一个猎场——她的狩猎，永不终结
            </p>
          </div>
          <div class="text-block">
            <h3>外貌／着装</h3>
            <p>
              嘉贝莉娜的右肩后搭着长长的蓝黑色羽毛披肩，腰后也装饰着几簇柔软飘逸的羽毛，衣服开衩的后摆更似鸟类张开的翅膀，看起来就像是一只带有“死亡气息”的“黑鸦”。飘落的黑羽即是她到来的标识，亦是她对猎物“命定一死”作出的宣告。
            </p>
          </div>
        </div>
      </section>

      <section id="resonance-status" class="card overview">
        <div class="card-head">
          <h2>共鸣状况</h2>
        </div>
        <div class="two-col">
          <div class="text-block">
            <p>
              嘉贝莉娜共鸣源已无法确认，其先天之火因黑潮污染而衰变，却始终未曾熄灭。后体内频率与黑潮造物“奇美拉”发生融合，火焰性质再度改变，具有“吞噬”其他频率的能力。
              对象借由该手段猎杀残象，并将它们的频率吸收转化为自己的能力，现驱使着体内多种残象力量进行战斗。
              被那火焰吞噬的“恶魔们”只存在两种选择：接受净炼，为她所用，或者……化为灰烬，彻底湮灭。
            </p>
          </div>
        </div>
      </section>

      <section id="food" class="card special-section">
        <div class="card-head">
          <h2>超级加倍特浓奶昔刨冰</h2>
        </div>
        <div class="content two-col">
          <div class="img-area">
            <img
              src="./img/food.png"
              alt="迎春酥"
              loading="lazy"
              decoding="async"
            />
          </div>
          <div class="text-block">
            <p>
              嘉贝莉娜独创的甜品配方，大块冰激凌覆盖在大碗创冰之上，淋有各色鲜果果酱提升风味，分量充足，尽情畅享。
            </p>
            <p>
              除此之外，还有各式残象形象的糖果饼干作为装点，考虑到大众接受度，她也特意将它们制成了相对可爱的模样。其中或许蕴含着嘉贝莉娜的一些行事理念：对待残象要“咔嚓”一下干脆利落，对待生命则要仔细品尝其中风味。
            </p>
            <p>
              但据嘉贝莉娜所言，无论分开还是混合食用，随心所欲就好，她的建议只有一个：趁着没化吃。
            </p>
            <p>
              生命中很多珍贵的瞬间就像冰花一样“转瞬即逝”，但不必担心，美好的滋味总会留在味蕾弥久不散，无论何时都能令人再次回味。
            </p>
          </div>
        </div>
      </section>
      <section id="shattered-crystal" class="card special-section">
        <div class="card-head">
          <h2>便携式频录装置·试作型</h2>
        </div>
        <div class="content two-col">
          <div class="img-area">
            <img src="./img/item1.png" loading="lazy" decoding="async" />
          </div>
          <div class="text-block">
            <p>
              嘉贝莉娜自拉海洛地区淘来的磁带播放器，随着当地技术的迭代，这款型号现已停产，已成孤品。物件虽老，却具有记录持有者“本质频率”的功能，能够帮助嘉贝莉娜对抗体内残象频率的侵蚀，也是她在猎场与猎场之间长途辗转时，为数不多的消遣与慰藉。
            </p>
            <p>
              嘉贝莉娜也在其中刻录了不少钟爱的音乐。如果你愿意尝试通过这种方式了解她，她也很愿意与你分享“她的歌曲”。
            </p>
          </div>
        </div>
      </section>

      <section id="cyclic-clock" class="card special-section">
        <div class="card-head">
          <h2>“一夜好梦”</h2>
        </div>
        <div class="content two-col">
          <div class="img-area">
            <img src="./img/item2.png" loading="lazy" decoding="async" />
          </div>
          <div class="text-block">
            <p>
              嘉贝莉娜制作的手工艺品，由她的羽毛与一些常见材料编织而成，每一样都是精挑细选，代表着一份美好的祝愿。
            </p>
            <p>
              对嘉贝莉娜而言，一个可以安然入睡的夜晚是难以多得的美好时光，她却时常会受到体内残象的侵扰，在无数重叠交织的梦境中与它们再度展开厮杀……她曾为此寻求解法，希望借这种手工艺品守住自己的片刻安宁……但结果，往往不尽人意。
            </p>
            <p>
              不过，当她将其转送给一些孩童后，它却发挥了本有的愿力：在他们的梦境中，每当“梦魇”袭来，总会有一位洁白的女子前来为他们击退怪物，带领他们走出幽谷，守护着他们，直至黎明到来。
            </p>
            <p>
              奇美拉对嘉贝莉娜如此解释：那些羽毛附带着她的频率，因此才能吓退“梦魇残象”的侵袭，而对本就存在于她体内的残象来说，自然不具效力。
            </p>
            <p>
              这番话虽令她感到失落，却也令她得到了些许宽慰——至少，她并不是只能为人们带去恐惧。
            </p>
          </div>
        </div>
      </section>

      <section id="collective-album" class="card special-section">
        <div class="card-head">
          <h2>“最初的血誓”</h2>
        </div>
        <div class="content two-col">
          <div class="img-area">
            <img src="./img/item3.png" loading="lazy" decoding="async" />
          </div>
          <div class="text-block">
            <p>
              嘉贝莉娜利用血液凝聚而成的“第一颗子弹”，如今她已将其赠送予你。
            </p>
            <p>
              在旧日新联邦的“无法之地”游历时，她于一处秘密结社，习得了这项名为“血誓”的“残忍技艺”。学习者或是走投无路的亡命之徒，或是与她相同的沾染黑暗之人。出于各种缘由，他们选择了这样一条“猎人之道”，只求在对抗邪恶的仇敌时，能够以最意想不到的方式发出最致命的一击。嘉贝莉娜学习得很快，成果也更为显著——她的血液早已化作烈火，她也早已熟稔于这条道路。
            </p>
            <p>
              而作出血誓的猎人们，都会拥有这样一颗子弹，它也被称作“最初的血誓”。在他们之间，还有一句俗语广为流传：“子弹上刻着你的名字”，象征着他们至死追杀猎物的决心。只是，在那时的无法之地，昔日盟友化作仇敌不过瞬息，而这些离群索居者，通常更为珍视同道之人，为此，他们曾发明了一种“誓盟仪式”……嘉贝莉娜未曾缔结盟约，却仍旧记得那仪式与意义。
            </p>
            <p>
              当一位猎人将“最初的血誓”赠予出去时，也会在其上刻下受赠者的名字——这即是那最为简易，却永不磨灭的古老盟约：她将化作【TA】的子弹，永不背叛，永不弃逃，直至鲜血干涸，烈火燃烬。
            </p>
          </div>
        </div>
      </section>

      <section
        id="timeline"
        class="card timeline"
        aria-labelledby="timeline-heading"
      >
        <div class="card-head">
          <h2 id="timeline-heading">共鸣链详解</h2>
        </div>
        <div class="tl-wrap" role="list">
          <div class="vl" aria-hidden="true"></div>
          <ol class="tl-list">
            <li
              v-for="(ev, i) in timeline"
              :key="i"
              class="tl-item"
              role="listitem"
              tabindex="0"
              :aria-label="``"
            >
              <div class="tl-card">
                <h3 class="tl-title">第 {{ i + 1 }} 链 · {{ ev.title }}</h3>
                <p class="tl-desc">{{ ev.desc }}</p>
              </div>
            </li>
          </ol>
        </div>
      </section>

      <section class="ll-stories" ref="storyRef">
        <div class="card" role="region" aria-labelledby="stories-title">
          <header class="card-head">
            <h2 id="stories-title" class="card-title">炼狱纪事</h2>
          </header>

          <main class="card-body">
            <transition name="fade-slide" mode="out-in">
              <article
                :key="items[current].id"
                :id="`panel-${items[current].id}`"
                class="story"
                role="tabpanel"
                :aria-labelledby="`tab-${items[current].id}`"
              >
                <h3 class="story-head">{{ items[current].title }}</h3>
                <div class="story-content">{{ items[current].content }}</div>
              </article>
            </transition>
          </main>

          <footer class="card-foot">
            <button class="nav-btn" @click="prev" aria-label="上一则故事">
              ‹
            </button>
            <div class="pager">{{ current + 1 }} / {{ items.length }}</div>
            <button class="nav-btn" @click="next" aria-label="下一则故事">
              ›
            </button>
          </footer>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

const timeline = ref([
  {
    title: "不熄抵牾抗争之心",
    desc: `嘉贝莉娜施放共鸣技能·恶翼扬升时，每点【余火】额外为普攻·炽天猎杀、重击·炼羽裁决、空中攻击·火狱暴雨、共鸣技能·掠袭、闪避反击·罪业当涤提升2%暴击伤害，至多提升80%暴击伤害，退出恶魔位格时移除。
恶魔位格期间，普攻·炽天猎杀第5段、重击·炼羽裁决第3段、空中攻击·火狱暴雨免疫打断。`,
  },
  {
    title: "行过烈狱与幽暗冥途",
    desc: `内燃烧提供的攻击加成提升350%。`,
  },
  {
    title: "再燃血狩死猎之誓",
    desc: `共鸣解放的伤害倍率提升130%。`,
  },
  {
    title: "承负无薪孤惧苦火",
    desc: `队伍中的角色施放声骸技能时，使队伍中所有角色全属性伤害加成提升20%，持续20秒。`,
  },
  {
    title: "纵使光明远去，厄难焚身",
    desc: `共鸣技能·迫近，共鸣技能·恶翼扬升，共鸣技能·掠袭的伤害倍率提升150%。`,
  },
  {
    title: "我仍炽耀不移，自有永有",
    desc: `恶魔位格升级为永恒位格，永恒位格保留恶魔位格全部原有效果。
永恒位格期间普攻·炽天猎杀、重击·炼羽裁决、空中攻击·火狱暴雨、闪避反击·罪业当涤的伤害倍率提升60%。

嘉贝莉娜施放共鸣技能·恶翼扬升时，每点【余火】额外为普攻·炽天猎杀、重击·炼羽裁决、空中攻击·火狱暴雨、共鸣技能·掠袭、闪避反击·罪业当涤提升0.875%热熔伤害加深，至多提升35%热熔伤害加深，退出永恒位格时移除`,
  },
]);

const reducedMotion =
  window.matchMedia &&
  window.matchMedia("(prefers-reduced-motion: reduce)").matches;

const items = [
  {
    id: "1",
    title: "猎人的一日",
    content: `
“恶魔已经死去，孩子们可以放声歌唱了。”

猎魔人缓缓收回燃烧的羽翼，自高天降落在人群中央。腰间猎枪散发的热量，正昭示着她刚刚完成了一场狩猎。

残象，由人类残存的、混乱的频率与能量构成的超自然存在，世间恶意与毁灭的具象。尽管它们已经被科学地分门别类，但在某些地区，人们仍会以“恶魔，邪灵”之类的名讳相称，并从各种传说怪谈中取得灵感为他们命名。而这世上，也总有一些出于各种目的专门狩猎强大残象之人，或为赏金，或为研究，又或是单纯地寻求挑战。为向那些可怖存在表示“敬意”与“决心”，他们也将那自古相衬的名号沿用了下来——“猎魔人”。

猎魔人们大都会用终端取得频率，或者带回声核证明成果，但她却总是“空手而归”，只是宣称自己已经将目标解决，并将猎物弱点与应对方法逐一转述。口说无凭，她只好伸出自己的右手，轻声呼唤……当“千喉歌者”的身影自她体内再度浮现，人们才彻底相信了她的说辞……周围的空气，也因恐惧而随之凝结。

类似的情形总是无法避免。她聆听着人们的窃窃私语，对她的怀疑，误解，敌意，却从不出口反驳：有人说她是某种人与残象融合的实验品，杀戮本是她的使命；也有人说她是某种残象频率变异的造物，生来便带着罪孽；还有人传言她与“恶魔”签订了契约，因此丧失了情感——关于这点，她往往欣然承认，这总能成为她用来回避一些问题的借口。

换作平常，她只会在此刻转身离去，但她难免也想犒劳一下自己。于是，在人们各异的目光中，她在一家露天餐吧坐了下来，点了几杯蓝莓冰激凌奶昔静静品尝。只有方才与之同行的猎人们知道，在那冷峻淡漠的外表之下，究竟隐藏了怎样炽热的一种杀意；战斗时，她又会对敌人施展怎样凶残的手段——

 

千喉歌者，一种活跃于林间幽谷的兽型残象。它诞于人间的嫉妒之心，通过模拟人类声音引诱孩童靠近，以掠夺他们的歌喉为乐。尽管她已经提醒过同行的猎人不要在它的主场作战，但出于对她年轻外表的不信任……他们还是落入了敌人的圈套：刺耳的音波在谷壁的反射下成倍增幅，小队几乎瞬间崩溃。年轻的猎魔人却在此刻刺破了自己的耳膜，鲜血先行，烈火后至，几息间便冲到敌人身前，枪管直抵胸膛。枪声过后，林间只剩下了她阴冷的低语：“该赎罪了。”

人们随即便见识到，那妖物为自己的恶行付出了何种代价：她以右手紧扼妖物的咽喉，恶火如长蛇蜿蜒直上将其包裹，“歌者”只能发出惨烈扭曲的哭嚎，直至化作一缕残魂，融入了她的体内——这也是她行狩所求的报偿。而她那浴血焚腾的身躯，也以一种极为恐怖的再生能力完成了愈合。一时无法分辨……谁才是真正的“恶魔”。

但所有人都无比清楚，她的能力足以支持她独自逃离，而她却选择了留下……若非如此，他们无法活下来。

而后，她只是拍了拍肩上的余烬，不知从何处变出了几根雪糕，一脸平常地向着惊魂未定的众人询问：“来一根？”

这凶险的狩猎，仿佛只是她生活中，再稀松不过的一件琐事。

待寒凉的甜蜜将杀戮的余温彻底冷却，她便再度展开羽翼，留给人们的，只有一个神秘的背影。

无人知晓她从何而来，又将去向何方。懵懂的孩童会在她畅饮三大杯冰激凌后，将她称作一只“冰激凌恶魔”；广识之人则因她散发着恶意频率的火焰，联想起那只传说中的“火魔”……如有人拾起她散落的羽毛，会发觉那足以斩断残象的锐羽，竟也附带着柔和的气息，还有一种……久经磨砺的苦涩。不由因此怀疑，也许她的自由与洒脱，只是因为无处落脚。

她很少提及自己的过去，有人问起，也只会是轻描淡写，几笔带过。

关于她的故事，还要从很早很早以前说起。那时的她，还拥有一头淡金色的短发，一双闪烁着熠熠金辉的眼眸……那时的她，也还没有被人们称为……“嘉贝莉娜”。
    `,
  },
  {
    id: "2",
    title: "童年远去",
    content: `
     人们说，安吉尔是在“光明与火焰的怀抱”中降生的。她生于一个金黄色的黎明，生而带有璀璨的火焰。

安吉尔父母的共鸣能力并不出众，若是在拉古那，人们会将她的降生视作一种“神迹”……但很可惜，七丘是没有“神”的，这里只以征服力量为荣。

对孩童而言，过早地拥有强大的共鸣力，未必是一种完全的馈赠，那往往意味着失控的风险。儿时的安吉尔牢记着父母的教诲，时刻克制着自己的情绪，以防那些跃动的火苗灼伤他人。在最该肆意欢笑的年纪里，她也因此显得与一众同龄人格格不入。孩子们总称她是一个冷冰冰的女孩，更有人将那种疏离感，视作一种傲慢。胆小的孩子选择远离，好斗的孩子则是挑衅，将她视作必须打倒的劲敌。那或许并非出自恶意，只是在孩子们眼里，无论性格，天赋还是身份，她都与他们太过不同……如同一个异类。

 

她的父母是拉古那的流民。二人一路辗转至此，听闻怪物作乱，父亲便出手相助；路遇讨者，即使日子再穷，母亲也会把食物分给更穷的人。在两座城邦彼此偏见尚未打破的年代里，这些品格使得他们被这座小镇接纳，在这落脚生根。

母亲常以圣典中的箴言，教她恩慈仁爱，宽容忍让，她都有很好地吸收进去。只是，在七丘，一味忍让是无法换来尊重的。在两种文化的交错熏陶之下，安吉尔也创造出了自己的信条：与人为善，从不惹事……但如果有谁打了她一拳，她一定会加倍奉还回去。

好在，在七丘，孩子们身上若是没点“磕碰”反而不够正常，但安吉尔并不总想为父母招惹麻烦，渐渐也习惯了独处，常会去到父亲好友费罗大叔的铁匠铺“避静”。不仅因那少有孩童光顾，许是天生对火焰亲近，她喜欢燃烧的炉火，迸溅的火星，还有铁锤敲击叮叮当当的清脆声音。也是在那里，安吉尔与一位红头发的女孩相识，因她那直爽的性子结交了不少伙伴，童年也有了更多欢笑，不再那么孤单。她们曾在炉火旁促膝长谈，诉说彼此的困惑，名为奥古斯塔的女孩更在意每把武器承载的故事，安吉尔则对名为“淬火”的神秘仪式充满好奇，费罗大叔常如此解释：再好的刀胚，不经淬火磨砺，是不会成为一把好武器的。

她不理解的事情还有很多，例如为何七丘的风总带有铁锈的气味，那时她还只当作是熔炉与风箱的鼓息。但随着成长，也逐渐明白了其中含义——那风自狩原而来，来自陨落的枪尖，折断的剑脊……还有战士们淋漓的鲜血。

 

十六年前，狩原的涨潮期到来。法比亚纳的人们日夜忙于行猎，她看到父母疲惫的身影，目睹人们伤痕累累地归来，也听见人们谈论着关于“力量”的种种……不由在心中立下了一个小小的誓言。

自那天起，安吉尔便开始了近乎疯狂的苦训。她向大人请教武艺，跟随巡林队学习狩猎，四处寻找对手挑战，如一只渴水的小兽一般，在世间所有泉中痛饮——一切都是为了七丘的“青训选拔赛”：获胜者将提前接受更专业的角斗士训练，更早地成为一名猎者。

付出总有回报，赛场之上，安吉尔战胜数十名对手脱颖而出，与时下种子选手阿奇莉娅展开决战。据说对方曾在野外独自击退黑潮造物，那经历生死考验的心性将安吉尔逼得连连败退。她不想错失这次机会……最终，选择释放出了自己的共鸣力。

光芒如火焰迸发，炽热却未灼伤对手，耀眼却未刺痛众人双目。但只此一击，足以将局势彻底逆转……胜负既定，安吉尔上前关心对手，却被其不甘的话语刺痛——“为什么，你生来便可以拥有这样强大的力量？”

这也是她儿时以来，一直在思考的问题……为什么是自己？

明明有更多、更努力、更优秀的人，他们为什么没能得到这份馈赠？

如果人们都拥有和我一样的力量，是不是就不会受伤了？

如果我能运用好这份力量，是不是也可以帮上大家？如果……

天空中，狩王鹫的啼啸打乱了她的思绪，它们正整齐划一地向着狩原飞去——那里是所有狩猎的起点。

是的，至少，现在她已经证明，自己能够掌控这份力量了。用不了多久，她就会乘着狮王鹫在猎场上翱翔，用她的力量，去猎杀那些邪恶的造物，守护更多的人……这即是她所立下的誓言。她的“狩猎”，很快就会开始。

一切本该如此，一切的确如此。命运和她开了一个简单的“文字玩笑”，又或许，这是一场早有预谋的捉弄，命运终于向这个孩子展露了它那可憎的狰狞面容：凡赠予的就会收回，凡向善的就要教她作恶，凡不畏的，就要打到她屈膝伏地，长跪不起。

只不过，她从未去过四方殿，不曾理解命运，也不想理解命运。她只知道，如果有谁打了她一拳，她一定会加倍奉还回去——无论对方是谁……是人，是神，抑或是命运，都不会例外。
    `,
  },

  {
    id: "3",
    title: "安吉尔的灰烬",
    content: `
      她仍记得自己第一次“吃掉”一只残象时，身体所产生的“排异反应”：那是一种灼烧五脏六腑的痛苦，仿佛要将她的灵魂都焚噬殆尽……但相比之下，更令她痛苦的，是自己的弱小。

她清楚自己的第二次生命因何而来，也记得自己曾立下的誓言，可当她真正面对那些“邪恶的真身”时，才发现自己竟是那样的无力。

于是，她出让了自己的频率，选择与体内的恶魔“签订了契约”，踏上了一条无法回头的道路。

但她始终认为，这是她本该开始的“狩猎”：那未能参加的出猎仪式，本该由谕女点燃的圣火……不过是被她以“嘉贝莉娜“的恶火所点燃。

 

就这样，少女负火而行，游历文明与荒野，从流言与传说中探听情报，出没于充斥尸骸与白骨的偏僻地界，只为狩猎那些因世间种种情感而生的可怕造物。

她曾在险峻的峭壁与敌人搏杀，与之一同坠入崖底——哪怕那时的她尚未学会飞翔。

她曾在幽邃的湖底与敌人对决，只因对方惧怕深水——即使她自己的水性并不出色。

她杀死过许许多多的怪物，也险些死于许许多多的怪物手下。

奇美拉本以为，一个侥幸获得了第二次生命的人，理应格外珍惜自己的生命，苟且偷生，直至意志磨灭，落入它的圈套……却从未想过，自己也会被它所钟意的血性所反噬：这个女孩会无数次选择挑战远比她强大的对手，甚至以生命为筹码，将自己化作了束缚它的血肉囚笼。

这第二次生命本就来之不易，若是一味苟且偷生，此生未免太过虚无漫长。对她而言，这不仅仅是为了驯服体内的那只“恶魔”，也是为了从命运那里，夺回更多的力量。

奇美拉的话语并非一无是处，没有力量的善良是最可悲的，若想拯救他人，必须也要拥有“作恶的能力”。她记得母亲亦曾说过：“树木的根若无法扎进地狱，它的枝叶也无法触及天堂。”不过，她从未想过进入天堂，如果能触及地狱的话，她只想往地狱去得更深一些，要将更多的邪魔恶灵拖入进去，让它们在那浊燃的烈焰中臣服，或者永世沉沦……纵然那业火也会灼伤她自己。

但有时，她也会质问自己，她几乎已经成为了人们口中的恶魔，甚至……自己的这副身躯，真的还能算得上“人”吗？她又是否真的可以驾驭黑暗为善，却不被其吞噬？

尽管她会向人们毫无保留地施予善意……但她也做过一只恶魔该做的事。

她曾去向南方大地的边陲小镇猎杀“无名影魔”，传言在它的影响下，当地人们迷恋上了某种“调换频率”的技术，他们残害收集过路者的频率，换来自己的长生。可当影魔死去，仪器崩塌，不朽之人瞬间衰老，陷入癫狂，直到生命尽头仍不知悔改：他们仍在思考，如何献祭别人的生命令自己生还……

她终于明白，并非是影魔影响了他们的心智，而是他们非人的欲念“召唤”出了影魔……最终，她用一场大火，将那化作“人间地狱”的小镇烧为了灰烬，让那些罪恶彻底断绝在了自己这里。

那场狩猎教她明白，世间邪魔并非只有残象一种，以及……所谓恶魔，究竟因何而至。

也许自己仍会思考这个问题，便是依旧为人的答案——又或许，这个世界早就给予了她答案。

她曾见过人们为了蝇头小利你争我夺，也曾见过人们为了微渺希望献身赴死；她看见一座城市毁于人们的私欲，也看见泥泞的废墟中开出最洁白的花朵……人性总是迷人又脆弱，善良与邪恶，卑劣与伟大往往同道而行，世界也并非是纯粹的黑与白，那道“灰色”恒久地存在于这个世界之中——这是最适合她悬停的位置。

年轻的猎魔人逐渐习惯了人们对她的态度，也习惯了在夹缝之中生活。过去她因无法适应长成的火羽而撞得头破血流，如今已经学会了游刃飞翔。

白日，她便长久地在那道边界之上徘徊，如猎鹰般寻找着猎物，也默默守望着这片尘世；夜晚，她就在无人的枝头栖息，独自守护着历代星辰，也被历代星辰所守护。

她依然记得自己立下的誓言。曾经，她也会对那些“阴影与力量”感到恐惧，后来她选择利用恐惧，现在，则要选择成为“恐惧本身”，成为……令恶魔也感到恐惧的存在。
    `,
  },

  {
    id: "4",
    title: "内在的天空",
    content: `
     落日，黄沙，硝烟。这次的猎场，不比以往的更加残酷。

昔日的少女如今愈发冷酷成熟，身上早已布满累累疤痕，破旧衣衫下散发出的杀伐气息，足以令无数残象避之不及。

尽管如此，在那尊钢铁之躯面前，她的存在仍是如此渺小——杜拉罕，在大地之上四处征伐的无头骑士……它的出现没有任何征兆。

交手过后，嘉贝莉娜很快便发觉“黑潮感应”失效的原因：它的频率太过强大，以至于成为了黑潮都不敢妄图染指的存在。

她早已解放了奇美拉，任由其享受着久违的生死搏杀……但这也仅仅是限制住了杜拉罕的战马。

要逃走吗？她不仅一次产生过这个想法。但她知道，自己身后几百米，有一对正在逃命的母子。自己能多拖住敌人一秒，她们幸存的概率便能多上一分。她们会前往几公里外的部族报信，让那里的人们远离这场灾难，更有机会唤来其他势力的支援，将它的铁蹄拦在文明之前——只要自己还站在这里，希望就能再传播出去一点。所以理由也很明显了：这不是她能否战胜的问题，而是她必须站在这里。

她不畏惧死亡，却也不甘在这里终结。哈尔庇恩化出的锐翼已经折断，现在……她唯一能够依靠的，只有“嘉贝莉娜”奄奄一息的业火。但在这空无人烟的战场上，她已无处吸食更多的恨意。

“……想要点燃这团火焰的方法，你一直都知道的。”

一道稚嫩的声音在她心中无端响起。

“如果嘉贝莉娜生来以恨火为食……”

“那就憎恨你自己吧。”

“憎恨你的弱小，憎恨你的无力，憎恨你的犹疑……”

“如果‘火魔’的火焰还不够……那就用那些火焰，去点燃自己。”

“如果‘眼魔’告诉你，它的外在坚不可摧……那就相信你自己的‘眼睛’。”

她不知道那声音究竟来自于何种存在，那话语却提醒着她，教她相信自己的判断……就像她一路以来，一直相信着自己一样。

恨意与火焰一同自她的指尖缓缓浮现，虽然微弱，但足以支持她划过自己的伤口，引燃她的血液与身体。

杜拉罕的巨剑再度挥来，她已有一战之力，却不再与之正面相碰，而是瞄准了它头颅处的空缺，纵身跃入那空心的铠甲之中。

滚滚烈焰瞬间将她吞没，但如她所想，这里正是它的弱点——它内在的火焰是如此孱弱，远不及她的烈火炽热。

两股火焰交织碰撞，那庞大的身躯也开始轰然作响……最终，一切归于了寂静。

 

不知过去了多久，嘉贝莉娜在那对母子的怀抱中醒来。

自己是被救活了吗？嘉贝莉娜为此庆幸。于是，她于指尖再度燃火，尝试引燃自己——她庆幸的是，同样的招式，她又可以再用一次了。

好在最后，她还是被劝阻了下来……因那无头的铁骑早已不知去向。据人们所言，救援赶到时，只看到天边燃起了一道金色的黎明，嘉贝莉娜则独自昏倒在黄沙之上。直到旁人提醒，她才后知后觉地意识到身体产生的变化：在那场纯粹内在的比拼里她早已获胜，杜拉罕的频率已经融入了她的骨血，无头骑士的再生能力修复了她几近死灭的躯体，连同昔日的累累伤疤一并洗涤——不死的火魔，现在名副其实了。不过她还是没什么活着的实感，只是知道，同样的招式，她又可以再用无数次了。

她那身残破的衣装也被烧得不成样子，有人拾起地上几片散落的白羽，想要以其为材，为她织就一身崭新的行装。她只是指了指自己肩上的黑羽，说道：“这样就好”。

她猜想，杜拉罕也会惧怕耀眼的金黄，至于那金色的黎明由谁带来，她已无从知晓，或许只是一场天地异象，白羽也只是路过的飞鸟所留，它们与自己实在搭不上什么关系。黑色的行装，更符合她行事的风格。

不久之后，嘉贝莉娜再度启程时，奇美拉也终于苏醒。她询问：自己听到的那个声音究竟是什么？

“那是你体内最为古老，也是最为强大的恶魔。”

“比你还要早存在于我的体内？”

“当然。她早就存在于你的肉体与心灵之中了，不然我也不可能直到现在还没有‘吃掉’你……也是她，帮助你战胜了‘嘉贝莉娜’。”

“我不记得我有吸收过这样一头残象。”

“未必是残象……你当真不知道她的名字？”

“不知道。”

“……你的无知总是令我怀疑，你到底是怎么活到今天的？”

“少废话，说。”

“……安吉尔。她的名字是，安吉尔。”
    `,
  },

  {
    id: "5",
    title: "漫长的归来",
    content: `
    她曾将枪口对准自己，但这里并非是她的梦境。

她已在这无边的黑暗中斩杀了无数黑潮造物，也因此而疲惫不堪，重重跌倒在黑色的潮水之上——又一次，她落入了“命运编织的罗网”，迷失在了这里。

“不能在这倒下……还有很多未竟之事，和【TA】还有一个约定……绝不能在这倒下……”

再度睁开双眼，法比亚纳的景象却在她的眼前浮现……她的对手，她的伙伴，她的家人……正带着温暖的笑意，向她缓步走来。

 

又是鸣式创造的幻境吗？利维亚坦竟认为，她在恐惧着“幸福”？还是说，祂认为自己是在恐惧着某种“不配得的幸福”：一个拥有着如此黑暗力量的人，要如何被他人真正看见、接纳、所爱……

在过去，她或许还会思考这个问题，可现在，她已不再需要那个答案……她只要知道，自己的靶心向谁就好。

她起身，引火，上膛，将枪口对准了面前的“故人”……

“哈哈哈！小姑娘，看来，你已经把自己淬炼得无比锋利了。”

如果这是梦的话，费罗大叔的笑声未免太过真切……但当她看到人们身上被黑潮侵蚀的痕迹时，终于明白：这些曾为她献出了几乎所有频率的人，本该成为利维亚坦眷属的魂灵们，十几年间，依然在抵抗着侵蚀，至死未曾接受“馈赠”……他们被利维亚坦放逐到了黑潮最深层的境界，承受着最深的痛苦与折磨。

她陷入了沉默。这一路上，她有过松懈，有过游移，也许她应该再努力一些，这样她便能更早地掌控这份力量，能够早些回来，也能拯救更多的人……也许……

“猎人，你已经做得很好了。”

“你要抬头挺胸，自由且骄傲地活下去，这是我们一直以来的愿望。”

“你永远也是我们的骄傲。”

人们以出奇统一的笑容回应了她，而母亲的话语，则回答了她长久以来，从未有过机会，也从未敢问出口的疑问。

“但……我的孩子，你知道的，这里不是家。”

“你该起程了。还有人在等你。”

“就像当时揍我一样，对利维亚坦狠狠来上两拳！连带着我们的份——愉快地复仇吧！”

“再见了，安吉尔。这一次，也许是永别了。”

“不要忘记，我们永远在你的身边。”

最后的最后，她看见父亲以一个极为夸张的姿势，向她比出了一个大大的V字。

这个笨蛋老爹——她心中如此笑骂，却明白，父亲的手势意味着什么：不必拥抱，不要回头。既是抚慰，亦是告别。

众灵的身影变得模糊，化为点点星光，为她指明了一瞬的方向……这即是他们出现的理由。尽管他们已无多余力量相赠，但，又一次，她被拯救了。

这就是利维亚坦的诡计，多么可笑——祂本想用黑潮将她拖入无尽黑暗，却帮助她完成了那场未来得及完成的告别。

法比亚纳在她眼前逐渐远去，瓦解，消亡……她也不再是那个小女孩了。她的过去或有美好，但她不会沉溺在那里；她的心中或有柔软，但她必须将自己打磨得更加锋利。

于是，她不再犹豫，转身向黑暗走去。

 

再一次，奇美拉挡在了她的面前。

她从未奢望这头生性暴戾的残象能够通晓人性，更不会与它建立平等友好的情谊，只希望它在自己目标清晰时，不要再惹是生非，四处寻衅。为此，她唯一要做的，就是驯服它。

她已经做好了恶战的准备……可这次，奇美拉却出奇安分，只是一言不发看着她走来，静静地在她的火焰中燃烧——那是属于安吉尔的火焰，是属于她的火焰。

过往的许多谜团，如今终于得到了解答。

“才这点火焰就承受不住了？”

“笑话。你才是，可别死了。我们的狩猎，不会在这里结束。”

“类似的险境，我们不是已经跨越过很多了吗？”

世间不存在无法狩猎的邪魔，鸣式不过是最强的一种……更何况，她并不是孤身一人在战斗。

奇美拉不再言语，让开了道路。而在它身后，是更多的，她所吞噬过的，无数残象的身影。

她曾与它们展开生死搏杀，在无数梦境与它们中再度交锋，只为从它们手中借来力量……但如今……

她无视了它们的存在，从它们面前坦然走过，一条无尽的火路，也于她的脚下逐渐展开。而在这条璀璨火路的两旁，那些曾令万千生灵畏惧的造物也纷然屈膝，如同恭送着自己主人的出征。

它们是在恐惧着另一只远比它们强大的恶魔，还是在恐惧着……另一种同样会令恶魔感到恐惧的存在？

是什么都无所谓——她的力量早已凌驾在它们之上，无需认可，只应服从。

而她，则会用这些罪恶的力量，去猎杀更多的罪恶——正如她儿时立下的小小誓言一样，至死不易。

为她自己，也为那些无法归来的人。为了法比亚纳的悲剧不再重演，也为了她的苦难不再重演……

她的狩猎，永远都不会结束。
    `,
  },
];
const current = ref(0);

function select(index) {
  current.value = index;
  // 将焦点移回当前 tab（便于无障碍与键盘导航）
  const id = `tab-${items[index].id}`;
  const el = document.getElementById(id);
  if (el) el.focus();
}
const storyRef = ref<HTMLElement | null>(null);

function prev() {
  current.value = (current.value - 1 + items.length) % items.length;
  select(current.value);
  storyRef.value.scrollIntoView({ behavior: "smooth", block: "start" });
}

function next() {
  current.value = (current.value + 1) % items.length;
  select(current.value);
  storyRef.value.scrollIntoView({ behavior: "smooth", block: "start" });
}

onMounted(() => {
  if (!reducedMotion) {
    const tl = gsap.timeline({ defaults: { ease: "power3.out" } });
    tl.from(".avatar-card", {
      duration: 0.8,
      y: 18,
      opacity: 0,
      scale: 0.99,
    }).from(
      ".right-col > .hero-panel .name",
      { duration: 0.9, x: 24, opacity: 0 },
      "-=0.45"
    );

    gsap.utils.toArray(".tl-item").forEach((it: any, idx: number) => {
      gsap.from(it.querySelector(".tl-card"), {
        scrollTrigger: {
          trigger: it,
          start: "top 85%",
          toggleActions: "play none none reverse",
        },
        opacity: 0,
        y: 22,
        duration: 0.7,
        delay: idx * 0.06,
      });
    });

    gsap.to(".avatar-card", {
      scale: 1.007,
      duration: 2.8,
      yoyo: true,
      repeat: -1,
      ease: "sine.inOut",
    });
  } else {
    document.documentElement.classList.add("reduced-motion");
  }
});
</script>

<style scoped lang="scss">
$bg-deep: #0a0f14; // 深夜蓝黑底
$deep-2: #0f1c24; // 深蓝黑渐深
$accent-1: #3c9eff; // 冰蓝起点（冷焰）
$accent-2: #ff9a4c; // 炽橙终点（火焰点缀）
$text-main: #e1e8ed; // 主正文浅色
$text-muted: rgba(225, 232, 238, 0.78);
$card-bg: rgba(12, 24, 30, 0.46);
$card-border: rgba(60, 150, 210, 0.06);
$soft-shadow: rgba(3, 10, 14, 0.5);
$inner-glow: rgba(60, 150, 210, 0.03);
$warm-flare: rgba(255, 154, 76, 0.04); // 火焰橙微光点缀

.megumi-page {
  position: relative;
  min-height: 100vh;
  background: linear-gradient(180deg, $bg-deep 0%, $deep-2 72%);
  font-family: "Noto Sans SC", system-ui, -apple-system, "Segoe UI", Roboto,
    Arial;
  color: $text-main;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: clamp(20px, 4vw, 80px);
  box-sizing: border-box;
  padding-top: 60px;

  &.reduced-motion * {
    transition: none !important;
    animation: none !important;
  }

  .container {
    position: relative;
    z-index: 10;
    max-width: 1100px;
    margin: 0 auto;
    padding: clamp(12px, 2vw, 40px);
  }
}

/* ========== HERO 区域 ========== */
.hero {
  position: relative;
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 28px;
  align-items: start;
  padding: 12px;
  margin-bottom: 12px;

  .left-col {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .avatar-card {
    background: linear-gradient(
      180deg,
      rgba(255, 255, 255, 0.01),
      rgba(60, 150, 210, 0.01)
    );
    border-radius: 16px;
    padding: 12px;
    display: grid;
    justify-items: center;
    gap: 8px;
    border: 1px solid $card-border;
    box-shadow: 0 12px 34px $soft-shadow, inset 0 1px 0 $inner-glow;
    cursor: pointer;
    transition: transform 0.28s ease, box-shadow 0.28s ease;
    width: 100%;

    &:hover {
      transform: translateY(-6px);
      box-shadow: 0 22px 60px rgba(3, 10, 14, 0.55),
        inset 0 1px 0 rgba(60, 150, 210, 0.045);
    }
  }

  .avatar-wrap {
    width: 100%;
    display: block;
  }

  .avatar {
    width: 100%;
    height: auto;
    border-radius: 12px;
    display: block;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.36),
      0 0 18px rgba(60, 150, 210, 0.02);
    transition: transform 0.5s ease;
    background-color: rgba(0, 0, 0, 0.04);
  }

  .avatar-card:hover .avatar {
    transform: translateY(-4px) scale(1.01);
  }

  .avatar-meta {
    display: flex;
    gap: 8px;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
  }

  .avatar-badge {
    font-size: 0.9rem;
    color: $text-main;
    background: rgba(0, 0, 0, 0.16);
    padding: 6px 10px;
    border-radius: 999px;
    border: 1px solid rgba(60, 150, 210, 0.045);
    font-weight: 600;
  }

  .right-col {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .hero-panel {
    position: relative;
    z-index: 9;
    padding: 20px;
    border-radius: 14px;
    background: $card-bg;
    backdrop-filter: blur(6px) saturate(0.95);
    border: 1px solid $card-border;
    box-shadow: 0 12px 40px rgba(4, 10, 10, 0.44), inset 0 1px 0 $inner-glow;
  }

  .name {
    font-size: clamp(1.8rem, 3vw, 2.8rem);
    margin: 0;
    font-weight: 900;
    letter-spacing: 1px;
    line-height: 1;
    display: inline-block;
    background: linear-gradient(90deg, $accent-1 0%, $accent-2 60%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
    -webkit-text-stroke: 0.2px rgba(0, 0, 0, 0.18);
    text-shadow: 0 6px 18px rgba(8, 40, 38, 0.06),
      0 2px 6px rgba(60, 150, 210, 0.03);
  }

  .jp {
    font-size: 0.95rem;
    color: $accent-1;
    margin-left: 8px;
    font-weight: 400;
  }

  .subtitle {
    margin: 6px 0 0;
    font-size: 1.1rem;
    color: $accent-1;
    font-weight: 600;
    line-height: 1.4;
  }

  .lead {
    margin: 10px 0 0;
    color: $text-main;
    opacity: 0.95;
    line-height: 1.7;
    max-width: 72ch;
  }
}

/* ========== 通用卡片 ========== */
.card {
  margin-top: 24px;
  background: rgba(8, 20, 18, 0.42);
  border-radius: 14px;
  padding: 24px;
  box-shadow: 0 12px 42px rgba(3, 10, 10, 0.4);
  backdrop-filter: blur(4px);
  color: $text-main;
  border: 1px solid $card-border;
  transition: transform 0.28s ease, box-shadow 0.28s ease;

  &:hover {
    transform: translateY(-8px) scale(1.01);
    box-shadow: 0 25px 70px rgba(3, 10, 10, 0.55);
  }

  h2 {
    margin: 0 0 12px 0;
    font-size: 1.3rem;
    color: $accent-2;
  }

  .card-head {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
  }
}

/* personality 列表样式 */
.personality .traits li {
  padding: 12px 0;
  border-bottom: 1px dashed rgba(60, 150, 210, 0.07);
  font-size: 1rem;
  color: rgba($text-main, 0.92);
}

/* overview 双栏布局 */
.overview .two-col {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
  margin-top: 12px;
}

.overview .text-block {
  flex: 1 1 40%;
  min-width: 240px;
  line-height: 1.6;
  color: rgba($text-main, 0.96);
}

/* special-section：三大主题区公共布局 */
.special-section {
  position: relative;
  overflow: hidden;

  .content {
    display: flex;
    gap: 24px;
    align-items: center;
    margin-top: 16px;
  }

  .img-area {
    flex: 0 0 200px;

    img {
      width: 100%;
      height: auto;
      border-radius: 12px;
      box-shadow: 0 12px 36px rgba(4, 10, 10, 0.36),
        0 0 12px rgba(60, 150, 210, 0.02);
      border: 1px solid rgba(60, 150, 210, 0.03);
    }
  }

  .text-block {
    flex: 1;
    line-height: 1.6;
    color: rgba($text-main, 0.95);
  }
}

/* ll-stories */
.ll-stories {
  .card {
    width: min(1200px, 100%);
    border-radius: 12px;
    box-shadow: 0 8px 30px rgba(6, 6, 6, 0.5),
      inset 0 1px 0 rgba(60, 150, 210, 0.02);
    color: $text-main;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    background: linear-gradient(
      180deg,
      rgba(8, 24, 22, 0.12),
      rgba(8, 20, 18, 0.06)
    );
  }

  .card-head {
    padding: 14px 16px;
    border-bottom: 1px solid rgba(60, 150, 210, 0.03);
    display: flex;
    flex-direction: column;
    gap: 12px;

    .card-title {
      font-size: 24px;
      font-weight: 700;
      color: $accent-1;
      letter-spacing: 0.6px;
    }
  }

  .card-body {
    padding: 18px 16px;
    min-height: 160px;
    position: relative;
    background: linear-gradient(
      180deg,
      rgba(0, 0, 0, 0),
      rgba(8, 12, 10, 0.02)
    );
  }

  .story {
    color: rgba($text-main, 0.96);

    .story-head {
      font-size: 18px;
      color: $accent-2;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .story-content {
      line-height: 1.7;
      color: rgba($text-main, 0.92);
      white-space: pre-wrap;
    }
  }

  .card-foot {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 8px;
    padding: 10px 14px;
    border-top: 1px solid rgba(60, 150, 210, 0.02);
    background: linear-gradient(
      180deg,
      rgba(0, 0, 0, 0.02),
      rgba(0, 0, 0, 0.04)
    );

    .nav-btn {
      background: transparent;
      border: 1px solid rgba(60, 150, 210, 0.06);
      color: $accent-2;
      padding: 6px 10px;
      border-radius: 6px;
      cursor: pointer;
      transition: background 180ms ease;
      &:hover {
        background: rgba(255, 154, 76, 0.06);
      }
    }

    .pager {
      color: rgba($text-main, 0.72);
      font-size: 13px;
      font-weight: 600;
    }
  }

  /* 切换动画：淡入并轻微上移 */
  .fade-slide-enter-active,
  .fade-slide-leave-active {
    transition: all 320ms cubic-bezier(0.2, 0.9, 0.2, 1);
  }

  .fade-slide-enter-from {
    opacity: 0;
    transform: translateY(6px);
  }

  .fade-slide-enter-to {
    opacity: 1;
    transform: translateY(0);
  }

  .fade-slide-leave-from {
    opacity: 1;
    transform: translateY(0);
  }

  .fade-slide-leave-to {
    opacity: 0;
    transform: translateY(-6px);
  }
}

/* timeline 样式（蓝橙火焰触感） */
.timeline {
  position: relative;

  .tl-wrap {
    position: relative;
    padding: 24px 12px 12px 96px;
  }

  .vl {
    position: absolute;
    left: 80px;
    top: 32px;
    bottom: 20px;
    width: 4px;
    border-radius: 6px;
    background: linear-gradient(
      180deg,
      rgba($accent-2, 0.15),
      rgba($accent-1, 0.12)
    );
    box-shadow: 0 6px 18px rgba(60, 150, 210, 0.06),
      inset 0 0 10px rgba(60, 150, 210, 0.02);
    opacity: 0.95;
  }

  .tl-list {
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .tl-item {
    position: relative;
    display: flex;
    gap: 18px;
    align-items: flex-start;
    margin: 20px 0;
    transition: transform 0.28s ease, box-shadow 0.28s ease;
  }

  .tl-card {
    background: rgba(8, 20, 18, 0.36);
    border-radius: 12px;
    padding: 16px 20px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
    width: calc(100% - 130px);
    border-left: 4px solid transparent;
    transition: transform 0.28s ease, box-shadow 0.28s ease,
      border-color 0.28s ease;
    position: relative;
    z-index: 2;
  }

  .tl-item:hover .tl-card,
  .tl-item:focus-within .tl-card {
    transform: translateY(-8px);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.35);
    border-left-color: rgba(255, 154, 76, 0.18);
  }

  .tl-title {
    margin: 0 0 6px 0;
    font-size: 1.1rem;
    color: $accent-1;
    display: flex;
    align-items: baseline;
    gap: 8px;
  }

  .tl-desc {
    margin: 0;
    color: rgba($text-main, 0.92);
    white-space: pre-wrap;
  }
}

/* 小屏响应式调整 */
@media (max-width: 980px) {
  .hero {
    grid-template-columns: 1fr;
    gap: 18px;
    padding: 8px;
  }

  .avatar-card {
    width: 140px;
    padding: 8px;
  }

  .hero-panel {
    padding: 14px;
  }

  .name {
    font-size: 1.8rem;
  }

  .subtitle {
    font-size: 1rem;
  }

  .lead {
    font-size: 0.95rem;
  }

  .card {
    padding: 18px;
    border-radius: 12px;
  }

  .overview .two-col {
    flex-direction: column;
  }

  .special-section .content {
    flex-direction: column;
  }

  .ll-stories {
    .card {
      border-radius: 10px;
    }

    .card-head {
      padding: 12px 12px;
    }

    .card-body {
      padding: 14px 12px;
      min-height: 180px;
    }

    .card-foot {
      padding: 8px 12px;
    }
  }

  .timeline {
    overflow: visible;
  }

  .timeline .tl-wrap {
    padding-left: 14px !important;
    padding-right: 14px;
    min-height: 0;
  }

  .timeline .vl {
    display: none !important;
  }

  .timeline .tl-list {
    overflow: visible;
  }

  .timeline .tl-item {
    display: block !important;
    margin: 14px 0 !important;
    width: 100%;
  }

  .timeline .tl-card {
    width: 100% !important;
    padding: 14px !important;
    border-left: 0 !important;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
    transform: none !important;
  }
}
</style>

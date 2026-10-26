<script setup>
const navigation = [
  { label: '首页', href: '#top' },
  { label: '普查动态', href: '#news' },
  { label: '政策法规', href: '#services' },
  { label: '普查知识', href: '#census' },
  { label: '数据发布', href: '#data' },
  { label: '下载中心', href: '#services' },
  { label: '互动交流', href: '#services' },
]

const censusTopics = [
  { icon: '▤', title: '普查方案', description: '了解普查对象、内容、时间和组织实施安排。' },
  { icon: '⌁', title: '普查登记', description: '规范登记流程，确保源头数据真实准确。' },
  { icon: '♧', title: '数据质量', description: '全过程质量控制，守护农业统计生命线。' },
  { icon: '◉', title: '成果应用', description: '以普查数据服务“三农”决策和发展。' },
]

const statistics = [
  { icon: '🌿', value: '31', unit: '个', label: '省（区、市）共同参与' },
  { icon: '🏡', value: '2800+', unit: '个', label: '县级普查机构暖心服务' },
  { icon: '🌾', value: '千万级', unit: '', label: '农业经营主体相伴同行' },
  { icon: '♡', value: '100%', unit: '', label: '守护每一份数据安心' },
]

const highlights = [
  {
    icon: '🌱',
    title: '产业更有活力',
    description: '现代农业、特色种养和农产品加工协同发展，让好收成有了更广阔的市场。',
  },
  {
    icon: '☀️',
    title: '乡村更有温度',
    description: '人居环境持续改善，公共服务不断完善，共同绘就宜居宜业和美乡村新画卷。',
  },
]

const news = [
  { day: '22', date: '2026.10', title: '全国农业普查办公室召开第四次全国农业普查工作推进会' },
  { day: '18', date: '2026.10', title: '各地稳步推进农业普查综合试点和业务培训工作' },
  { day: '09', date: '2026.10', title: '第四次全国农业普查宣传月活动正式启动' },
]

const services = ['普查员登录入口', '普查资料下载', '常见问题解答']
</script>

<template>
  <div id="top">
    <div class="topbar">
      <div class="wrap topbar-inner">
        <span>国家统计局 · 农业农村部</span>
        <span>今天是 2026年10月22日　|　无障碍浏览　|　简体中文</span>
      </div>
    </div>

    <header class="header">
      <div class="wrap header-inner">
        <div class="brand">
          <div class="seal" aria-label="国徽标识">★</div>
          <div>
            <div class="brand-title">第四次全国农业普查</div>
            <div class="brand-sub">THE FOURTH NATIONAL AGRICULTURAL CENSUS</div>
          </div>
        </div>
        <div class="hotline">全国统一咨询热线 <b>12345</b></div>
      </div>
    </header>

    <nav class="nav" aria-label="主导航">
      <div class="wrap nav-inner">
        <a
          v-for="(item, index) in navigation"
          :key="item.label"
          :href="item.href"
          :class="{ active: index === 0 }"
        >
          {{ item.label }}
        </a>
      </div>
    </nav>

    <section class="hero">
      <div class="wrap hero-content">
        <div class="kicker">摸清“三农”家底　服务乡村振兴</div>
        <h1>第四次全国农业普查</h1>
        <p>全面查清新时代我国“三农”发展变化，准确反映农业农村现代化进程，为加快建设农业强国提供坚实统计支撑。</p>
        <a class="hero-btn" href="#census">了解农业普查工作 <span aria-hidden="true">→</span></a>
      </div>
    </section>

    <div class="notice wrap">
      <span class="notice-label">◆ 通知公告</span>
      <span class="notice-text">国务院关于开展第四次全国农业普查的通知</span>
      <a class="more" href="#news">查看更多　›</a>
    </div>

    <main>
      <section id="census" class="section wrap">
        <h2 class="section-title">普查工作</h2>
        <p class="section-desc">依法普查、科学普查、为民普查</p>
        <div class="cards">
          <article v-for="topic in censusTopics" :key="topic.title" class="card">
            <div class="card-icon" aria-hidden="true">{{ topic.icon }}</div>
            <h3>{{ topic.title }}</h3>
            <p>{{ topic.description }}</p>
          </article>
        </div>
      </section>

      <section id="data" class="data">
        <div class="wrap data-content">
          <h2 class="section-title">农业发展概览</h2>
          <p class="section-desc">一组组数字，记录田野里的耕耘与丰收　·　数据以最终普查公报为准</p>
          <div class="stats">
            <article v-for="stat in statistics" :key="stat.label" class="stat">
              <div class="stat-icon" aria-hidden="true">{{ stat.icon }}</div>
              <div>
                <span class="num">{{ stat.value }}</span>
                <span v-if="stat.unit" class="unit">{{ stat.unit }}</span>
              </div>
              <div class="stat-label">{{ stat.label }}</div>
            </article>
          </div>

          <div class="highlights">
            <article class="field-note">
              <div class="eyebrow">田 野 新 景</div>
              <h3>以普查丈量乡村脉动，以数据描绘振兴图景。</h3>
              <p>从清晨的第一缕炊烟，到丰收时的满仓喜悦，普查记录着乡村发展的每一步。</p>
            </article>
            <article v-for="highlight in highlights" :key="highlight.title" class="highlight">
              <i aria-hidden="true">{{ highlight.icon }}</i>
              <h3>{{ highlight.title }}</h3>
              <p>{{ highlight.description }}</p>
            </article>
          </div>
        </div>
      </section>

      <section class="section wrap bottom">
        <div id="news" class="panel">
          <div class="panel-head">
            <h2>工作动态</h2>
            <a class="more" href="#news">更多　›</a>
          </div>
          <article v-for="item in news" :key="item.day" class="news">
            <div class="date">{{ item.day }}<small>{{ item.date }}</small></div>
            <div class="news-title">{{ item.title }}</div>
          </article>
        </div>

        <div id="services" class="panel">
          <div class="panel-head"><h2>普查服务</h2></div>
          <a v-for="service in services" :key="service" class="news service-link" href="#services">
            <span aria-hidden="true">▸</span>
            <span class="news-title">{{ service }}</span>
          </a>
        </div>
      </section>
    </main>

    <footer class="footer">
      <strong>第四次全国农业普查领导小组办公室</strong><br />
      主办单位：国家统计局　农业农村部　|　网站标识码：bmxxxxxx　|　京ICP备xxxxxx号
    </footer>
  </div>
</template>

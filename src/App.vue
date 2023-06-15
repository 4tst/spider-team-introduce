<template>
  <div id="container" class="relative h-screen w-screen overflow-y-auto grid items-center">
    <div v-show='showWeChat' class="w-28 absolute right-0 top-0 bottom-0 mx-auto">
      <n-image :src="WeChat"></n-image>
    </div>
    <div class="w-4/5 mx-auto my-auto">
      <div class="text-center">
        <n-button size="small" @click="showWeChat = !showWeChat" type="error">点击加客服微信</n-button>
      </div>
      <n-grid :cols="2" :x-gap="6">
        <n-gi>
          <n-alert title="【网络爬虫 数据采集】" type="info" :show-icon="false">
            <div v-for="line, i in lines2" :key="i">{{ line }}</div>
          </n-alert>
          <n-alert type="error" :show-icon="false">PS：只爬取内容合法公开数据</n-alert>
        </n-gi>
        <n-gi>
          <n-alert title="【专业团队 保质保量】" type="info" :show-icon="false">
            <div v-for="line, i in lines" :key="i">{{ line }}</div>
            <div class="w-28 absolute right-0 top-0 bottom-0">
              <n-image :src="Wait"></n-image>
            </div>
          </n-alert>
          <n-alert type="error" :show-icon="false">不满意，全额退😭😭</n-alert>
        </n-gi>

      </n-grid>
      <n-alert class="relative" title="我们能为您做些什么？" type="info" :show-icon="false">
        <div v-for="line, i in features" :key="i">{{ line }}</div>
        <div class="absolute top-0 right-0 bottom-0 grid items-center">
          <n-image :src="Skills" width="200"></n-image>
        </div>
      </n-alert>
      <n-alert type="error" :show-icon="false">以上场景仅为示例，只要您有需求，我们均可按需定制！</n-alert>
      <n-alert :title="sites[0]" type="info" :show-icon="false">
        <n-grid :cols="2">
          <n-gi>
            <strong>国内：</strong>
            <div v-for="line, i in inner" :key="i">{{ line }}</div>
          </n-gi>
          <n-gi>
            <strong>国外：</strong>
            <div v-for="line, i in outer" :key="i">{{ line }}</div>
          </n-gi>
        </n-grid>
      </n-alert>
    </div>
  </div>
</template>

<script setup lang="ts">
import Skills from '@/assets/images/skills.jpg';
import Wait from '@/assets/images/wait4customer.jpg';
import WeChat from '@/assets/images/wechat.jpg';

useHead({
  title: "专业爬虫、数据采集",
})

const showWeChat = ref(false)

const lines = [
  "专业爬虫队伍  数据质量有保障。",
  "抖音 快手 淘宝 京东 知乎 哔哩哔哩 …等等", "现️软件可以爬数据 最快半小时起交付",
  "网页爬虫 ｜ app爬虫 ｜ 数据分析 ｜办公自动化 ｜情感分析 ｜ 软件定制",
]
const lines2 = [
  "轻松掌握公开网络信息 精准爬虫服务为您的事业加油",
  "网页数据爬虫，有经验，有实力",
  "不用问在不在，直接带需求咨询哦；价格可协商，原则上依据爬取难度，数据数量定价哦",
  "依据您的需求，量身定制属于您的数据",
]

const features = [
  "① 因为某些需求，需要到某个网站复制粘贴很多网页文章，任务数量是 10000+ 篇 … 爬虫可以帮到您！ ",
  "② 一万个表格里，从中提取特定的数据，然后进行计算得到相对应的结果 … 爬虫可以帮到您！ ",
  "③ 因为某些用途，您需要重复打开某个软件，点击某个按钮 lw 次 … 爬虫可以帮到您！",
  "④ 需要在公司某个系统里，每天录入大量的数据，头晕眼花 … 爬虫可以帮到您！ ",
  "⑤ 因为某些需求，需要统计几万份表格或文件里的关键数据，简直无从下手 … 爬虫可以帮到您！",

]
const sites = [
  "接单数年，擅各类python爬虫、jupyter可视化、selenium、playwright自动化、数据分析，环境部署均可接／可带／可指导，以下是近来部分爬虫项目："
]
const inner = [
  "0️⃣ d音", "1️⃣ 某东", "2️⃣ 某宝", "3️⃣ 人民r报",
  "4️⃣ 猫👀", "5️⃣ 豆瓣", "6️⃣ 时光网", "7️⃣ 知网",
  "8️⃣ w博", "9️⃣ 某乎",
  "1️⃣0️⃣ 巨潮", "1️⃣1️⃣ 微医", "1️⃣2️⃣ 头条、新浪、纵横、红袖等",
]
const outer = [
  "0️⃣ amazon", "1️⃣ shoppe东南亚最大电商网站",
  "2️⃣ booking 全球", "3️⃣ ozon", "4️⃣ vivino",
  "5️⃣ Trip Advisor 国外大众点评", "6️⃣ houzz 家具设计",
  "7️⃣ omim 人类基因数据库", "8️⃣ takealot 南非电商",
  "9️⃣ tunebat 国外音乐网站", "1️⃣0️⃣ proquest 学术数据库",
  "1️⃣1️⃣ 大英museum 大都会 museum", "1️⃣2️⃣ patentscope 专利数据库"
]
</script>

<style scoped>
#container {
  background-color: aliceblue;
  background-image: url('@/assets/images/code.jpg');
  background-repeat: repeat;
  /* background: transparent; */
  backdrop-filter: blur(8px);
}

:deep(.n-alert) {
  /* background: transparent; */
  margin: 10px;
}
</style>
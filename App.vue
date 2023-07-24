<script>
import logoHeader from '@/assets/images/logo-dark.svg?url'
import logoFooter from '@/assets/images/logo-light.svg?url'

import imgHeroMB from '@/assets/images/image-hero-mobile.png?url'
import imgHeroTB from '@/assets/images/image-hero-tablet.png?url'
import imgHeroDT from '@/assets/images/image-hero-desktop.png?url'

import iconAnimation from '@/assets/images/icon-animation.svg?url'
import iconDesign from '@/assets/images/icon-design.svg?url'
import iconPhotography from '@/assets/images/icon-photography.svg?url'
import iconCrypto from '@/assets/images/icon-crypto.svg?url'
import iconBusiness from '@/assets/images/icon-business.svg?url'

export default {
  data() {
    return {
      logoHeader,
      logoFooter,
      imgHeroMB,
      imgHeroTB,
      imgHeroDT,
      isFooterBtnHovered: false,
      data: [
        {
          icon: iconAnimation,
          header: 'Animation',
          main: 'Learn the latest animation techniques to create stunning motion design and captivate your audience.'
        },
        {
          icon: iconDesign,
          header: 'Design',
          main: 'Create beautiful, usable interfaces to help shape the future of how the web looks.'
        },
        {
          icon: iconPhotography,
          header: 'Photography',
          main: 'Explore critical fundamentals like lighting, composition, and focus to capture exceptional photos.'
        },
        {
          icon: iconCrypto,
          header: 'Crypto',
          main: 'All you need to know to get started investing in crypto. Go from beginner to advanced with this 54 hour course.'
        },
        {
          icon: iconBusiness,
          header: 'Business',
          main: 'A step-by-step playbook to help you start, scale, and sustain your business without outside investment.'
        },
      ]
    }
  },
  computed: {
    getHoverState() {
      return this.isFooterBtnHovered ? 'bg-opacity-50' : 'bg-opacity-0'
    }
  }
}
</script>
<template>
  <body class=" flex flex-col items-center text-neo-dark-blue font-jakarta">
    <header class=" flex flex-col gap-9 w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] overflow-hidden">
      <nav class=" flex justify-between items-center px-4 TB:px-10 DT:px-[165px] pt-4 TB:pt-6">
        <img class=" h-6 DT:h-8 select-none" :src="logoHeader" alt="logoHeader" draggable="false">
        <button
          class=" w-[140px] DT:w-[167px] h-12 DT:h-14 bg-neo-dark-blue hover:bg-neo-light-blue text-neo-white text-[16px] DT:text-[18px] leading-7 DT:leading-[28px] font-bold rounded-[28px] select-none">
          Get Started</button>
      </nav>
      <div class=" relative flex flex-col TB:flex-row gap-14 TB:gap-0 TB:w-full TB:h-[525px] DT:h-[720px]">
        <div
          class=" flex flex-col TB:self-start TB:w-[58%] DT:w-[44%] px-4 TB:pl-10 DT:pl-[165px] TB:pr-0 TB:pt-[50px] DT:pt-[150px]">
          <h1 class=" mb-6 DT:mb-7 text-[40px] DT:text-[56px] leading-[50px] DT:leading-[71px] font-extrabold">
            Maximize skill, minimize budget</h1>
          <p
            class=" mb-6 DT:mb-10 DT:pr-8 text-neo-gray text-[16px] DT:text-[18px] leading-[26px] DT:leading-[28px] font-medium">
            Our modern courses across a range of in-demand skills will give you the
            knowledge you need to live the life you want.
          </p>
          <button
            class=" w-[167px] h-14 bg-gradient-to-b from-neo-gradient-ab to-neo-gradient-aa hover:opacity-60 text-neo-white text-[16px] leading-[26px] DT:leading-[28px] font-bold rounded-[32px] select-none">
            Get Started
          </button>
        </div>
        <img class=" TB:hidden scale-[1.15] select-none" :src="imgHeroMB" alt="imgHero" draggable="false">
        <img class=" absolute top-[-205px] right-[-300px] hidden TB:block DT:hidden select-none pointer-events-none"
          :src="imgHeroTB" alt="imgHero" draggable="false">
        <img class=" absolute top-[-265px] right-[-330px] hidden DT:block select-none pointer-events-none"
          :src="imgHeroDT" alt="imgHero" draggable="false">
      </div>
    </header>
    <main
      class=" grid grid-cols-1 TB:grid-cols-2 DT:grid-cols-3 gap-4 TB:gap-x-[10px] DT:gap-x-7 TB:gap-y-14 w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] px-4 TB:px-10 DT:px-[165px] pb-20 TB:pb-[86px] DT:pb-[140px] bg-gradient-to-b from-neo-white to-neo-gradient-main">
      <div
        class=" flex items-center TB:items-start TB:self-end w-full h-[120px] TB:h-[259px] DT:h-[322px] px-7 DT:px-8 TB:pt-14 DT:pt-16 bg-gradient-to-b from-neo-gradient-ab to-neo-gradient-aa text-neo-white text-[24px] DT:text-[32px] leading-8 DT:leading-10 font-extrabold rounded-[10px]">
        Check out our most popular courses!
      </div>
      <article v-for="(item, index) in data">
        <img class=" -mb-7 pl-7 TB:pl-8 select-none" :src="item.icon" :alt="`icon ${index + 1}`" draggable="false">
        <div
          class=" flex flex-col items-start justify-between h-[259px] DT:h-[322px] px-7 TB:pl-8 TB:pr-5 DT:px-8 pt-14 pb-8 DT:pb-10 bg-neo-white rounded-[10px]">
          <div class=" flex flex-col gap-4 DT:gap-6">
            <h4 class=" text-[20px] DT:text-[24px] leading-[25px] DT:leading-[30px] font-extrabold">
              {{ item.header }}</h4>
            <p class=" text-neo-gray text-[16px] DT:text-[18px] leading-[26px] DT:leading-[28px] font-medium">
              {{ item.main }}
            </p>
          </div>
          <button class=" text-neo-pink hover:text-neo-opaque-pink text-[18px] leading-7 font-bold select-none">
            Get Started
          </button>
        </div>
      </article>
    </main>
    <footer
      class=" flex justify-between items-center w-full max-w-[425px] TB:max-w-[1024px] DT:max-w-[1920px] px-4 TB:px-10 DT:px-[165px] py-9 DT:py-8 bg-neo-dark-blue">
      <img class=" h-6 DT:h-8 select-none" :src="logoFooter" alt="logoFooter" draggable="false">
      <button @mouseenter="isFooterBtnHovered = true" @mouseleave="isFooterBtnHovered = false"
        class=" relative w-[140px] DT:w-[167px] h-12 DT:h-14 bg-gradient-to-b from-neo-gradient-ba to-neo-gradient-bb text-neo-white text-[16px] DT:text-[18px] leading-7 DT:leading-[28px] font-bold rounded-[28px] overflow-hidden select-none">
        <div :class="` absolute top-0 w-full h-full bg-neo-white ${getHoverState}`"></div>
        Get Started
      </button>
    </footer>
  </body>
</template>
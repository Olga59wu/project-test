<template>
  <main class="container max-w-full py-12 px-14">
    <div class="flex w-full h-full login-wrap">
      <div class="w-[60vw] left-block">
        <img src="@/assets/imgs/front_page_img.svg" alt="front_img" class="aspect-auto h-full">
      </div>
      <div class="flex w-[40vw] right-block">
        <div class="flex flex-col justify-between flex-1 px-6 pt-12 ">
          <div class="logo-block">
            <img class="mx-auto w-400px h-46px" src="@/assets/imgs/csi-logo.svg" alt="csi logo">
          </div>
          <div class=" relative w-4/5 px-8 py-8 mx-auto my-16 border rounded-3xl h-full flex justify-center align-middle items-center">
            <p class=" absolute top-8 left-1/2 transform -translate-x-1/2 text-center text-2xl font-semibold">平台</p>
            <GoogleLogin />
          </div>
          <footer>
            <div class="flex justify-center mb-4">
              <p class="flex items-center justify-center mr-6 font-normal">
                <span class="text-lg"><i class="mr-3 icon-call" /></span>
                0800-001-568
              </p>
              <p class="flex items-center justify-center font-normal">
                <span class="text-lg"><i class="mr-3 icon-mail" /></span>
                csi_service@ch-si.com.tw
              </p>
            </div>
            <div class="flex items-baseline justify-center flex-wrap">
              <p class="flex items-center justify-center mr-3 font-normal ">
                <span class="text-lg"><i class="mr-3 icon-location-on" /></span>
                總公司 : 台北市大安區金山南路二段52號3樓
              </p>
              <p>高雄 : 高雄市苓雅區苓南路2號13樓</p>
            </div>
            <div class="p-6 text-center">
              <span>{{ copyRightStr }}</span>
            </div>
          </footer>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import moment from 'moment'
import GoogleLogin from '@/components/TheGoogleLogin.vue'

const copyRightStr = ref('')

onMounted(() => {
  copyRightStr.value = `© ${moment().format('YYYY')} CSI 中華系統整合. All rights reserved.`
})

</script>


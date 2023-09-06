<template>
  <GoogleLogin :callback="callback1" popup-type="TOKEN">
    <button class=" font-google px-4 py-2 border flex gap-2 text-sm border-slate-200 rounded text-slate-700 hover:border-slate-400 hover:text-slate-900 hover:shadow transition duration-150">
      <img
        class="w-5 h-5"
        src="@/assets/googleLogo.svg"
        loading="lazy"
        alt="google logo"
      >
      <!-- https://www.svgrepo.com/show/475656/google-color.svg -->
      <!-- <span>使用 Google 帳戶登入</span> -->
      <span>Sign in with Google</span>
    </button>
  </GoogleLogin>
</template>
<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
const router = useRouter()
const accessToken = ref()
const callback1 = (res) => {
  accessToken.value = res.access_token
  console.log('accessToken:', accessToken.value)
  router.push('/home')
}
</script>

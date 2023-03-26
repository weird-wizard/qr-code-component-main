<script setup lang="ts">
  import { onMounted, ref, Ref } from 'vue';

  let title: Ref<string> = ref('Improve your front-end skills by building projects')
  let desc: Ref<string> = ref('Scan the QR code to visit Frontend Mentor and take your coding skills to the next level.')
  let imageSrc = ref('')

  const loadImage = async () => {
    const image = await import('./assets/image-qr-code.png')
    imageSrc.value = image.default
  }

  onMounted(() => {
    loadImage()
  })
  
</script>

<template>
  <div class="container">
    <div class="component">
      <img :src="imageSrc" alt="QR-CODE">
      <div class="title">
        {{ title }}
      </div>
      <div class="desc">
        {{ desc }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: var(--LightGray);
}

.component {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 335px;
  padding: .16rem;
  background-color: var(--White);
  border-radius: .18rem;
  box-shadow: 0 0 .8rem rgba(0, 0, 0, .15);
}

.component img {
  width: 100%;
  margin-bottom: .3rem;
  border-radius: .1rem;
  -webkit-user-drag: none;
  font-size: .15rem;
}

.component .title {
  font-size: .22rem;
  font-weight: 700;
  text-align: center;
  margin-bottom: .25rem;
  color: var(--DarkBlue);
}
.component .desc {
  font-size: .15rem;
  text-align: center;
  color: var(--GrayishBlue);
  margin-bottom: .35rem;
}

</style>

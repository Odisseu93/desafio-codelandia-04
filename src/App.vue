<script setup lang="ts">
import BackgroundImage from './components/BackgroundImage.vue';
import LoginForm from './components/form/LoginForm.vue';
import H1 from './components/typography/LargeText.vue'
</script>

<template>
  <main class="main">
      <BackgroundImage />
    <div class="content">
      <p class="greetings">Bem vindo de volta</p>
      <H1 aligment="center">Faça login na sua conta</H1>
      <LoginForm/>
      <p class="register">Não tem uma conta? <a href="" target="_blank" rel="noopener noreferrer">Cadastre-se</a></p>
    </div>
  </main>
</template>

<style lang="scss">
.bg-image {
  margin-top: 2rem;
}

.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  
  width: clamp(1099px, 70%, 1440px);

  margin-inline: auto ;
  margin-block: auto;

  .greetings {
    line-height: 2rem;
  }

  @media(min-width: 1099px) {
    flex-direction: row;;
  }
}

.content {
  padding-top: 2rem;
}

.register {
  padding-top: 10rem;
  display: flex;
  justify-content: center;
  gap: .5rem;
  width: 100%;
}
</style>

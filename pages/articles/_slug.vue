<template>
  <section class="container">
    <div>
      <nuxt-link to="/articles/" class="button--grey">ブログ一覧へ戻る</nuxt-link>
      <h1 class="title">タイトル</h1>
      <div class="text">
        本文
      </div>
    </div>
  </section>
</template>

<script>
export default {
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  text-align: left;
}

.title {
  font-size: 30px;
}
</style>

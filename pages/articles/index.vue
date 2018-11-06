<template>
  <section class="container">
    <div>
      <h1>記事一覧</h1>
      <nuxt-link to="/" class="button--grey">トップへ戻る</nuxt-link>
      <div class="article-list">
        <ul>
          <li>
            <div class="article-image"></div>
            <div class="title">
              <nuxt-link :to="{ name: 'articles-slug', params: { slug: 'test' }}">タイトル</nuxt-link>
            </div>
          </li>
        </ul>
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
  align-items: center;
  text-align: center;
}

.article-list ul {
  padding: 0;
  margin: 0;
  list-style: none;
  display: flex;
  justify-content: space-between;
  flex-direction: row;
  flex-wrap: wrap;
}

.article-list li {
  border: 1px solid #ccc;
  margin: 20px;
  padding: 20px;
}
</style>
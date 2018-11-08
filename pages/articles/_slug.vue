<template>
  <section id="detail" class="container">
    <div>
      <nuxt-link to="/articles/" class="button--grey">ブログ一覧へ戻る</nuxt-link>
      <div class="title">
        <h1>{{ currentPost.fields.title }}</h1>
        <p>公開日：{{ currentPost.fields.publishDate }}</p>
      </div>
      <div class="text">
        {{ currentPost.fields.mainText }}
      </div>
    </div>
  </section>
</template>

<script>
// contentfulの宣言
import { createClient } from '~/plugins/contentful.js';
// 設定情報の取得
const client = createClient();

export default {
  // 変数の宣言
  data() {
    return {
      allPosts: [],
      currentPost: [],
    };
  },
  // データの取得(非同期)
  asyncData({ env, params }) {
    return client
      .getEntries({
        content_type: env.CTF_BLOG_ID,
      })
      .then((entries) => {
        const posts = entries.items;
        const current = posts.filter(item => item.fields._slug == params._slug);
        return {
          allPosts: posts,
          currentPost: current[0],
        };
      })
      .catch(console.error);
  },
};
</script>

<style lang="css" scoped>
@import "~/assets/style.css";
</style>

<template>
  <article>
   
    <h1>{{ article.title }}</h1>
    <p>{{ article.description }}</p>
     <AppSearchInput />
    <img :src="article.img" :alt="article.alt" />
    <nav>
      <ul>
        <li
          v-for="link of article.toc"
          :key="link.id"
          :class="{ margin1: link.depth === 2, margin2: link.depth === 3 }"
        >
          <NuxtLink :to="`#${link.id}`">{{
            link.text + " " + link.depth
          }}</NuxtLink>
        </li>
      </ul>
    </nav>
    <nuxt-content :document="article" />
    <p>Post last updated: {{ formatDate(article.updatedAt) }}</p>
    <author :author="article.author" />
     <prev-next :prev="prev" :next="next" />
  </article>
</template>


<script>
export default {
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    },
  },
  async asyncData({ $content, params }) {
    const article = await $content("articles", params.slug).fetch();
     const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()
    return { article, prev, next };
  },
};
</script>
<style>
h1 {
  font-weight: bold;
  font-size: 28px;
  color: rgba(244, 56, 124, 0.85);
}
.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.nuxt-content p {
  margin-bottom: 20px;
}
.icon.icon-link {
  background-image: url("~assets/svg/icon-book.svg");
  display: inline-block;
  width: 20px;
  height: 20px;
  background-size: 20px 20px;
}
.margin1 {
  margin-left: 1rem;
}
.margin2 {
  margin-left: 3rem;
}
</style>
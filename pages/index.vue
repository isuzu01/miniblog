<template>
  <div class="container">
    <AboutMe />
    <div class="content">
      <main>
        <ArticleCard 
          v-for="article in articles"
          :key="article.slug"
        />
      </main>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      articles: [1, 2, 3, 4]
    }
  }
}
</script>

<style lang="scss">
.container {
 margin: auto;

}
.container .content {
  margin: 40px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  main {
  /*  @apply max-w-5xl grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6;*/
    display: grid;
    gap: 15px;
    grid-template-columns: repeat(3, auto);
    justify-items: center;
    width: 70%;

  }
}
</style>

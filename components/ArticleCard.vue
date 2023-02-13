
import { title } from 'process';

<template>
  <div class="article-card">
    <h3>{{ title }}</h3>
    <div class="author">
      <p>Por {{ author }}</p>
      <small>Fecha de pubkicación: {{ date }}</small>
    </div>
    <figure>
      <img :src="cover" alt="cover">
    </figure>
    <p>{{ description }}</p>
    <div class="actions">
      <a class="btn" :href="slug">Ir al post</a>
    </div>
  </div>
</template>

<script>
  export default{
    name: 'ArticleCard',
    props: {
      slug: {
        type: String,
        default: '',
      },
      title: {
        type: String,
        default: '',
      },
      author: {
        type: String,
        default: '',
      },
      date: {
        type: Date,
        default: '',
      },
      cover: {
        type: String,
        default: '',
      },
      description: {
        type: String,
        default: '',
      }
    }
  }
</script>

<style lang="scss" scoped>
  .article-card {
    display: block;
    background: white;
    padding: 40px;
    border: solid rgb(186, 186, 186) 1px;
    border-radius: 10px;
    h3 {
      font-weight: bold;
      font-size: 2rem;
    }
    div.author {
      margin: 2 auto;
      p {
        margin: 0;
      }
      small {

      }
    }
    figure {
      img {
        width: 100%;
      }
    }
    p {
      margin: 4px auto;
      font-family: sans-serif;
    }
    div.actions {
      display: flex;
      gap: 2;
      .btn {
        width: 100%;
        text-align: center;
        border-radius: 25px;
        padding: 5px 10px;
        background-color: rgba(128, 128, 128, 0.355);
        &:hover {
          background-color: rgba(128, 128, 128, 0.631);
        }
      }
    }
  }
</style>

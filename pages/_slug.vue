<template>
  <div class="box">
    <article class="post">
      <h1>{{ post.title }}</h1>
      <div class="author">
        <p>{{ post.author }}</p>
        <small>Fecha de publlicaclón: {{ post.updated }}</small>
      </div>
      <p>{{ post.description }}</p>
      <figure>
        <img :src="post.cover" :alt="post.cover">
        <figcaption>Portada - {{ post.title }}</figcaption>
      </figure>
      <VueMarkdown class="markdown">{{ post.content }}</VueMarkdown>
    </article>
  </div>
</template>

<script>
import VueMarkdown from 'vue-markdown'
export default {
  name: 'ArticlePage',
  comments: {
    VueMarkdown,
  },
  data() {
    return {
      post: {
        slug: 'mi-primer-post',
        title: 'Mi primer post',
        author: 'Jhuli Trujillo',
        update: '13/02/23',
        description: 'Loren ipsum dolor sit amet',
        cover: 'https://via.placeholder.com/1024x420',
        content: '# Title/n/n## Second title/n/nLorem ipsum dolor dit amet'
      }
    }
  },
  head() {
    return {
      title: this.post?.title,
      meta: [{ name: 'description', content: this.post?.description || '' }]
    }
  }
} 
</script>

<style lang="scss">
.box {
  height: 100%;
}
article.not-found {
  /*@apply flex flex-col justify-center items-center gap-4 p-16;*/
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 64px;
  h1 {
    /*@apply text-2xl font-bold;*/
    font-size: 1.5rem;
    font-weight: 700;
  }
  .nuxt-link-active {
    /*@apply underline;*/
    text-decoration-line: underline;
  }
}
article.post {
  /*@apply m-auto p-4 w-full max-w-3xl;*/
  margin: auto;
  padding: 16px;
  max-width: 768px;
  > h1 {
   /* @apply font-black text-4xl mt-6 my-4;*/
    font-weight: 900;
    font-size: 36px;
    line-height: 40px;
    margin: 24px;
  }
  > div.author {
    /*@apply text-gray-800;*/
    color: rgb(75 85 99);
    small {
      /*@apply italic;*/
      font-style: italic;
    }
  }
  > p {
    /*@apply block text-gray-700 font-semibold my-4;*/
    display: block;
    color: rgb(75 85 99);
    font-weight: 600;
    margin: 16px auto;
  }
  > figure {
   /* @apply w-full my-4;*/
    width: 100%;
    margin: 16px auto;
    img {
     /* @apply w-full;*/
     width: 100%;
    }
    figcaption {
    /*  @apply italic text-gray-400 text-right;*/
    font-style: italic;
    color: rgb(75 85 99);
    text-align: right;
    }
  }
  .markdown {
    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
     /* @apply font-bold my-6;*/
     font-weight: 700;
     margin: 24px auto;
      
    }
    h1 {
     /* @apply text-3xl;*/
     font-size: 30px;
    }
    h2 {
    /* @apply text-2xl;*/
    font-size: 24px;
    }
    h3 {
    /*  @apply text-xl;*/
    font-size: 20px;
    }
    h4 {
     /* @apply text-lg;*/
     font-size: 18px;
    }
    p {
    /*  @apply font-serif inline-block w-full my-4;*/
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      display: inline-block;
      width: 100%;
      margin: 16px auto;
    }
    a {
      /*  @apply underline;*/
      text-decoration-line: underline;
    }
    pre {
     /* @apply w-full block bg-gray-200 font-mono my-4 px-4 py-4 box-border overflow-x-auto;*/
      width: 100%;
      display: block;
      background-color: rgb(229 231 235);
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      margin: 16px auto;
      padding: 16px;
      box-sizing: border-box;
      overflow-x: auto;
    }
    code {
     /* @apply inline bg-gray-200 font-mono px-1;*/
     display: inline;
     background: rgb(229 231 235);
     font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
     padding: 0 4px;

    }
    em {
     /* @apply italic;*/
     font-style: italic;
    }
    strong {
     /* @apply font-bold;*/
     font-weight: 700;
    }
    blockquote {
     /* @apply block w-full my-4 px-4 py-2 bg-gray-200 border-l-8 border-gray-600;*/
     display: block;
     width: 100%;
     margin: 16px auto;
     padding: 8px 16px;
     background-color: rgb(229 231 235);
     border: 8px solid rgb(75 85 99);
    }
    ol {
    /*  @apply ml-8 list-disc;*/
    margin-left: 32px;
    list-style-type: disc;
    }
    ul {
     /* @apply ml-8 list-decimal;*/
     margin-left: 32px;
     list-style-type: decimal;
    }
    hr {
    /*  @apply my-8;*/
      margin: 32px auto;
    }
    dl {
    /*  @apply bg-gray-100 my-4 px-6 pt-3 pb-4;*/
      background-color: rgb(243 244 246);
      margin: 16px auto;
      pad: 12px 24px 16px 24px;

      dt {
     /*   @apply font-bold font-sans;*/
        font-weight: 700;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      }
      dd {
     /*   @apply italic text-sm text-gray-800 ml-8 mb-1;*/
        font-style: italic;
        font-size: 14px;
        color: rgb(31 41 55);
        margin: auto auto 4px 32px;
      }
    }
    table {
    /*  @apply block table-auto my-4 text-left whitespace-nowrap overflow-x-auto;*/
      display: block;
      table-layout: auto;
      margin: 16px auto;
      text-align: left;
      white-space: nowrap;
      overflow-x: auto;
      thead {
      /*  @apply w-full bg-gray-300;*/
        width: 100%;
        background-color: rgb(209 213 219);
        th {
       /*   @apply border border-collapse px-3 py-2;*/
          border: 1px solid black;
          border-collapse: collapse;
          padding: 8px 13px;
        }
      }
      tbody {
       /* @apply w-full;*/
        width: 100%;
        tr {
          td {
          /*  @apply border border-collapse px-3 py-2;*/
            border: 1px solid black;
            border-collapse: collapse;
            padding: 8px 12px;
          }
        }
        tr:nth-child(even) {
         /* @apply bg-gray-100;*/
         background-color: rgb(243 244 246);
        }
      }
    }
  }
  .comments {
  /*  @apply block w-full bg-gray-200 my-4 px-6 py-6;*/
    display: block;
    width: 100%;
    background-color: rgb(229 231 235);
    margin: 16px auto;
    padding: 24px;
    .title {
   /*   @apply font-bold text-2xl;*/
      font-weight: 700;
      font-size: 24px;
    }
    .total-comments {
    /*  @apply mb-4;*/
      margin-bottom: 16px;
    }
    .comments-list {
    /*  @apply flex flex-col gap-4;*/
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
  }
  .to-top {
  /*  @apply pointer-events-none absolute sticky w-full flex justify-end my-4 px-4 py-4 left-0 right-0 bottom-0;*/
    pointer-events: none;
    position: absolute;
    position: sticky;
    width: 100%;
    display: flex;
    justify-content: end;
    margin: 16px auto;
    padding: 16px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    button {
    /*  @apply pointer-events-auto border rounded-lg px-6 py-2 bg-white;*/
      pointer-events: auto;
      border: 1px solid black;
      border-radius: 8px;
      padding: 8px 24px;
      background-color: white;
    }
  }
}
</style>

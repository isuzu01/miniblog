<template>
  <div class="about-me">
    <h1>Miniblog</h1>
    <p>Miniblog es un pequeño sistema de un blog personal con NuxtJS</p>
  </div>
</template>

<style lang="scss" scoped>
.about-me {
  /*@apply w-full flex flex-col justify-center items-center px-4 py-16 bg-gray-200;*/
    
    background: rgba(128, 128, 128, 0.349);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

  h1 {
   /* @apply font-black text-4xl text-gray-900 pb-2;*/
   color: black;
   font-weight: 700;
   font-size: 3rem;
   margin: 80px auto 10px;

  }
  p {
   /* @apply text-lg py-2;*/
   margin-bottom: 50px;
  }
}
</style>
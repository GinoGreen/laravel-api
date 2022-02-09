<template>
   <header>
      <ul>
         <li><a href="">Home</a></li>
         <li><a href="">Post</a></li>
         <li><a href="">Chi Siamo</a></li>
         <li><a href="">Contatti</a></li>
      </ul>
   </header>
</template>

<script>
export default {
   name: 'Header'
}
</script>

<style lang="scss">

   header {
      ul {
         @include reset-list();
         li {

            a {
               @include reset-a();
            }
         }
      }
   }
</style>
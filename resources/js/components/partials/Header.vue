<template>
   <header>
      <ul>
         <li><a href="">Home</a></li>
         <li><a href="">Blog</a></li>
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
      background-color: white;
      ul {
         list-style: none;
         font-size: 2em;
         display: flex;
         li {
            margin: 0 20px;
            padding: 20px 0;
            a {
               text-decoration: none;
               color: #23272E;
               &:hover {
                  text-decoration: underline;
               }
            }
         }
      }
   }
</style>
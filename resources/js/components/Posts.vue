<template>
   <main class="container blog">
      <article 
         v-for="post in posts"
         :key = "post.id"
      >
         <h2><a href="">{{ truncatesTextAt(post.title, 20) }}</a></h2>
         <span class="date">{{ getDatePost(post.created_at) }}</span>
         <p>{{ truncatesTextAt(post.content, 50) }}</p>
      </article>
   </main>
</template>

<script>
export default {
   name: 'Posts',
   mounted() {
      this.getPosts();
   },
   data() {
      return {
         apiUrl: 'http://127.0.0.1:8000/api/posts',
         posts: [],
      }
   },
   methods: {

      getPosts() {
         axios.get(this.apiUrl)
            .then(response => {
               this.posts = response.data;
            })
      },

      truncatesTextAt(text, numberChars) {
         if (text.length > numberChars) {
            return text.substr(0, numberChars) + ' ...';
         }
         return text;
      },

      getDatePost(dateString) {
         const date = new Date(dateString);
         let day = date.getDate();
         let month = date.getMonth() + 1;
         let year = date.getFullYear();
         
         if (day < 10) day = '0' + day;
         if (month < 10) month = '0' + month;

         return `${day}/${month}/${year}`
      },
   }
}
</script>

<style lang="scss">

</style>
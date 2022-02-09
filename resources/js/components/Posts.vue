<template>
   <main class="container blog">
      <article 
         v-for="post in posts"
         :key = "post.id"
      >
         <h2><a href="">{{ truncatesTextAt(post.title, 20) }}</a></h2>
         <span class="date">{{ post.created_at }}</span>
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
      }
   }
}
</script>

<style lang="scss">

</style>
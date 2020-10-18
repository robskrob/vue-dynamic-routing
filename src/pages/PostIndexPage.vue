<template>
    <div>
        <template v-for="(post, index) in posts" >
            <router-link :to="'/posts/' + post.id" :key="index">
                {{ post.title }}
            </router-link>
        </template>
    </div>
</template>

<script>
export default {

  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then(response => response.json())
      .then(json => this.posts = json);
  },

  data: function () {
    return {
      posts: []
    }
  }
}
</script>

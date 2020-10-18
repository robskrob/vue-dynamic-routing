<template>
    <div>
        <router-link to="/posts">Back</router-link>
        <template v-if="post">
            <div>
                {{ post.title }}
            </div>
            <div>
                {{ post.body }}
            </div>
        </template>
    </div>
</template>

<script>
export default {

  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts/' + this.$route.params.id)
      .then(response => response.json())
      .then(json => this.post = json);
  },

  data: function () {
    return {
      post: null
    }
  }
}
</script>

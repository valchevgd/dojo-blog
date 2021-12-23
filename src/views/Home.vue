<template>
  <div class="home">
    <h1>Home</h1>
    <p v-if="error">{{ error }}</p>
    <PostList v-if="posts.length" :posts="posts"/>
    <p v-else-if="!error">Loading...</p>
  </div>
</template>

<script>
import {ref} from 'vue';
import PostList from '../components/PostList';

export default {
  name: 'Home',
  components: {PostList},
  setup() {
    const posts = ref([]);
    const error = ref(null);

    const load = async () => {
      try {

        const data = await fetch('http://localhost:3000/posts');

        if (!data.ok) {
          throw Error('Something went wrong...');
        }

        posts.value = await data.json();

      } catch (err) {
        error.value = err.message;
      }
    };

    load();

    return {posts, error};
  }
};
</script>

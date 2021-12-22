<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts"/>
  </div>
</template>

<script>
import {ref} from 'vue';
import PostList from '../components/PostList';

export default {
  name: 'Home',
  components: {PostList},
  setup() {
    const posts = ref([
      {id: 1, title: 'Welcome to the blog', body: 'orem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum at risus id purus commodo dapibus. Praesent dapibus a purus ut porttitor. Nunc viverra massa ac magna accumsan, in porta urna iaculis. Pellentesque tincidunt non.'},
      {id: 2, title: 'Top 5 CSS tips', body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eget libero at diam porttitor luctus at at diam. Phasellus molestie sed quam id dignissim. Morbi a aliquet ipsum. Sed scelerisque nibh sit amet risus laoreet mi.'}
    ]);

    return {posts};
  }
};
</script>

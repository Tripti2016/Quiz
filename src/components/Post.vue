<template>
    <div>
      <h1>Posts</h1>
      <ul>
        <li v-for="post in paginatedPosts" :key="post.id">{{ post.title }}</li>
      </ul>
      <div>
        <button @click="previousPage" :disabled="currentPage === 1">Previous</button>
        <button @click="nextPage" :disabled="currentPage >= totalPages">Next</button>
      </div>
    </div>
  </template>
  
<script>
import axios from 'axios';

export default {
    name: 'Post',
    data() {
    return {
      posts: [],
      currentPage: 1,
      itemsPerPage: 10,
      totalPages: 0,
    };
  },
    methods: {
    async fetchPosts() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts', {
          params: {
            _page: this.currentPage,
            _limit: this.itemsPerPage,
          },
        });
        this.totalPages = Math.ceil(Number(response.headers['x-total-count']) / this.itemsPerPage);
        this.posts = response.data;
      } catch (error) {
        console.error(error);
      }
    },
    previousPage() {
      this.currentPage--;
      this.fetchPosts();
    },
    nextPage() {
      this.currentPage++;
      this.fetchPosts();
      
      
    },
  },
    computed: {
    startIndex() {
      return (this.currentPage - 1) * this.itemsPerPage;
    },
    endIndex() {
      return this.startIndex + this.itemsPerPage;
    },
    paginatedPosts() {
      return this.posts.slice(this.startIndex, this.endIndex);
    },
  },
  watch: {
    currentPage() {
      this.fetchPosts();
    },
    itemsPerPage() {
      this.currentPage = 1;
      this.fetchPosts();
    },
  },
  created() {
    this.fetchPosts();
  },
};
</script>
  
<script>
import BlogPost from "./components/BlogPost.vue";
export default {
  components: {
    BlogPost,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: null,
          author: { name: "abc" },
          tag: [1, 2, 3],
          marks: 98
        },
        {
          id: 2,
          title: "Blogging with Vue",
          author: { name: "def" },
          tag: [4, 5, 6],
        },
        {
          id: 3,
          title: "Why Vue is so fun",
          author: { name: "ghi" },
          tag: [7, 8, 9],
          marks: 56
        },
      ],
    };
  },
};
</script>

<template>
  <BlogPost
    v-for="post in posts"
    :id="post.id"
    :title="post.title"
    :isValid="true"
    :author="post.author"
    :tag="post.tag"
    :marks="post.marks"
  />
</template>

<style scoped></style>

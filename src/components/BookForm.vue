<template>
  <form class action="#" method="post" v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)">
    <input type="text" name="title" value v-model="bookTitle" placeholder="Book Title" />
    <input type="text" name="author" value v-model="bookAuthor" placeholder="Book Author" />
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  data: () => {
    return {
      bookTitle: "",
      bookAuthor: ""
    };
  },
  methods: {
    bookSubmit: function(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    }
  },
  props: ["books"]
};
</script>

<style>
</style>

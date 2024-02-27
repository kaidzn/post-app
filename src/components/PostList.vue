<template>
    <div class="post" 
    v-for="post in posts">
      <div class="container">
          <p>This is the <strong>{{ post.title }}</strong></p>
          <p>Description: <strong>{{ post.description }}</strong></p>
        </div>
        <button @click="removePost(post)" class="rmv-btn">Remove</button>
    </div>
</template>

<script>
export default {
   props: {
    posts: {
        type: Array,
        required: true,
    }
   },
   methods: {
    removePost(post) {
      this.$emit('remove', post);
    }
   }
}
</script>

<style scoped>
.rmv-btn{
  padding: 10px 15px;
  border: 2px solid teal;
  color: teal;
  background: none ;
  margin: 10px 0;
}
.post{
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-left: auto;
  margin-right: auto;
  padding: 10px;
  width: 50%;
  margin-top: 15px;
  border: 2px solid teal;
}
</style>
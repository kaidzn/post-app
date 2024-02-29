<template>
    <div v-if="posts.length > 0">
      <h3>List of users</h3>
      <post-item
          v-for="post in posts"
          :key="post.id"
          :post="post"
          @remove="$emit('remove', post)"
      />
    </div>
  <h1 v-else style="color: red">
      Users' list is empty
  </h1>
</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  components: {PostItem},
   props: {
    posts: {
        type: Array,
        required: true,
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
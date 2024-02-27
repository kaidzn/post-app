<template>
    <form @submit.prevent>
      <h1>Creating Post</h1>
      <input 
        v-model="post.title"
        class="input" 
        type="text" 
        placeholder="Title">
      <input 
        v-model="post.description"
        class="input" 
        type="text" 
        placeholder="Description">
      <button class="btn" @click="createPost">Create</button>
    </form>
</template>

<script>
    export default {
        data(){
            return{
                post: {
                    title: '',
                    description: '',
                }
            }
        },
        methods: {
            createPost(){
                this.post.id = Date.now();
                this.$emit('create', this.post);
                this.post = {
                    title: '',
                    description: '',
                }
            }
        }
    }
</script>

<style scoped>
form{
  display: flex;
  flex-direction: column;
}
.input{
  width: 100%;
  border: 1px solid teal;
  padding: 10px 16px;
  margin-top: 15px;
}
.btn{
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
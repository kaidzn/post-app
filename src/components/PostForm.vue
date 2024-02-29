<template>
    <form @submit.prevent>
      <h1>Creating Post</h1>
      <my-input
        v-model="post.title"
        type="text"
        placeholder="Title"/>
      <my-input
        v-model="post.description"
        type="text" 
        placeholder="Description"/>
      <my-button
          @click="createPost"
          style="align-self: flex-end; margin-top: 15px;"
      >
        Create
      </my-button>
    </form>
</template>

<script>
    import MyInput from "@/components/UI/MyInput.vue";

    export default {
      components: {MyInput},
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


</style>
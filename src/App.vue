<template>
  <div class="app">
    <h1>Page with posts</h1>
    <my-button
      @click="showDialog"
      style="margin: 15px 0"
    >
      Create user
    </my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form
         @create="createPost"
      />
    </my-dialog>
    <post-list
      :posts="posts"
      @remove="removePost"
    />
  </div>
</template>
<script>
import PostForm from './components/PostForm.vue'
import PostList from './components/PostList.vue'
import MyDialog from "@/components/UI/MyDialog.vue";
export default{
  name: 'App',
  components: {
    MyDialog,
    PostForm,
    PostList,
  },
  data(){
    return{
      posts: [
        {id: 1, title: "Javascript", description: "Description"},
        {id: 2, title: "Javascript 2", description: "Description 2"},
        {id: 3, title: "Javascript 3", description: "Description 3"},
      ],
      dialogVisible: false,
      title: '',
      description: '',
    }
  },
  methods: {
    createPost(post){
      this.posts.push(post)
      this.dialogVisible = false
    },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialog(){
      this.dialogVisible = true;
    }

  }

}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app{
  padding: 20px;
}



</style>

<template>
  <div class="container">
    <post-form
       @create="createPost"/>
    <post-list
      :posts="posts"
      @remove="removePost"/>
  </div>
</template>
<script>
import PostForm from './components/PostForm.vue'
import PostList from './components/PostList.vue'
export default{
  name: 'App',
  components: {
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
      title: '',
      description: '',
    }
  },
  methods: {
    createPost(post){
      this.posts.push(post)
    },
    removePost(post){
      this.posts = this.posts.filter(item => item.id !== post.id);
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
.container{
  padding: 20px;
}



</style>

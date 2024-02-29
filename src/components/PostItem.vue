<template>
  <div class="post">
    <div>
    <p>This is the <strong>{{ post.title }}</strong></p>
    <p>Description: <strong>{{ post.description }}</strong></p>
    </div>
    <div class="post__btns">
        <my-button
            @click="$emit('remove', post)"
        >Remove</my-button>
    </div>
  </div>
</template>

<script>
export default {

  props: {
    post: {
      type: Object,
      required: true
    }
  }

}
</script>

<style scoped>
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
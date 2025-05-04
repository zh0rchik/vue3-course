<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Название">
    <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Описание">
    <button
        class="btn"
        @click="createPost"
    >
      Создать</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post:{
        title:'',
        body:'',
      }
    }
  },
  methods:{
    createPost(){

      this.post.id = Date.now();

      this.posts.push(newPost);

      this.title = '';
      this.body = '';
    },
  }
}
</script>

<style scoped>
form{
  display: flex;
  flex-direction: column;
}

.btn{
  align-self: flex-end;
  margin-top: 15px;
  padding: 15px 10px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

.input{
  width: 100%;
  border: 3px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

</style>
<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <my-input
        v-model="post.title"
        type="text"
        placeholder="Название"/>
    <my-input
        v-model="post.body"
        type="text"
        placeholder="Описание"/>
    <my-button
        style="align-self: flex-end; margin-top: 15px"
        class="btn"
        @click="createPost"
    >
      Создать</my-button>
  </form>
</template>

<script>

export default {
  components: {},
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
      this.$emit('create', this.post);    // заимитить событие. $emit - сгенерировать событие, на который родительский компонент сможет подписаться
      this.post = {
        title: '',
        body: ''
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
<template>
  <div class="app">
    <post-form
        @create="createPost"/> <!--подписываемся под событие, функци которая отработает по этому событию-->
    <post-list
        :posts="posts"
    />  <!--передаем в компонент (бандим) как пропсы-->
  </div>
</template>

<script>
import PostForm from "./components/PostForm";
import PostList from "./components/PostList";
// компонент, всё остальное - синтактический сахар
export default {
  //регистрация компонентов
  components: {
    PostForm, PostList
  },
  data(){
    return{ // здесь модели
      posts: [
        {id: 1, title: 'JavaScript', body: 'Описание поста'},
        {id: 2, title: 'JavaScript 2', body: 'Описание поста 2'},
        {id: 3, title: 'JavaScript 3', body: 'Описание поста 3'},
      ],
    }
  },
  methods:{
    createPost(post){
      this.posts.push(post);
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app{
  padding: 20px;
}
</style>
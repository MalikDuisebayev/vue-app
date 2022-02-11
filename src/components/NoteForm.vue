<template>
  <form @submit.prevent>
    <input type="text" placeholder="Заголовок" v-model.trim="post.title" />
    <input type="text" placeholder="Описание" v-model.trim="post.body" />
    <my-button @click="createNote">Сохранить</my-button>
  </form>
</template>

<script>
import myButton from './UI/myButton.vue'
export default {
    components: {myButton},
  data() {
    return {
        post: {
          title: "",
          body: "",
        }
    };
  },
  methods: {
      createNote(){
        if(!this.post.title || !this.post.body) return
          this.post.id = Date.now()
          this.$emit('create',this.post)
          this.post = {title : '', body : ''}
      }
  },
};
</script>

<style scoped>
.notes form {
  display: flex;
  flex-direction: column;
  margin-bottom: 50px;
}
.notes form input {
  padding: 15px 18px;
  margin-bottom: 20px;
  width: 100%;
}
button {
  align-self: flex-end;
  background: rgb(26, 26, 114);
}

</style>
<template>
   <div class="notes__list">
        <div class="notes__item" v-for="note in notes" :key="note.id">
          <p><strong>Заголовок:</strong> {{ note.title }}</p>
          <p><strong>Описание:</strong> {{ note.body }}</p>
          <i class='notes__btn bx bxs-trash' @click="$emit('delete',note)" title = "Delete"> </i>
        </div>
        <div class="notes__length">
          <p v-if="notes.length">
            <strong>Количество заметок:</strong> {{ notes.length }}
          </p>
          <p v-else><strong>Добавьте свою первую заметку</strong></p>
        </div>
      </div>
</template>

<script>
export default {
    props:{
        notes: {
            type: Array,
            required: true
        }
    }

}
</script>

<style scoped>
.notes__list {
  width: 100%;
}
.notes__item {
  width: 100%;
  padding: 15px 18px;
  margin-bottom: 20px;
  border-radius: 12px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  position: relative;
}
.notes__item p {
  max-width: 100%;
}
.notes__item p:first-child {
  margin-bottom: 15px;
}
.notes__btn {
  position: absolute;
  top: 50%;
  right: 18px;
  transform: translateY(-50%);
  cursor: pointer;
  font-size: 25px;
  color: darkred;
}
.notes__length {
  padding: 15px 18px;
  text-align: right;
}

</style>
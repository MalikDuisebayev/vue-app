<template>
  <div class="container">
    <i class='bx bx-edit'></i>
    <div class="notes">
      <note-form @create ='createNote' /> 
     <note-list @delete ='deleteNote' :notes ='notes' />
    </div>
  </div>
</template>

<script>
import myButton from "../components/UI/myButton.vue";
import NoteForm from '../components/NoteForm.vue'
import NoteList from '../components/NoteList.vue'
export default {
  components: { myButton , NoteForm, NoteList },
  data() {
    return {
      notes: []
    };
  },
  methods: {
    createNote(post){
      this.notes.push(post)
      this.saveNoteLocaleStorage()
    },
    deleteNote(note) {
      this.notes = this.notes.filter((i) => i.id !== note.id);

      this.saveNoteLocaleStorage();
    },
    saveNoteLocaleStorage() {
      const data = JSON.stringify(this.notes);
      localStorage.setItem("note", data);
    },
  },
  mounted() {
    if (localStorage.getItem("note")) {
      try {
        this.notes = JSON.parse(localStorage.getItem("note"));
      } catch (e) {
        localStorage.removeItem("note");
      }
    }
  },
};
</script>

<style scoped>
.notes {
  max-width: 100%;
}
.bx-edit{
  font-size: 30px;
  margin-bottom: 50px;
  color:  rgb(9, 9, 54);
}

</style>
<template>
  <div class="notes">
    <div class="card has-background-danger p-4 mb-4">
      <div class="field">
        <label class="label" style="color: white;">Message</label>
        <div class="control">
          <textarea v-model="newNote" class="textarea" placeholder="Textarea" ref="newNoteRef"></textarea>
        </div>
      </div>

      <div class="field is-grouped is-grouped-right">
        <div class="control">
          <button @click="addNote" :disabled="!newNote" class="button is-link is-danger is-light">Add New Note</button>
        </div>
      </div>
    </div>
    <div class="card mb-4" v-for="note in notes" :key="note.id">
      <div class="card-content">
        <div class="content">
          {{ note.content  }}
        </div>
      </div>
      <footer class="card-footer">
        <a href="#" class="card-footer-item">Edit</a>
        <a href="#" class="card-footer-item">Delete</a>
      </footer>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { v4 as uuidv4 } from 'uuid';

const newNote = ref("");
const newNoteRef = ref(null);
const notes = ref([
    {
        id: 1,
        content: "My first note message here 1" ,
    },
])

const addNote = () => {
    let note = {
        id: uuidv4() ,
        content : newNote.value
    }
    notes.value.unshift(note);
    newNote.value = ""; 
    newNoteRef.value.focus();
}
</script>
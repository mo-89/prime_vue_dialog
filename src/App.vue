<template>
  <div id="app">
    <Button label="Show" icon="pi pi-check" @click="showDialog = true"></Button>
  </div>

  <Dialog header="GodFather I" v-model:visible="showDialog" :modal="true" :style="{width: '50vw'}">
    <p>The story begins as Don Vito Corleone, the head of a New York Mafia family, oversees his daughter's wedding...</p>
    <Button label="Hide" icon="pi pi-times" @click="showDialog = false"></Button>
  </Dialog>
</template>

<script>
import { ref } from 'vue';
import Dialog from 'primevue/dialog'
import Button from 'primevue/button'

export default {
  components: {
    Dialog,
    Button
  },
  setup() {
    const showDialog = ref(false);

    return { showDialog };
  }
}

</script>

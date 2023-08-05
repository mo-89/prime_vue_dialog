<template>
  <Button label="open modal" @click="showDialog" />

  <Dialog :visible="display" :modal="true" :style="{ width: '50vw'}" :closable="false" @hide="onHide">  
    <template #header>
      <h2>Input form</h2>
    </template>
    <div class="p-fluid">
      <div class="p-filed">
        <label for="input1">input 1</label>
        <InputText id="input1" v-model="input1" />
      </div>
      <div class="p-filed">
        <label for="input2">input 2</label>
        <InputText id="input2" v-model="input2" />
      </div>
    </div>
    <template #footer>
      <Button label="Cancel" class="p-button-text" @click="onHide" />
      <Button label="Submit" class="p-button-success" @click="submit" />
    </template>
  </Dialog>
</template>

<script>
import Dialog from 'primevue/dialog'
import Button from 'primevue/button'
import InputText from 'primevue/inputtext'

export default {
  components: {
    Dialog,
    Button,
    InputText
  },
  data() {
    return {
      display: false,
      input1: '',
      input2: '',
    }
  },
  methods: {
    showDialog() {
      this.display = true;
    },
    onHide() {
      this.display = false;
    },
    submit() {
      console.log(this.input1);
      console.log(this.input2);
      this.onHide();
    }
  }
}
</script>
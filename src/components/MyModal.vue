
<template>
  <Dialog :visible="localDisplay" :modal="true" :closable="false">
    <template #header>
      <h2>Input form</h2>
    </template>
    <div class="p-fluid">
      <div class="p-filed">
        <label for="input1">input 1</label>
        <InputText id="input1" v-model="record.input1" />
      </div>
      <div class="p-filed">
        <label for="input2">input 2</label>
        <InputText id="input2" v-model="record.input2" />
      </div>
    </div>
    <template #footer>
      <Button label="create" @click="create" />
      <Button label="close" @click="close" />
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
  props: {
    display: Boolean,
    createRecord: Function
  },
  data() {
    return {
      localDisplay: this.display,
      record: {
        input1: '',
        input2: ''
      }
    };
  },
  watch: {
    display(newVal) {
      this.localDisplay = newVal
    }
  },
  methods: {
    create() {
      this.createRecord(this.record)
    },
    close() {
      this.localDisplay = false
      this.$emit('update:display', false)
    }
  }
};
</script>

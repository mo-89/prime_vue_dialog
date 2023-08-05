<template>
  <div>
    <Button label="create new" @click="display = true" />
    <MyModal 
      :display="display"
      @update:display="display = $event"
      :createRecord="createRecord"
    ></MyModal>
  </div>
</template>

<script>
import axios from 'axios'
import Button from 'primevue/button'
import MyModal from './components/MyModal.vue'

export default {
  components: {
    Button,
    MyModal
  },
  data() {
    return {
      display: false,
      records: []
    };
  },
  async created() {
    // const response = await axios.get('/api/records')
      const response = []
    this.records = response.data
  },
  methods: {
    async createRecord(record) {
      await axios.post('api/create', record)
      // const response = await axios.get('/api/records')
      const response = []
      this.records = response.data
      this.display = false
    }
  }
}
</script>
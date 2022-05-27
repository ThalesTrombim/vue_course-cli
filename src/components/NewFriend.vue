<template>
  <form @submit.prevent='submitData'>
    <div>
      <label>Name</label>
      <input @click='name' type="text" v-model="enteredName">
    </div>
    <div>
      <label>Phone</label>
      <input @click='name' type="tel" v-model="enteredPhone">
    </div>
    <div>
      <label>E-mail</label>
      <input @click='name' type="email" v-model="enteredEmail">
    </div>
    <div>
      <button>Add Contact</button>
    </div>
  </form>
</template>

<script>
  export default {
    emits: ['add-contact'],
    data() {
      return {
        enteredName: '',
        enteredPhone: '',
        enteredEmail: ''
      }
    },
    methods: {
      submitData() {
        this.$emit('add-contact', {
          name: this.enteredName,
          phone: this.enteredPhone,
          email: this.enteredEmail
        })
      }
    }
  }
</script>
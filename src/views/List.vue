<template>
  <div>
    <input v-model="newContact" type="text" placeholder="Name" />
    <button @click="addContact">Add Contact</button>
    <button @click="sortContact">Sort Contact</button>

    <transition-group name="slide-up" tag="ul" appear>
      <li v-for="contact of contacts" :key="contact">
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newContact: '',
      contacts: ['kameko', 'boboji']
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
      this.newContact = ''
    },
    sortContact() {
      this.contacts.sort()
    }
  }
}
</script>

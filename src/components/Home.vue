<template>
  <div>
    <h1>Hello World</h1>
    <form @submit.prevent="add">
      <input type="text" v-model="newItem">
      <button type="submit">Add</button>
    </form>
    <items :items="items" :remove="remove"></items>
  </div>
</template>

<script>
import items from "@/components/Items";

export default {
  components: {
    items
  },
  data() {
    return {
      lists: [
        {'name': 'Adi'},
        {'name': 'Permana'},
        {'name': 'Putra'},
        {'name': 'Vuejs'},
        {'name': 'Angular'},
        {'name': 'Pikachu'}
      ],
      newItem: null
    }
  },
  computed: {
    items: function () {
      return this.lists.filter(function (item) {
        if (item.name === 'React') item.name = 'No React Allowed';

        return item;
      })
    }
  },
  methods: {
    remove(index) {
      this.lists.splice(index,1);
    },
    add() {
      if (null !== this.newItem) {
        this.lists.push({
          'name': this.newItem
        })
      }
    }
  }
}
</script>

<style>

</style>
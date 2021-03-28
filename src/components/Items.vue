<template>
  <div>
    <ul>
      <li
          v-for="(item, index) in items"
          :key="item.name"
      >
        {{item.name}} <button @click="removeItem(index)">X</button>
      </li>
    </ul>
  </div>
</template>

<script>
 export default {
   props: {
     items: Array,
     remove: Function
   },
   methods: {
     removeItem(index) {
       this.remove(index);
     }
   }
 }
</script>

<style>

</style>
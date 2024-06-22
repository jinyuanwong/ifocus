<template>
  <div class="container mx-auto p-4">
    <h1 class="text-2xl font-bold mb-4">Items</h1>
    <ul>
      <li v-for="item in items" :key="item._id" class="mb-2">
        {{ item.name }} ({{ item.quantity }})
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: []
    };
  },
  async created() {
    const response = await fetch('http://localhost:5000/api/items');
    this.items = await response.json();
  }
};
</script>

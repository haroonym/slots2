<template>
  <div class="container mt-5" id="app">
    <Catogram :cats="cats">
      <template #boss="{item}">
        <h5>{{ item.name }}</h5>
        <img :src="item.image" width="200" alt="" />
      </template>
      <template #employees="{item}">
        <div>
          <h5>{{ item.name }}</h5>
          <img :src="item.image" width="200" alt="" />
          <p class="mt-2 fw-bold">Job role: {{ item.role }}</p>
        </div>
      </template>
    </Catogram>
  </div>
</template>

<script>
import cats from '@/assets/cats.json';

import Catogram from '@/components/Catogram.vue';

export default {
  name: 'App',
  components: {
    Catogram,
  },
  data() {
    return {
      cats,
      // cats: [
      //   {
      //     name: 'Franz',
      //     role: 'Sales',
      //     image: 'images/franz.png',
      //   },
      //   {
      //     name: 'Pizz',
      //     role: 'Research',
      //     image: 'images/pizz.png',
      //   },
      //   {
      //     name: 'Jeremy',
      //     role: 'Boss',
      //     image: 'images/jeremy.png',
      //   },
      //   {
      //     name: 'Stella',
      //     role: 'Customer Support',
      //     image: 'images/stella.png',
      //   },
      // ],
    };
  },
};
</script>

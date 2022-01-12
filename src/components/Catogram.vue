<template>
  <div>
    <h3 class="fw-bold mb-5">Scratchy Inc.</h3>
    <div>
      <h4 class="fw-bold">Boss</h4>
      <slot name="boss" :item="boss"></slot>
    </div>
    <h4 class="fw-bold mt-5">Employees</h4>
    <div class="d-flex flex-wrap">
      <div class="m-1" v-for="(employee, i) of employees" :key="i">
        <slot name="employees" :item="employee">
          <span>{{ cat.name }}</span>
        </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cats: {
      type: Array,
    },
  },
  data() {
    return {
      boss: this.cats.find((el) => el.role == 'Boss'),
      employees: this.cats.filter((el) => el.role != 'Boss'),
    };
  },
};
</script>

<style lang="scss" scoped></style>

<template>
  <div class="budget-list-wrap">
    <ElCard :header="header">
      <template v-if="!isEmpty">
        <BudgetListItem :list="list" @deleteItem="deleteItem" />
      </template>
      <ElAlert v-else type="info" :title="emptyTitle" :closable="false" />
    </ElCard>
  </div>
</template>

<script>
import BudgetListItem from '@/components/BudgetListItem';

export default {
  name: 'BudgetList',
  props: {
    list: {
      type: Object,
      default: () => ({}),
    },
  },
  components: {
    BudgetListItem,
  },
  data: () => ({
    header: 'Budget List',
    emptyTitle: 'Empty List',
  }),
  computed: {
    isEmpty() {
      return !Object.keys(this.list).length;
    },
  },
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    },
  },
};
</script>

<style scoped>
.budget-list-wrap {
  max-width: 520px;
  margin: auto;
}
</style>

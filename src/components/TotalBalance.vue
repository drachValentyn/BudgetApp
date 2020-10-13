<template>
  <div class="total-value" :class="colorClass">Balance: {{ total }}</div>
</template>

<script>
export default {
  name: 'TotalBalance',
  props: {
    total: {
      type: Number,
      default: 0,
    },
  },
  data: () => ({
    colorClass: '',
  }),
  created: function() {
    this.color();
  },
  watch: {
    total: 'color',
  },
  methods: {
    color() {
      return (this.colorClass =
        this.total > 0 ? 'more' : this.total < 0 ? 'less' : 'default');
    },
  },
};
</script>

<style scoped>
.total-value {
  font-size: 26px;
  text-transform: uppercase;
  padding: 20px;
  text-align: center;
}
.more {
  color: green;
}

.less {
  color: red;
}

.default {
  color: black;
}
</style>

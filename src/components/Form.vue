<template>
  <ElCard>
    <ElForm :model="formData">
      <ElFormItem label="Type" prop="type">
        <ElSelect>
          <ElOption></ElOption>
        </ElSelect>
      </ElFormItem>
    </ElForm>
  </ElCard>
</template>

<script>
export default {
  name: 'Form',
  data: () => ({
    formData: {
      type: 'INCOME',
      comment: '',
      value: 0,
    },
  }),
};
</script>

<style scoped></style>

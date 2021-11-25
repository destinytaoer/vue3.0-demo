<template>
  <p>
    用户编号: {{ id }}<br />
    用户姓名: {{ name }}<br />
  </p>
</template>
<script lang="ts">
const query = () => {
  return new Promise<{ id: number; name: string }>((resolve, reject) => {
    setTimeout(() => {
      resolve({ id: 1, name: 'destiny' });
    }, 2000);
  });
};

export default {
  name: 'SuspenseDemo',
  async setup() {
    const data = await query();
    return {
      ...data,
    };
  },
};
</script>
<style></style>

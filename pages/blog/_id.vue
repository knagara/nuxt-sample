<template>
  <div>
    <h2>Blog</h2>
    <h3>id: {{ $route.params.id }}</h3>
  </div>
</template>

<script>
export default {
  validate({ params }) {
    // paramsが数字かどうかを判定
    return /^\d+$/.test(params.id);
  },
};
</script>

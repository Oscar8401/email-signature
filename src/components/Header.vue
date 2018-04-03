<template>
  <div>
    <h1>{{ pageTitle }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  },
  data() {
    return {
      pageTitle: this.title,
    };
  },
};
</script>
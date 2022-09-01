<template>
    <the-header title="RememberMe"></the-header>
    <the-resources></the-resources>
</template>

<script>
import TheHeader from './componets/layouts/TheHeader.vue';
import TheResources from './componets/learning-resources/TheResources.vue';

export default {
    components: {
        TheHeader,
        TheResources,
    },
}
</script>

<!-- styles for all components -->
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
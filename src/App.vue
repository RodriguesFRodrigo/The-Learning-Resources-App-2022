<template>
    <stored-resource :resources="storedResources"></stored-resource>
</template>

<script>
import StoredResource from './componets/learning-resources/StoredResource.vue';

export default {
    components: {
        StoredResource,
    },

    data() {
        return {
            storedResources: [
                {
                    id: 'sql',
                    title: 'SQL Plus',
                    description: 'Lean SQL Plus',
                    link: 'https://www.oracle.com/br/database/technologies/sqlplus-cloud.html',
                },
                {
                    id: 'joins',
                    title: 'Joins',
                    description: 'Lean Joins',
                    link: 'https://www.devmedia.com.br/clausulas-inner-join-left-join-e-right-join-no-sql-server/18930',
                }
            ]
        };
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
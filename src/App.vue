<template>
    <ul>
        <learning-resource 
            v-for="res in storedResources" 
            :key="res.id"
            :title="res.title"
            :description="res.description"
            :link="res.link"
        >
        </learning-resource>
    </ul>
</template>

<script>
import LearningResource from './componets/learning-resources/LearningResource.vue';

export default {
    components: {
        LearningResource,
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

<style>

</style>
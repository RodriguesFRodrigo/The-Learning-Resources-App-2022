<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resource')" :mode="getSelectedTab">Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResource">Add Resource</base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
import StoredResource from './StoredResource.vue';
import AddResource from './AddResource.vue';

export default {
    components: {
        StoredResource,
        AddResource,
    },

    data() {
        return {
            selectedTab: 'stored-resource',
            
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
    
    computed: {
        getSelectedTab() {
            return this.selectedTab ===  'stored-resource' ? null : 'flat';
        },

        addResource() {
            return this.selectedTab ===  'add-resource' ? null : 'flat';
        },
    },

    provide() {
        return {
            resources: this.storedResources
        };
    },
    
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
    }
}
</script>

<style>

</style>
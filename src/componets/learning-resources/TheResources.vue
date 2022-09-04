<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resource')" :mode="getSelectedTab">Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResource">Add Resource</base-button>
    </base-card>
    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
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
            resources: this.storedResources,
            addNewResource: this.addNewResource,
            removeResource: this.removeResource,
        };
    },
    
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },

        addNewResource(title, description, url){
            const newResource = {
                id: new Date().toISOString(),
                title,
                description,
                url,
            };
            this.storedResources.unshift(newResource);
            this.selectedTab = 'stored-resource';
        },

        removeResource(id) {
            // Do not work! cauz change the reference os the storedResources and not create reactivity
            // in the components that use storedResources
            // this.storedResources = this.storedResources.filter(resource => resource.id !== id);
            // console.log(this.storedResources.length);
            const idx = this.storedResources.findIndex(resource => resource.id === id);
            this.storedResources.splice(idx, 1);
        },
    }
}
</script>

<style>

</style>
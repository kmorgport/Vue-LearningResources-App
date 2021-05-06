<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" 
        :mode="storedResButton">
        Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resources')"
        :mode="addResButtonMode">
        Add Resources</base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from './StoredResources.vue'
import AddResource from './AddResource.vue'
export default{
    components:{
        StoredResources,
        AddResource
    },
    data(){
        return{
            selectedTab: 'stored-resources',
            storedResources:[
                {id:'official-guide',
                title:'Official Guide',
                description:'The official vue.js documentation.',
                link:'https://vuejs.org'},
                {id:'google',
                title:'Google Guide',
                description:'How to google',
                link:'https://google.com'},
            ]
        };
    },
    computed:{
        storedResButton(){
            return this.selectedTab === 'stored-resources' ? null : 'flat'
        },
        addResButtonMode(){
            return this.selectedTab === 'add-resource' ? null : 'flat'
        }
    },
    provide(){
        return{
            resources: this.storedResources
        }
    },
    methods:{
        setSelectedTab(tab){
            this.selectedTab = tab;
        }
    }
}
</script>

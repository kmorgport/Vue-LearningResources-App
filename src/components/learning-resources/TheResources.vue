<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" 
        :mode="storedResButton">
        Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')"
        :mode="addResButtonMode">
        Add Resources</base-button>
    </base-card>
    <keep-alive>
    <component :is="selectedTab"></component>
    </keep-alive>
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
            resources: this.storedResources,
            addResource: this.addResource,
            deleteResource: this.removeResource
        }
    },
    methods:{
        setSelectedTab(tab){
            this.selectedTab = tab;
        },
        addResource(title, description, url){
            const newResource = {
                id: new Date().toISOString,
                title : title,
                description : description,
                link: url
            };
            this.storedResources.unshift(newResource);
            this.selectedTab = 'stored-resources';
        },
        removeResource(resId){
            //finds the array id of the object based off of id
            const resIndex = this.storedResources.findIndex(res=> res.id==resId)
            //splice removes the object at exactly its array index
            this.storedResources.splice(resIndex,1)
        }
    }
}
</script>

<template>
    <stored-resources
    :resources="storedResources"
    ></stored-resources>
</template>

<script>
// import LearningResource from './components/learning-resources/LearningResource.vue'
import StoredResources from './components/learning-resources/StoredResources.vue'
export default{
    components: {
        StoredResources,
     },
    data(){
        return{
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
        }
    }
}
</script>
<style>
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

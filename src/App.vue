<template>
    <ul>
        <learning-resource v-for="resource in storedResources" :key="resource.id"></learning-resource>
        <!-- why create a separate component instead of markup here? -->
        <!-- there is no hard rull for when a component is better -->
        <!-- list items thru which you loop are a good candidate for smaller component -->
    </ul>
</template>

<script>
import LearningResource from './components/learning-resources/LearningResource.vue'
export default{
    components: {

        LearningResource

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

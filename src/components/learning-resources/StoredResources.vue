<template>
    <ul>
        <learning-resource v-for="resource in resources" 
        :key="resource.id"
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"></learning-resource>
        <!-- why create a separate component instead of markup here? -->
        <!-- there is no hard rull for when a component is better -->
        <!-- list items thru which you loop are a good candidate for smaller component -->
    </ul>
</template>
<script>
import LearningResource from './LearningResource.vue'
export default {
    components:{LearningResource},
    inject:['resources']
}
</script>
<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
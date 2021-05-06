<template>
    <the-header title="Remember Me"></the-header>
    <the-resources></the-resources>
    <!-- <stored-resources
    :resources="storedResources"
    ></stored-resources> -->
</template>

<script>
// import LearningResource from './components/learning-resources/LearningResource.vue'ß
import TheHeader from './components/layouts/TheHeader.vue'
import TheResources from './components/learning-resources/TheResources'
export default{
    components: {
        TheHeader,
        TheResources
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

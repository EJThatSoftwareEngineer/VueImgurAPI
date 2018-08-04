<template>
    <div>
        <div v-if="isLoggedIn" class="image-container">
            <img v-for="image in allImages" :src="image.link" :key="image.id" />
        </div>
        <h2 v-else>Please Log-In</h2>
    </div>
</template>

<script>

import {mapActions, mapGetters} from 'vuex';

export default {
    name:'ImageList',
    computed: mapGetters(['allImages','isLoggedIn']),
    methods:mapActions(['fetchImages']),
    created(){
        this.fetchImages();
    }
}
</script>

<style scoped>
.image-container {
    column-count: 2;
    column-gap: 0;
}

img {
    max-width: 100%;
    padding: 5px;
}

</style>



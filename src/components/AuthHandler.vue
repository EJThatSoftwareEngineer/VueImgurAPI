<template>
    <div>
        Please wait...
    </div>
</template>

<script>

import {mapActions} from 'vuex';

export default {
    
    name:'AuthHandler',
    methods: mapActions(['finalizedLogin']),
    //Life Cycle Method
    created(){
        this.finalizedLogin(window.location.hash);
    }
}
</script>

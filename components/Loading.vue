<template>
    <div class="loading">
        <img src="@/assets/logo.png" alt="logo">
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
    .loading{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100vh;
        background: rgba(0,0,0,.98);
        z-index: 1000000;
        position: absolute;
        top: 0;
        left: 0;
        transition: .2s all ;
    }
</style>
<template>
    <div class="card">
        <img :src="cover" alt="">
        <div class="content">
            <h2>{{title}}</h2>
            <span v-for="(tec, index) in tecs" :key="index">{{tec}}</span>
            <div class="links">
                <a :href="link" target="_blank">View Web</a>
                <a :href="github" target="_blank">Github</a>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        props:{
            title:String,
            cover: String,
            link: String,
            github: String,
            tecs: Array
        }
    }
</script>

<style lang="scss" scoped>
    .card{
        width: 100%;
        height: 300px;
        border: 1px #fff solid;
        color: #fff;
        margin: 1.5em 0;
        display: flex;
        overflow: hidden;
        border-radius: 15px;
        @media (max-width:992px){
            // width: 100%;
            height: auto;
            flex-direction: column;
        }
    }
    img{
        width: 60%;
        height: 100%;
        object-fit: cover;
        transition: cubic-bezier(0.075, 0.82, 0.165, 1) 2s;
        // clip-path: polygon(0 0, 90% 0, 76% 100%, 0% 100%);
        &:hover{
            // clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
        }
        @media (max-width:992px){
            width: 100%;
            height: 180px;
        }
    }
    .content{
        width: 40%;
        // background-color: aqua;
        padding: 2em;
        h2{
            margin-bottom: 1em;
            @media (max-width:992px){
                margin-bottom: .5em;
            }
        }
        span{
            background: #fff;
            color: #000;
            border-radius: 10px;
            margin-right: 1em;
            padding: .2em .6em;
            font-size: .8em;
            font-weight: bold;
        }
        .links{
            // background: chartreuse;
            display: flex;
            // justify-content: space-around;
            justify-content: space-between;
            // justify-content: space-evenly;
            margin-top: 2em;
            @media (max-width:992px){
                margin-top: 1em;
            }
            a{
                text-decoration: none;
                color: #fff;
                border: 1px solid #fff;
                padding: .5em 2em;
                transition: .2s all ease;
                border-radius: 15px;
                &:hover{
                    background: #fff;
                    color: #000;
                    
                }
            }
        }
        @media (max-width:992px){
            width: 100%;
            padding: 1em;
        }
    }
</style>
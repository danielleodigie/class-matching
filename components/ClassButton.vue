<template>
    <div id="classbuttonwrapper">
        <a id="classbutton"> {{ classcode }} </a>
    </div>
</template>

<script>
    export default{
        props: {
            classcode: String
        }
    }
</script>

<style>
    #classbuttonwrapper{
        max-width: 50px;
    }
    #classbutton {
        color: whitesmoke;
        padding: 10px;
        border-radius: 11px;
        background: rgb(23, 38, 100);
        font-size: 12px;
        text-decoration: none;
        font-family: Montserrat;
        word-wrap: break-word; 
        margin: 0;
    }
</style>
<template>
    <div>
        <a href="#" id="classbutton"> {{ classcode }} </a>
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
    #classbutton {
        color: whitesmoke;
        padding: 10px;
        border-radius: 11px;
        background: rgb(23, 38, 100);
        font-size: 14px;
        text-decoration: none;
        font-family: Verdana;
    }
</style>
<template>
    <div id="card">
        <div id="namearea">
            <h2>{{ name }}</h2>
            <p id="uni"> Uni: {{ uni }}</p>
            <p> Email: {{ email }}</p>
            <p> Phone: {{ phone }}</p>
        </div>
        <div id="classarea">
            <h2>Classes:</h2>
            <li v-for="classcode in classes"> <ClassButton :classcode="classcode"></ClassButton> </li>
        </div>
    </div>
</template>

<script>
import ClassButton from './ClassButton.vue';

    export default{
    props: {
        name: String,
        uni: String,
        email: String,
        phone: String,
        classes: Array
    },
    components: { ClassButton }
}
</script>

<style>
    @import url(https://fonts.googleapis.com/css2?family=Montserrat:wght@300&family=Raleway:wght@300;600&display=swap);
    #card{
        overflow: auto;
        width: 300px;
        height: 180px;
        color: #233a60;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        margin: 20px;
        padding: 15px;
        border-radius: 13px;
        background: #d1dff6;
        box-shadow: inset 7px 7px 14px #b0bbcf,
                    inset -7px -7px 14px #f2ffff;
    }

    #namearea{
        font-family: Raleway;
    }

    #namearea h2{
        font-weight: bold;
        font-size: 16px;
    }

    #namearea p{
        font-size: 12px;
    }

    #classarea{
        display: flex;
        flex-direction: column;
        justify-content: center;
        font-family: Raleway;
        
    }
    
    #classarea h2{
        font-size: 18px;
        text-align: center;
    }
    #classarea li{
        margin: 10px;
        white-space: nowrap;
        list-style: none;
    }
</style>
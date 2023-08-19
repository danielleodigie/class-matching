<template>
    <div id="home">
        <div id="welcome">
            <h1>ClassMatch</h1>
            <p>by your friends at ColorStack @ Columbia</p>
        </div>
        <div id="nav">
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSfVrvqj0SN2qr2hyW5jZoP27JOIIiL9IqnhF8nsGPme6vmjIA/viewform?usp=sf_link" class="navbutton"> Fill out our matching form!</a>
            <nuxt-link to="classes" class="navbutton"> Already did? Head in!</nuxt-link>
        </div>
        <div id="links">
            <a href="https://github.com/danielleodigie" class="linkbutton">GitHub</a>
            <a href="https://www.colorstack.org" class="linkbutton">Join Colorstack</a>
        </div>
    </div>
</template>

<style>
    #home{
        display: flex;
        flex-direction: column;
        
    }

    #welcome{
        position: absolute;
        top: 40%;
        left: 50%;
        transform: translate(-50%, -50%);
        padding: 10px;
        text-align: center;
        font-family: Raleway;
        color: #233a60;
    }

    #welcome h1{
        font-size: 96px;
        margin-bottom: 10px;
    }

    #nav{
        position: absolute;
        top: 70%;
        left: 50%;
        transform: translate(-50%, -50%);
        padding: 10px;
        text-align: center;

    }

    .navbutton{
        border-radius: 13px;
        background: #d1dff6;
        box-shadow: inset 6px 6px 12px #b4c0d4,
                    inset -6px -6px 12px #eefeff;
        color: #233a60;
        padding: 25px;
        font-family: Raleway;
        text-decoration: none;
        margin: 20px;
        transition: 300ms;
    }
    
    .navbutton:hover{

        border-radius: 13px;
        box-shadow: inset 19px 19px 38px #b0bbcf,
            inset -19px -19px 38px #f2ffff;
        transition: 300ms;
    }

    #links{
        position: absolute;
        top: 90%;
        left: 50%;
        transform: translate(-50%, -50%);
        padding: 10px;
        text-align: center;
    }

    .linkbutton{
        margin: 15px;
        text-decoration: none;
        color: #233a60;
        transition: 500ms;
    }

    .linkbutton:hover{
        transform: 500ms;
        font-size: 18px;
    }

    @media only screen and (max-width: 768px) {
        #home{
            display: flex;
            flex-direction: column;
        }
        
        #welcome h1{
            font-size: 48px;
            margin-bottom: 10px;
        }

        #links{
            width: 300px;
        }

    }

</style>
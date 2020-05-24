<template>
    <div class="home row">
        <div class="col-md-3">
            <span class="hipster img-fluid rounded"></span>
        </div>
        <div class="col-md-9">
            <h1 class="display-4">开始你的游戏之旅</h1>

            <div class="logIn">
                <div class="alert alert-success" v-if="authenticated">
                    <span v-if="username">You are logged in as user "{{username}}"</span>
                </div>

                <div class="alert alert-warning" v-if="!authenticated">
                    <span>If you want to </span>
                    <a class="alert-link" v-on:click="openLogin()">sign in</a><span >, you can try the default accounts:<br/>- Administrator (login="admin" and password="admin") <br/>- User (login="user" and password="user").</span>
                </div>
                <div class="alert alert-warning" v-if="!authenticated">
                    <span>You don't have an account yet?</span>&nbsp;
                    <router-link class="alert-link" to="/register">Register a new account</router-link>
                </div>
            </div>
            <div class="linkBox">
                <router-link class="myLink1" to="/rasianBlock">俄罗斯方块</router-link>
                <router-link class="myLink" to="/numsCom">2048</router-link>
            </div>
        </div>
    </div>
</template>

<script lang="ts" src="./home.component.ts">
</script>

<style>
    .logIn{
        margin-top: 30px;
    }

    .linkBox{
        display:flex;
    }

    h1{
        font-weight: normal;
    }

    .myLink{
        color: #fff;
        font-size: 40px;
        margin-left: 100px;
    }

    .myLink1{
        color: #fff;
        font-size: 40px;
    }
</style>

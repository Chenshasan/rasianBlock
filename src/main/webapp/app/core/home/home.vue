<template>
    <div class="home row">
        <div class="col-md-12">
            <h1 class="display-4">开始你的游戏之旅</h1>

            <div class="logIn">
                <div class="alert alert-success" v-if="authenticated">
                    <span class="suc" v-if="username">You are logged in as user "{{username}}"</span>
                    <br>
                    <a class="myLink1" href="/content/rasianBlock.html">俄罗斯方块</a>
                    <a class="myLink" href="/content/2048.html">2048</a>
                        <!-- 后端通过虚拟路径实现本地访问跳转 -->
                        <!--                 <iframe src="../../../outerHTML/2048.html"></iframe>
                         -->
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
        </div>
    </div>
</template>

<script lang="ts" src="./home.component.ts">
</script>

<style>
    .suc{
        font-size: 30px;
    }

    .home{
        margin-top: 150px;
        text-align: center;
    }
    .logIn{
        margin-top: 30px;
    }

    .linkBox{
        display:flex;
        text-align: center;
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

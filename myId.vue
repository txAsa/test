<template>
    <div>
        <el-row class='headerphone'>
            <el-col :span="12">
                <a href="#">
                    <div @click='goback'>&lt;</div>
                </a>
            </el-col>
            <el-col :span="22">
                <div class="grid-content bg-purple-light">手机号登录</div>
            </el-col>
        </el-row>
        <form :action='IP+ "/wylogin"' method="POST">
            <div>
                <input type="text" class='inputSty' placeholder="手机号" name='phone' />
            </div>
            <div>
                <input type="password" class='inputSty' placeholder="密码" name='pwd' />
            </div>
            <button>登录</button>
            <div class='goReg' @click='goreg'>新手注册</div>
        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                IP: 'http://192.168.43.49:3001'
            }
        },
        methods: {
            goreg() {
                this.$router.push({
                    path: '/phoneReg',
                })
            },
            // 后退
            goback() {
                this.$router.push({
                    path: '/Wymusic/findmusic',
                })
            }
        }
    }

</script>

<style scoped>
    .headerphone {
        background: red;
        display: flex;
        align-items: center;
        justify-content: center;
        height: 4rem;
        font-size: 1.4rem;
        color: white;
        margin-bottom: 1rem
    }

    form {
        text-align: center
    }

    .inputSty {
        width: 95%;
        height: 4rem;
        font-size: 1.2rem;
        text-indent: 1rem;
        outline: none;
        border-top: none;
        border-left: none;
        border-right: none;
    }

    button {
        width: 95%;
        height: 3rem;
        margin-top: 2rem;
        border: none;
        border-radius: 2rem;
        font-size: 1.2rem;
        color: white;
        background: red;
        margin-bottom: 1.8rem;
    }

    .goReg {
        color: gray;
        text-decoration: none
    }
</style>
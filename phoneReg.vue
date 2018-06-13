<template>
    <div>
        <el-row class='headerphone'>
            <el-col :span="12">
                <a href="#">
                    <div @click='forward'>&lt;</div>
                </a>
            </el-col>
            <el-col :span="22">
                <div class="grid-content bg-purple-light">手机号注册</div>
            </el-col>
        </el-row>
        <form :action='IP+ "/wyreg"' method="POST">
            <div>
                <input type="text" class='inputSty' placeholder="+86 输入手机号" name='phone' />
            </div>
            <div>
                <input type="password" class='inputSty' placeholder="设置登录密码，不少于6位" name='pwd' />
            </div>
            <button>注册</button>
        </form>
        <div class='footerway'>
            <div class='other'>其他注册方式</div>
            <div class='otherImg'>
                <div>
                    <div class='tuimg'>图</div>微信
                </div>
                <div>
                    <div class='tuimg'>图</div>QQ
                </div>
                <div>
                    <div class='tuimg'>图</div>微博
                </div>
                <div>
                    <div class='tuimg'>图</div>网易邮箱
                </div>
            </div>
        </div>
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
            forward() {
                this.$router.push({
                    path: '/myId',
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

    .otherImg {
        display: flex;
        justify-content: space-around;
        margin-top: 1rem;
        text-align: center;

    }

    .tuimg {
        width: 4rem;
        height: 4rem;
        border: 0.01rem solid;
        border-radius: 50%
    }

    /* .footerway {
        position: fixed;
        bottom: 0;
    } */

    .other {
        display: flex;
        justify-content: center;
        margin-top: 6rem
    }
</style>
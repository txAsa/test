<template>
    <div class='bodycolor'>
        <el-row class="sss">
            <el-col :span="10">
                账号
            </el-col>
        </el-row>
        <div class='headerImg'>
            <div>
                <img src="" alt="" class='photoimg'>
            </div>
            <div>
                <label for=""> sadasd</label>
                <div>sdasdas</div>
            </div>
            <div>
                <button @click='loginBtn'>登录</button>
            </div>
        </div>
        <!-- 动态 -->
        <div class='lookdong'>
            <div>动态
                <div>1</div>
            </div>
            <label for="" class='smallsu'> </label>
            <div>动态
                <div>1</div>
            </div>
            <label for="" class='smallsu'></label>
            <div>动态
                <div>1</div>
            </div>
            <label for="" class='smallsu'></label>
            <div>
                <div>
                    <img class='myimg' src="../../../assets/mymes.png" alt="sda">
                </div> 我的资料
            </div>
        </div>
        <!-- 我的消息 -->
        <div class='mymes'>
            <div>
                <img class='myimg' src="../../../assets/mymes.png" alt="ss">
            </div>
            <div>我的消息</div>
            <div>
                &gt;
            </div>
        </div>
        <!-- 会员中心 -->
        <div class='vipshop'>
            <div class='myvip'>
                <div>
                    <img class='myimg' src="../../../assets/vip.png" alt="dd">
                </div>
                <div>会员中心</div>
                <div>&gt;</div>
            </div>
            <div class='myvip'>
                <div>
                    <img class='myimg' src="../../../assets/mall.png" alt="dd">
                </div>
                <div>商城</div>
                <div>&gt;</div>
            </div>
            <div class='myvip'>
                <div>
                    <img class='myimg' src="../../../assets/listen.png" alt="dd">
                </div>
                <div>在线听歌不免费</div>
                <div>&gt;</div>
            </div>
        </div>
        <!-- 设置少一勺 -->
        <div class='set'>
            <div class='myset'>
                <div>
                    <img class='myimg' src="../../../assets/set.png" alt="dd">
                </div>
                <div>设置</div>
                <div>&gt;</div>
            </div>
            <div class='myset'>
                <div>
                    <img class='myimg' src="../../../assets/sao.png" alt="dd">
                </div>
                <div>扫一扫</div>
                <div>&gt;</div>
            </div>
            <div class='myset'>
                <div>
                    <img class='myimg' src="../../../assets/change.png" alt="dd">
                </div>
                <div>个性换肤</div>
                <div>&gt;</div>
            </div>
            <div class='myset'>
                <div>
                    <img class='myimg' src="../../../assets/tongier.png" alt="dd">
                </div>
                <div>夜间模式</div>
                <div>&gt;</div>
            </div>
            <div class='myset'>
                <div>
                    <img class='myimg' src="../../../assets/timer.png" alt="dd">
                </div>
                <div>定时关闭</div>
                <div>&gt;</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            loginBtn() {
                this.$router.push({
                    path: '/myId',
                })
            }
        }
    }
</script>


<style scoped>
    .bodycolor {
        background: rgb(221, 218, 218)
    }

    .sss {
        background: red;
        height: 4rem;
        line-height: 4rem;
        text-align: center;
        display: flex;
        justify-content: space-around;
        font-size: 1.2rem;
        color: white
    }

    .headerImg {
        border-bottom: 0.01rem solid rgb(226, 222, 222);
        ;
        height: 6rem;
        display: flex;
        align-items: center;
        background: white
    }

    .headerImg>div {
        margin: 0 0.3rem;
    }

    .headerImg>div:nth-child(3) {
        margin-left: auto;
    }

    button {
        width: 3.5rem;
        height: 1.8rem;
        border-radius: 2rem;
        border: 0.01rem solid red;
        outline: none;
        background: white;
        color: red;
    }

    .photoimg {
        width: 4.5rem;
        height: 4.5rem;
        border: 0.01rem solid;
        border-radius: 50%;

    }

    .smallsu {
        border-right: 0.01rem solid rgb(163, 160, 160);
        height: 1.8rem;
    }

    .lookdong {
        border-bottom: 0.01rem solid rgb(173, 172, 172);
        height: 3rem;
        display: flex;
        justify-content: space-around;
        align-items: center;
        text-align: center;
        background: white
    }

    .lookdong>div {
        color: rgb(173, 173, 173);
    }

    .lookdong>div>div {
        color: black
    }

    .mymes {
        margin-top: 0.5rem;
        height: 3rem;
        background: white;
        display: flex;
        padding-left: 0.5rem;
        margin-bottom: 0.5rem;
        align-items: center
    }

    .mymes>div:last-child {
        margin-left: auto
    }

    .mymes>div {
        margin: 0 0.5rem
    }

    .myvip {
        height: 3rem;
        background: white;
        display: flex;
        border-bottom: 0.01rem solid rgb(226, 222, 222);
        padding-left: 0.5rem;
        align-items: center;
    }

    .myvip>div {
        margin: 0 0.5rem
    }

    .myvip>div:last-child {
        margin-left: auto
    }

    .vipshop {
        margin-bottom: 0.5rem
    }

    .myset {
        height: 3rem;
        background: white;
        display: flex;
        border-bottom: 0.01rem solid rgb(226, 222, 222);
        padding-left: 0.5rem;
        align-items: center;
    }

    .myset>div {
        margin: 0 0.5rem
    }

    .set {
        margin-bottom: 5rem
    }

    .myset>div:last-child {
        margin-left: auto
    }

    .myimg {
        width: 1.2rem;
    }
</style>
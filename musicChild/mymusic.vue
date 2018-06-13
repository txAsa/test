<template>
    <div>
        <el-row class="sss">
            <el-col :span="8">
                <div>更多</div>
            </el-col>
            <el-col :span="8">
                <div>我的音乐</div>
            </el-col>
            <el-col :span="8">
                <div>|||</div>
            </el-col>
        </el-row>

        <div class='mymusicge'>
            <div>
                <img src="../../../assets/mymes.png" alt="ss">
            </div>
            <div>本地音乐</div>
            <div>123&gt;</div>
        </div>
        <div class='mymusicge' @click='comedmusiced'>
            <div>
                <img src="../../../assets/mymes.png" alt="ss">
            </div>
            <div>最近播放</div>
            <div>123&gt;</div>
        </div>
        <div class='mymusicge'>
            <div>
                <img src="../../../assets/mymes.png" alt="ss">
            </div>
            <div>我的电台</div>
            <div>123&gt;</div>
        </div>
        <div class='mymusicge'>
            <div>
                <img src="../../../assets/mymes.png" alt="ss">
            </div>
            <div>我的收藏</div>
            <div>123&gt;</div>
        </div>
        <div class='savesong'>
            <div>&gt;</div>
            <div>
                <a href="">我创建的歌单</a>
            </div>
        </div>
        <div class='savesong'>
            <div>&gt;</div>
            <div>
                <a href=""> 我收藏的歌单</a>
            </div>
        </div>

    </div>
</template>

<script>    
    export default {
        methods: {
            //跳转路由到最近播放列表
            comedmusiced() {
                this.$router.push({
                    path: '/WYmusic/comedmusic',
                })
            }
        }
    }
</script>

<style scoped>
    .mymusicge {
        margin-left: 0.5rem;
        width: 95%;
        height: 3rem;
        border-bottom: 0.01rem solid rgb(218, 213, 213);
        display: flex;
        align-items: center;
        font-size: 1.2rem
    }

    .mymusicge>div {
        margin: 0 0.5rem
    }

    .mymusicge>:nth-of-type(3) {
        margin-left: auto;
        font-size: 1rem;
        color: gray
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

    .savesong {
        display: flex;
        align-items: center;
        height: 1.5rem;
        background: rgb(235, 230, 230);

    }

    .savesong>div {
        margin: 0 0.5rem;
    }

    a {
        text-decoration: none;
        color: rgb(151, 142, 142)
    }
</style>
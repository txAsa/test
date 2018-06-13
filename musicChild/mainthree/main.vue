<template>
    <div>
        <!--轮播-->
        <div class="block">
            <el-carousel height="150px">
                <el-carousel-item v-for="item in getLunbo" :key='item._id'>
                    <img class='banner1' :src="IP+item.banner" alt="s" />
                </el-carousel-item>
            </el-carousel>
        </div>

        <!-- 可遍历，先写4个占位置 -->
        <div class='owner'>
            <div>
                <img class='tui' src="../../../../assets/our.png" alt="">
                <div>私人FM</div>
            </div>
            <div>
                <img class='tui' src="../../../../assets/xihuan.png" alt="">
                <div>每日推荐</div>
            </div>
            <div>
                <img class='tui' src="../../../../assets/songlist.png" alt="">
                <div>歌单</div>
            </div>
            <div>
                <img class='tui' src="../../../../assets/paihang.png" alt="">
                <div>排行榜</div>
            </div>
        </div>

        <div>
            <div class='title'>
                <a href=""> 推荐歌单 ></a>
            </div>
            <!-- 推荐歌单 -->
            <div class='songs'>
                <div v-for='(item , index) in Allcomm'>
                    <img class='tuijianImg' :src="[IP+item.img]" @click='changeSong(item._id)' alt="ss">
                    <div class="tag">{{item.title}}</div>
                </div>

            </div>
        </div>
    </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                IP: "http://192.168.43.49:3001",
                ind: 0
            }
        },
        beforeCreate() {
            //请求轮播图片
            return this.$store.dispatch({
                type: 'music_lunbo',
            })
        },
        created() {
            return this.$store.dispatch({
                type: 'music_gettuijian',
            })

        },
        computed: {
            // 获取6个推荐歌单
            Allcomm() {
                return this.$store.state.Allmusic.musicComm
            },
            // 轮播
            getLunbo() {
                return this.$store.state.Allmusic.lunbo
            }
        },
        methods: {
            changeSong(id) {
                console.log(id)
                this.$router.push({
                    path: '/WYmusic/songlist',
                    query: { plan: id }
                })
            }
        }

    }
</script>

<style scoped>
    .title {
        border-left: 0.2rem solid red;
        padding-left: 0.5rem;
        margin: 0.8rem 0;
    }

    a {
        text-decoration: none;
        color: black;
        font-size: 1.1rem
    }

    .tuijianImg {
        width: 7.25rem;
        height: 7.25rem;
        margin: 0 0.1rem
    }

    .tui {
        width: 3rem;
    }

    .search {
        width: 100%;
        height: 2rem;
        background: red;
        display: flex;
        justify-content: space-around;
        align-items: center
    }

    /* .inputSearch {
        width: 80%;
        height: 1.8rem;
        border-radius: 1rem;
        border: none;
        outline: none;
        text-indent: 0.5rem;
    } */

    .clear {
        padding: 0;
    }

    .owner {
        display: flex;
        height: 5rem;
        align-items: center;
        justify-content: space-between;
    }

    .owner>div {
        width: 30%;
        height: 4rem;
        text-align: center
    }

    .songs {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        margin-bottom: 5rem
    }

    .tag {
        width: 6rem;
        font-size: 0.8rem;
        margin: 0 0.5rem
    }

    .bg-purple {
        background: #d3dce6;
        line-height: 2rem
    }

    .bg-purple-light {
        background: #e5e9f2;
        line-height: 2rem
    }

    .grid-content {
        min-height: 2rem;

    }

    .banner1 {
        height: 8.5rem;
        width: 100%
    }














    .el-header,
    .el-footer {
        color: #333;
        text-align: center;
        line-height: 2.5rem;
    }

    .el-main {
        color: #333;
        text-align: center;
    }
</style>
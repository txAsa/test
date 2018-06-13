<template>
    <div>
        <el-container>
            <el-header class='search'>
                <!-- 搜索框 -->
                <div>
                    <img class='mai' src="../../../assets/find_listen.png" alt="">
                </div>
                <div>
                    <el-input placeholder="搜索音乐、视频、歌词、电台" v-model="input5" class="input-with-select">
                        <el-button slot="append" icon="el-icon-search" @click='searchBtn'></el-button>
                    </el-input>
                </div>
                <div>
                    <img class='mai' src="../../../assets/find_play.png" alt="">
                </div>
            </el-header>
            <el-main class='clear'>
                <el-row>
                    <el-col :span="8">
                        <router-link to="/Wymusic/findmusic/main">
                            <div class="grid-content">音乐</div>
                        </router-link>
                    </el-col>
                    <el-col :span="8">
                        <router-link to="/Wymusic/findmusic/movies">
                            <div class="grid-content">影视</div>
                        </router-link>
                    </el-col>
                    <el-col :span="8">
                        <router-link to="/Wymusic/findmusic/station">
                            <div class="grid-content">电台</div>
                        </router-link>
                    </el-col>
                </el-row>
            </el-main>
        </el-container>
        <div>
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                input5: '',
            }
        },
        //     beforeCreate() {
        //     },
        //     created() {
        //         setInterval(() => {
        //             this.ind++;
        //             if (this.ind == 4) {
        //                 this.ind = 0;
        //             }
        //         }, 1000);
        //         return this.$store.dispatch({
        //             type: 'music_gettuijian',
        //         })

        //     },
        //     computed: {
        //         // 获取6个推荐歌单
        //         Allcomm() {
        //             return this.$store.state.Allmusic.musicComm
        //         }
        //     },
        methods: {
            searchBtn() {
                this.$store.dispatch({
                    type: 'music_search',
                    data: this.input5
                })
                this.$router.push({
                    path: '/WYmusic/searchsong',
                    query: { plan: this.input5 }
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
        width: 6.5rem;
        height: 6.5rem;
        margin: 0 0.1rem
    }

    .search {
        width: 100%;
        height: 2rem;
        background: red;
        display: flex;
        justify-content: space-around;
        align-items: center;
    }

    .inputSearch {
        width: 80%;
        height: 1.8rem;
        border-radius: 1rem;
        border: none;
        outline: none;
        text-indent: 0.5rem;
    }

    .clear {
        padding: 0;
    }

    .owner {
        display: flex;
        height: 5rem;
        background: blueviolet;
        align-items: center;
        justify-content: space-between;
    }

    .owner>div {
        width: 30%;
        height: 4rem;
        outline: 0.1rem solid;

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


    .grid-content {
        min-height: 2rem;
        line-height: 2rem;
        background: rgb(204, 203, 203)
    }

    .banner1 {
        height: 8.5rem;
        width: 100%
    }

    .mai {
        width: 1.5rem;
        height: 1.5rem;
        margin-top: 1rem;
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
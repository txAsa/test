<template>
    <div>
        <el-container>
            <el-header class='search'>
                <!-- 搜索框 -->
                <div>
                    <img class='mai' src="../../../assets/find_listen.png" alt="">
                </div>
                <div>
                    <el-input placeholder="搜索音乐、视频、歌词、电台" v-model="input8" class="input-with-select">
                        <el-button slot="append" icon="el-icon-search" @click='searchmusic'></el-button>
                    </el-input>
                </div>
                <div>
                    <img class='mai' src="../../../assets/find_play.png" alt="">
                </div>
            </el-header>
            <!-- <div class='userselect'>
                <div>单曲</div>
                <div>歌手</div>
                <div>专辑</div>
                <div>歌单</div>
                <div>视频</div>
            </div> -->
            <el-tabs v-model="activeName" @tab-click="handleClick">
                <el-tab-pane label="单曲" name="first">
                    <div>
                        <div v-if='getsersong.length==0'>无相关歌曲信息-_-</div>
                        <div class='searlist' v-for='(item,index) in getsersong' @click='playsong(item._id)'>

                            <div> {{item.name}}
                                <div class='singername'> {{item.singer}} </div>

                            </div>

                        </div>
                    </div>

                </el-tab-pane>
                <el-tab-pane label="歌手" name="second">配置管理</el-tab-pane>
                <el-tab-pane label="专辑" name="third">角色管理</el-tab-pane>
                <el-tab-pane label="歌单" name="fourth">定时任务补偿</el-tab-pane>
            </el-tabs>
        </el-container>
        <!-- {{getsersong}} -->

    </div>
</template>

<script>
    export default {
        data() {
            return {
                activeName: 'first',
                input8: '',
                songname: ''
            }
        },
        computed: {
            getsersong() {
                return this.$store.state.Allmusic.allsing
            }
        },
        created() {

        },
        methods: {
            playsong(id) {
                this.$router.push({
                    path: '/playmusic',
                    query: { plan: id }
                })
            },
            handleClick(tab, event) {
                console.log(tab, event);
            },
            searchmusic() {
                this.$store.dispatch({
                    type: 'music_search',
                    data: this.input8
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

    .search {
        width: 100%;
        height: 2rem;
        background: red;
        display: flex;
        justify-content: space-around;
        align-items: center;
    }

    .mai {
        width: 1.5rem;
        height: 1.5rem;
        margin-top: 1rem;
    }

    .userselect {
        /* width: 100%; */
        height: 3rem;
        display: flex;
        overflow: auto;
        align-items: center;
        justify-content: space-around;
        background: rgb(226, 219, 219)
    }

    .searlist {
        height: 3rem;
        background: ghostwhite;
        display: flex;
        align-items: center;
        padding-left: 2rem;
        border-bottom: 0.01rem solid rgb(212, 201, 201)
    }

    .singername {
        font-size: 0.8rem;
        color: rgb(146, 140, 140)
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
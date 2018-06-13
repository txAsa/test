<template>
    <div>
        <el-row class="sss">
            <el-col :span="6">
                <div @click='forw'>&lt;</div>
            </el-col>
            <el-col :span="12">
                <div>最近播放的歌曲</div>
            </el-col>
            <el-col :span="6">
                <div>|||</div>
            </el-col>
        </el-row>
        <!-- {{allmusic}} -->
        <div>
            <div class='comed' v-for='(item , index) in allmusic' @click='played(item._id)'>
                <div>{{item.name}}
                    <div class='fssty'>{{item.singer}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>    
    export default {
        created() {
            this.$store.dispatch({
                type: 'music_comedall',
            })
        },
        computed: {
            allmusic() {
                return this.$store.state.Allmusic.allsing
            }
        },
        methods: {
            played(id) {
                this.$router.push({
                    path: '/playmusic',
                    query: { plan: id }
                })
            },
            // 返回上一页
            forw() {
                history.go(-1)
            }

        }
    }
</script>

<style scoped>
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

    .comed {
        width: 90%;
        height: 3rem;
        border-bottom: 0.01rem solid rgb(216, 213, 213);
        margin: 0 auto;
        display: flex;
        align-items: center
    }

    .fssty {
        font-size: 0.8rem;
        color: rgb(167, 167, 167)
    }

    /* a {
        text-decoration: none;
        color: rgb(151, 142, 142)
    } */
</style>
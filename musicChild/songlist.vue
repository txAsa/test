<template>
    <div class='outout'>
        <div class='outbox'>
            <div class='ss'>歌单</div>
            <div class="titleIMG">
                <div>
                    <img class='photoimg' :src="[IP+getsongs.img]" alt="">
                </div>
                <div>
                    {{getsongs.title}}
                </div>
            </div>
            <div class='changeNeed'>
                <div>3321</div>
                <div>30</div>
                <div>27</div>
                <div>下载</div>
            </div>
        </div>
        <div class='autortag'>
            <div>标签：{{getsongs.tag+""}}</div>
            <div>简介：{{getsongs.intro}}</div>
        </div>
        <div class='songlistflex' v-for='(item,index) in getsongs.song' @click='playmusic(item._id)'>
            <div class='clickSong'>{{index+1}}</div>

            <div class='table'>
                {{item.name}}
                <div class='autor'>{{item.singer}} - {{item.album}}</div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                ids: '',
                IP: "http://192.168.43.49:3001",
                arr: []
            }
        },
        created() {
            // for (let i = 0; i < this.getsongs.song.length; i++) {
            // this.arr.push(this.getsongs.song[i])
            // }
            // console.log(this.arr, 'sadsadsdasdas')

            // 拿到对应歌单id
            this.ids = (window.location.hash).replace('#/WYmusic/songlist?plan=', '')
            return this.$store.dispatch({
                type: 'music_list',
                id: this.ids
            })
        },
        computed: {
            //获取对应歌单的歌曲
            getsongs() {
                return this.$store.state.Allmusic.songlists
            }
        },
        methods: {

            playmusic(id) {
                for (let i = 0; i < this.getsongs.song.length; i++) {
                    this.arr.push(this.getsongs.song[i])
                }
                this.$store.commit({
                    type: 'music_alls',
                    data: this.arr
                })
                // console.log(this.arr, 'sadsadsdasdas')
                this.$router.push({
                    path: '/playmusic',
                    query: { plan: id }
                })
            }
        }
    }
</script>

<style scoped>
    .outbox {
        height: 15rem;
        background: rgba(12, 9, 9, 0.589);
        color: rgb(230, 225, 225)
    }

    .ss {
        text-align: center;
        font-size: 1.2rem;
    }

    .photoimg {
        width: 8rem;
        height: 8rem;
        margin: 1rem
    }

    .titleIMG {
        display: flex;
        align-items: center
    }

    .changeNeed {
        display: flex;
        justify-content: space-around
    }

    .changeNeed>div {
        width: 20%;
        height: 2.8rem;
        border: 0.01rem solid;
        text-align: center;
        line-height: 2.8rem
    }

    .table {
        width: 95%;
        margin-left: 1rem;
        border-bottom: 0.01rem solid gainsboro;
        height: 3rem;
        font-size: 1rem;

    }

    .songlistflex {
        display: flex;
        font-size: 1.2rem;

    }

    .autor {
        font-size: 0.8rem;
        color: gray
    }

    .clickSong {
        line-height: 3rem;
        color: gray
    }

    .autortag {
        height: 6rem;
        padding: 0.5rem;
        border-bottom: 0.01rem solid rgb(219, 219, 219)
    }

    .outout {
        margin-bottom: 4.5rem
    }
</style>
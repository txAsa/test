<template>
    <div>
        <header class='header'>
            <div @click='gobackup'>
                &lt;&lt;
            </div>
            <div class='thema'>
                {{aiai[index].name}}
                <div class='singer'>{{aiai[index].singer}}</div>
            </div>
            <div>分享</div>
        </header>
        <div class='main'>
            <img class='songerimg' :src="IP+aiai[index].img" alt="">
            <audio id='play' :src="IP+aiai[index].song_src" controls autoplay="autoplay"></audio>
            <div class='begin'>
                <div>
                    <img src="../../assets/upsong.png" alt="dsa" @click='upsong'>
                </div>
                <div>
                    <img src="../../assets/play.png" alt="das" @click='playsong' v-if='isPlay==false'>
                    <img src="../../assets/bengin.png" alt="das" @click='playsong' v-if='isPlay==true'>
                </div>
                <div>
                    <img src="../../assets/downsong.png" alt="d" @click='downsong'>
                </div>
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
                isPlay: false,
                all: [],
                upsongs: [],
                index: 0,
                // songarr: []
            }
        },

        created() {
            //最近播放歌曲（每当歌游播放一次就会记录一次保存到数据库，后面再做去重）
            // this.$store.dispatch({
            //     type: 'music_findrep',
            //     arr: "",
            // })


            // 拿到对应歌曲的id
            this.ids = (window.location.hash).replace('#/playmusic?plan=', '');
            // console.log(this.getpla.song, 'qweqwe')
            // if (this.getpla.length == 0) {
            // this.getpla = [this.getplaymusic]
            // }
            // else {
            for (let i = 0; i < this.aiai.length; i++) {
                if (this.aiai[i]._id == this.ids) {
                    console.log(this.aiai[i], '在这里');
                    //最近播放歌曲（每当歌游播放一次就会记录一次保存到数据库，后面再做去重）
                    this.$store.dispatch({
                        type: 'music_findrep',
                        data: this.aiai[i],
                    })

                    this.index = i;
                }
            }
            // }

            console.log(this.getpla)

            return this.$store.dispatch({
                type: 'music_list',
                id: this.ids
            })
        },
        computed: {
            // 获取进入之前的歌曲集合
            getpla() {
                //大的歌单
                return this.$store.state.Allmusic.songlists;
            },
            // 获取单个对应的歌曲
            getplaymusic() {
                // 对应的单个歌曲
                return this.$store.state.Allmusic.play;
            },
            // 对应的所有歌曲
            aiai() {
                return this.$store.state.Allmusic.allsing;
            }
        },
        methods: {
            // 返回上一页
            gobackup() {
                history.go(-1);
            },
            // 上一首
            upsong() {
                console.log(this.getplaymusic)
                // 控制放个
                if (this.index == 0) {
                    this.index = 0
                } else {
                    this.index = this.index - 1
                    this.$store.dispatch({
                        type: 'music_findrep',
                        data: this.aiai[this.index],
                    })
                }
            },
            //播放/暂停
            playsong() {
                var play = document.getElementById('play');
                if (this.isPlay == false) {
                    this.isPlay = true;
                    play.play();
                } else {
                    this.isPlay = false;
                    play.pause();
                }

            },
            // 下一首
            downsong() {
                if (this.aiai.length - 1 <= this.index) {
                    this.index = this.aiai.length - 1
                }
                else {
                    this.index = this.index + 1
                    this.$store.dispatch({
                        type: 'music_findrep',
                        data: this.aiai[this.index]
                    })
                }

            }
        }
    }
</script>

<style scoped>
    audio::-webkit-media-controls-panel {
        background: rgba(0, 0, 0, 0)
    }

    .thema {
        text-align: center
    }

    .songerimg {
        width: 16rem;
        border-radius: 50%;
        margin: 2.8rem auto;
        animation: zhuan linear 5s infinite;
    }

    @keyframes zhuan {
        0% {
            transform: rotate(0deg)
        }
        25% {
            transform: rotate(90deg)
        }
        50% {
            transform: rotate(180deg)
        }
        75% {
            transform: rotate(270deg)
        }
        100% {
            transform: rotate(360deg)
        }

    }

    .header {
        background-color: #B3C0D1;
        color: white;
        height: 3rem;
        display: flex;
        justify-content: space-between;
        align-items: center;

    }

    .singer {
        font-size: 0.7rem
    }

    .main {
        background-color: #E9EEF3;
        text-align: center;
    }

    .begin {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 6.8rem;
    }

    .begin>div {
        margin: 0 1rem
    }
</style>
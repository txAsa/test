<template>
    <div class='footer'>
        <div>
            <router-view ></router-view>
        </div>
        <div class='footChange'>
            <div>
                <router-link to="/Wymusic/findmusic" class='fsSty'>
                    <img class='chencked' src="../../assets/fin_icon.png" alt="">
                    <div>发现音乐</div>
                </router-link>
            </div>
            <div>
                <router-link to="/Wymusic/mymusic" class='fsSty'>
                    <img class='chencked' src="../../assets/find_play.png" alt="">
                    <div>我的音乐</div>
                </router-link>
            </div>
            <div>
                <router-link to="/Wymusic/friends" class='fsSty'>
                    <img class='chencked' src="../../assets/friend_icon.png" alt="">
                    <div>朋友</div>
                </router-link>
            </div>
            <div>
                <router-link to="/Wymusic/logined" class='fsSty'>
                    <img class='chencked' src="../../assets/acc_icon.png" alt="">
                    <div>账号</div>
                </router-link>
            </div>
        </div>
    </div>
</template>
<script>

    import axios from "axios";
    export default {
        // created() {
        //     axios.post('http://192.168.43.49:3001/getsmall', {}).then((data) => {
        //         console.log(data)
        //     })
        // }
        medthods: {
          
        }
    }
</script>


<style scoped>
    * {
        margin: 0;
        padding: 0;
    }

    .footer {
        position: relative;
    }

    .footChange {
        display: flex;
        width: 100%;
        background: rgba(0, 0, 0, 0.829);
        height: 4rem;
        justify-content: space-around;
        align-items: center;
        position: fixed;
        left: 0;
        bottom: 0;
        text-align: center;
    }

    .chencked {
        width: 2rem;

    }

    .fsSty {
        text-decoration: none;
        color: white;
        font-size: 0.8rem
    }
</style>
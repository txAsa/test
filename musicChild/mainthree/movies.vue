<template>
    <div class='mvall'>
        <div v-for='(item,index) in getmv' class='mvbox'>
            <video :src="[IP+item.mv]" controls class='videos'></video>
            <div>用小手拍出极致体验，完全OJBK</div>
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
        created() {
            return this.$store.dispatch({
                type: 'music_mv',
            })
        },
        computed: {
            getmv() {
                return this.$store.state.Allmusic.mv
            }
        }
    }
</script>

<style scoped>
    video::-webkit-media-controls-panel {
        background: rgba(0, 0, 0, 0)
    }

    .videos {
        width: 100%;
        height: 12.8rem;
    }

    .mvbox {
        margin-bottom: 1rem;
    }

    .mvall {
        margin-bottom: 5rem;
    }
</style>
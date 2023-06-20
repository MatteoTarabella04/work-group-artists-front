<script>
import axios from 'axios';

export default {
    data() {
        return {
            server:'http://127.0.0.1:8000/',
            end_point_artists: 'api/artists',
            artists:null
        }
    },
    mounted() {
        //todo call API
        axios
        .get(this.server + this.end_point_artists)
        .then(response => {
            console.log(response)
            this.artists = response.data.artists.data
        })
        .catch(error => {
            console.log(error)
        })
    }
}
</script>

<template>

<router-view></router-view>
</template>

<style lang="scss">
@use './styles/general.scss';

</style>

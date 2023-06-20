<script>
import AppHeader from '../components/AppHeader.vue';
import AppFooter from '../components/AppFooter.vue';
import ArtistCard from '../components/ArtistCard.vue';
import axios from 'axios';
export default {
    name: 'HomePage',
    components: {
        AppHeader,
        AppFooter,
        ArtistCard
    },
    data() {
        return {
            server: 'http://127.0.0.1:8000/',
            end_point_artists: 'api/artists',
            artists: []
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
    <div>
        <AppHeader></AppHeader>
        <div class="container">
            <h1 class="text-center py-2">Home Page</h1>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4">
                <ArtistCard v-for="artist in this.artists" :name="artist.name" :image="artist.image" :genre="artist.genre"
                    :birth_date="artist.birth_date"></ArtistCard>
            </div>
        </div>
        <AppFooter></AppFooter>
    </div>
</template>


<style lang="scss" scoped></style>
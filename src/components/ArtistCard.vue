
<script>
export default {
    name: 'Artist Card',
    props: {
        image: String,
        name: String,
        genre: String,
        birth_date: String,
    },
    data() {


        return {}
    }
}
</script>

<template>
    <div>
        <div class="card">
            <img class="card-img-top" :src="image" alt="Title">
            <div class="card-body">
                <h4 class="card-title">{{ name }}</h4>
                <h5 class="card-title"> {{ genre }} </h5>
                <p class="card-text">{{ birth_date }}</p>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>
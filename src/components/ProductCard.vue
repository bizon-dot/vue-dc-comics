<template>
    <div class="card">
        <div class="img-album">
            <img :src="prod.thumb">



        </div>
        <div class="title">
            <h4>{{ prod.series.toUpperCase()}}</h4>
        </div>


    </div>

</template>

<script>
    export default {
        name: 'ProductCard',
        props: ['prod'],
    }
</script>


<style lang="scss" scoped>
    @import './style/general.scss';

    .card {
        width: calc(100% / 4 - 30px);
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;

        .img-card {
            aspect-ratio: 1 / 1;
            /*  transition: $fast; */

            img {
                width: 50%;
                height: 100%;
                object-fit: cover;
                object-position: top;
            }


        }

        .title {
            color: whitesmoke;
            margin-top: 30px;
        }
    }
</style>
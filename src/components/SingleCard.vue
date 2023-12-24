<!-- HTML -->
<template lang="">
    <article class="p-0 text-uppercase fw-bold">
        <section class="image">
            <img :src="card.card_images[0].image_url" alt="">
        </section>
        <h3>
            {{card.name}}
        </h3>
        <p>
            {{card.archetype}}
        </p>
    </article>
</template>

<!-- JavaScript -->
<script>


export default {

    props: {
        card : {
            type : Object,
            require: true,
        }

    },

    
}


</script>

<!--SASS-->
<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;


    article {
        width: calc(100%  / 5 - 1rem);
        margin-left: .5rem;
        margin-right: .5rem;
        margin-bottom: 1rem;
        background-color: $primary-bg;
    }

    img{
        width: 100%;
        height: 100%;
    }
    
</style>
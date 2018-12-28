<template>
    <div class="main-carousel">
        <slot></slot>
    </div>
</template>

<script>
    import Flickity from 'flickity';
    import "flickity/dist/flickity.min.css";
    export default {
        props: {
            autoplay: { default: false},
            wraparound: {default: true}
        },
        mounted() {
            var flkty = new Flickity( '.main-carousel', {
              "cellAlign": "left",
              "contain": true,
              "autoPlay": this.autoplay,
              "wrapAround": this.wraparound

            });
        }
    }
</script>


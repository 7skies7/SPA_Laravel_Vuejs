<template>
    <div class="columns">
        <div class="column">
            <article class="message">
                <div class="message-header">
                    The Carousel Component With VUEJs
                </div>
                <div class="message-body">
                    <carousel :autoplay="true">
                        <img src="http://placeimg.com/640/480/any">
                        <img src="http://placeimg.com/640/480/any?2">
                        <img src="http://placeimg.com/640/480/any?3">
                        <img src="http://placeimg.com/640/480/any?4">
                        <img src="http://placeimg.com/640/480/any?5">
                    </carousel>
                    <amplify-confirm-sign-in v-bind:confirmSignInConfig="confirmSignInConfig"></amplify-confirm-sign-in>

                </div>
            </article>
        </div>       
    </div>

</template>

<script>
    import Carousel from '../Components/Carousel.vue';
    export default {
        components: { Carousel },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>


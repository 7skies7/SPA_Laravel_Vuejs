<template>
    
        <div class="columns">
            <div class="column">
                <article class="message" v-for="status in statuses">
                    <div class="message-header">
                        <p>{{ status.user.name }}</p>
                        <p> {{ status.created_at | ago }} </p>
                    </div>
                    <div class="message-body">
                        {{ status.body }}
                    </div>
                </article>
            </div>
            <div class="column">
            <add-to-stream @completed="addStatus"></add-to-stream></div>
        </div>

    
</template>

<script>
    import moment from 'moment';
    import Status from '../models/Status';
    import AddToStream from '../components/AddToStream.vue';
    export default {
        data() {
            return {
                statuses: []
            }
        },
        components: { AddToStream },
        filters: {
            ago(date) {
                return moment(date).fromNow();
            }
        },
        created() {
            Status.all(statuses => this.statuses = statuses)            
                // .then(({data}) => this.statuses = data)
        },
        methods: {
            addStatus(status) {
                this.statuses.unshift(status);
                alert("Your status has been added to the stream.");
            }
        }
    }
</script>

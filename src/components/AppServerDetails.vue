<template>
    <div class="pa-3">
        <h3>Updated Server Detail</h3>
        <p>{{ serverStatus }}</p>
    </div>
</template>

<script>
    import { eventBus } from '../main';

    export default {
        data() {
            return {
                serverStatus: 'Server Details are currently not updated.'
            }
        },
        methods: {
            statusWatch() {
                if(this.serverStatus === 'Server Details are currently not updated.') {
                    alert('hello');
                }
            }
        },
        created() {
            eventBus.$on('updated', (data) => {
                this.serverStatus = data;
            });
        }
    }
</script>

<style scoped>
    h3 {
        text-decoration: underline;
    }
</style>

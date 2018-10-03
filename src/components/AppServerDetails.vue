<template>
    <div class="pa-3">
        <p>Server Details are currently not updated</p>
        <p>{{ test }}</p>
    </div>
</template>

<script>
    import { eventBus } from '../main';

    export default {
        data() {
            return {
                test: 'whats up'
            }
        },
        created() {
            eventBus.$on('alerted', (data) => {
                this.test = data;
            });
        }
    }
</script>
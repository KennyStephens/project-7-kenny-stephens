<template>
    <div id="servers">
        <v-list class="pa-3">
            <v-list-tile
                @click="statusChange"
                v-for="server in serverList" :key="server.name">
                <v-icon color="amber accent-2" class="mr-1">computer</v-icon>
                {{ server.name }} - Status: {{ server.status }}
            </v-list-tile>
        </v-list>
        <button @click="doAlert">doAlert</button>
    </div>
</template>

<script>
    import { eventBus } from '../main';

    export default {
        data() {
            return {
                serverList: [
                    {name: 'Server #1', status: 'active'},
                    {name: 'Server #2', status: 'inactive'},
                    {name: 'Server #3', status: 'active'},
                    {name: 'Server #4', status: 'inactive'},
                    {name: 'Server #5', status: 'active'},
                ]
            }
        },
        methods: {
            doAlert() {
                eventBus.$emit('alerted', 'hello');
            }
        }
    }
</script>

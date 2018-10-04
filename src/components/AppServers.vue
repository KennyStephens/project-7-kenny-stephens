<template>
    <div id="servers">
        <v-list class="pa-3">
            <v-list-tile
                v-for="(server, i) in serverList" :key="i">
                <v-icon color="amber accent-2" class="mr-2">computer</v-icon>
                {{ server.Name }} - Status: {{ server.status }}
                <v-btn @click="statusChange(i)" small>Change Status</v-btn>
            </v-list-tile>
                <v-btn @click="updateServers" small light>Update Servers</v-btn>
        </v-list>
    </div>
</template>

<script>
    import { eventBus } from '../main';

    export default {
        data() {
            return {
                serverList: [
				{ Name: "Server #1", status: true },
				{ Name: "Server #2", status: false },
				{ Name: "Server #3", status: true },
				{ Name: "Server #4", status: false },
				{ Name: "Server #5", status: true }
                ]
            }
        },
        methods: {
            statusChange(i) {
                this.serverList[i].status = !this.serverList[i].status;
            },
            updateServers() {
                eventBus.$emit('updated', 'Server Details are currently updated.');
            }
        }
    }
</script>

<style>

</style>


<template>
    <div id="servers">
        <v-list class="pa-3">
            <v-list-tile
                v-for="(server, i) in serverList" :key="i">
                <v-icon color="amber accent-2" class="mr-2">computer</v-icon>
                {{ server.Name }} - Status: {{ server.status }}
                <v-btn @click="statusChange(i, server.status)" small>Change Status</v-btn>
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
				{ Name: "Server #1", status: "ACTIVE" },
				{ Name: "Server #2", status: "INACTIVE" },
				{ Name: "Server #3", status: "ACTIVE" },
				{ Name: "Server #4", status: "INACTIVE" },
				{ Name: "Server #5", status: "ACTIVE" }
                ]
            }
        },
        methods: {      
            statusChange(i, newStatus) {
                return (newStatus === "ACTIVE" ? this.serverList[i].status ="INACTIVE" : this.serverList[i].status ="ACTIVE");                
            },
            updateServers() {
                eventBus.$emit('updated', 'Server Details are currently updated.');
            }
        }
    }
</script>

<style>

</style>


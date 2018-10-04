<template>
    <div id="servers">
        <v-list class="pa-3">
            <v-list-tile
                @click="statusChange"
                v-for="(server, i) in serverList" :key="i">
                <v-icon color="amber accent-2" class="mr-1">computer</v-icon>
                {{ server }} - Status: {{ status }}
            </v-list-tile>
            <v-btn @click="updateServers" small>Update Servers</v-btn>
        </v-list>
        
    </div>
</template>

<script>
    import { eventBus } from '../main';

    export default {
        data() {
            return {
                serverList: ['Server #1', 'Server #2', 'Server #3','Server #4', 'Server #5'],
                status: 'active'
            }
        },
        methods: {
            statusChange() {
                if(this.status = 'active') {
                    this.status = 'inactive';
                } else {
                    this.status = 'active';
                }
            },
            updateServers() {
                eventBus.$emit('updated', 'Server Details are currently updated.');
            }
        }
    }
</script>

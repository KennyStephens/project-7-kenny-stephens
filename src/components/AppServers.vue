<template>
  <v-layout row>
    <v-flex>
      <v-card>
        <v-list three-line>
          <template v-for="(server, index) in servers">

            <v-divider
              v-if="server.divider"
              :inset="server.inset"
              :key="index"
            ></v-divider>

            <v-list-tile
              v-else
              :key="server.name"
              avatar
            >

              <v-list-tile-content>
                <v-list-tile-title v-html="server.name"></v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </template>
        </v-list>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
    data() {
        return {
            servers: [
                {name: 'Server 1'},
                { divider: true, inset: true },
                {name: 'Server 2'},
                { divider: true, inset: true },
                {name: 'Server 3'},
                { divider: true, inset: true },
                {name: 'Server 4'},
                { divider: true, inset: true },
                {name: 'Server 5'},
                { divider: true, inset: true },
            ]
        }
    }
}
</script>



<style scoped>

</style>

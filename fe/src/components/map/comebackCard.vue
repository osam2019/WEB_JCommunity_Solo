<template>
  <v-card dark class="elevation-0">
    <v-card-title>
      <span class="body-2 font-weight-bold">{{title}}</span>
      <v-spacer></v-spacer>
      <v-btn v-if="close" class="elevation-0" color="grey darken-3" @click="c">x</v-btn>
    </v-card-title>
    <v-card-text>
      <div class="mb-2">
        <v-chip label class="mr-4">지역(시/군/구)</v-chip>
        <v-chip class="ml-10" color="green darken-3" label dark>
          <v-icon left>where_to_vote</v-icon>
          {{loc.region}}
        </v-chip>
      </div>
      <div class="mb-2">
        <v-chip label class="mr-12">세부 주소</v-chip>
        <v-chip class="ml-10" color="lime darken-4" label dark>
          <v-icon left>map</v-icon>
          {{loc.address}}
        </v-chip>
      </div>
      <div>
        <v-chip label class="mr-12">보고 시각</v-chip>
        <v-chip class="ml-10" color="lime darken-3" label dark>
          <v-icon left>replay</v-icon>
          {{loc.time}}
        </v-chip>
      </div>
    </v-card-text>
  </v-card>
</template>
<script>
export default {
  props: [ 'title', 'loc', 'close' ],
  methods: {
    c () {
      this.$emit('close')
    }
  }
}
</script>

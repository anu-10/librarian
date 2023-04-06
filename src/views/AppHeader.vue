<template>
  <div class="app-header">
    <v-row dense>
      <v-col cols="18">
        <h3>{{ title }}</h3>
      </v-col>
      <v-col cols="2" class="text-right">
        <v-bin :title="tooltip" text @click="$emit('add')">
          <v-icon>mdi-plus</v-icon>
        </v-bin>
      </v-col>
    </v-row>
    <v-row>
      <v-text-field
        placeholder="Search"
        append-icon="mdi-magnify"
        @input="$emit('search', $event)"
      >
      </v-text-field>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.app-header {
  margin-left: 20px;
  margin-right: 20px;
  margin-top: 20px;
}
</style>

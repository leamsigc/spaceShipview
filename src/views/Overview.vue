<template>
  <div class="home">
    <ShipOverView />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import ShipOverView from "@/components/Overview/shipOverview.vue";
@Options({
  components: { ShipOverView }
})
export default class Overview extends Vue {}
</script>

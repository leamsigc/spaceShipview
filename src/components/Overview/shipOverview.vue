<template>
  <div class="hello">
    OverviewShip
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    msg: String
  }
})
export default class ShipOverView extends Vue {
  msg!: string;
}
</script>
<style scoped lang="scss"></style>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({})
export default class ShipOverView extends Vue {
  overviewLeft = [
    {
      status: "normal",
      info: "All Systems Check",
      desc: "Normal"
    },
    {
      status: "awaiting",
      info: "RENDEZVOUS BURN SLOW",
      desc: "Awaiting"
    },
    {
      status: "applied",
      info: "PREPARE RENDEZVOUS BURN",
      desc: "Applied"
    },
    {
      status: "normal",
      info: "THERMAL SHIELD",
      desc: "Normal"
    },
    {
      status: "normal",
      info: "BURN Go/No-GO",
      desc: "Normal"
    },
    {
      status: "applied",
      info: "POWER COMPLETION",
      desc: "Applied"
    },
    {
      status: "awaiting",
      info: "STATION DECK CHECK",
      desc: "Awaiting"
    }
  ];
}
</script>

<template>
  <div class="ship-overview">
    <div class="overview-left">
      <div
        class="status-container"
        v-for="item in overviewLeft"
        :key="item.info"
      >
        <div class="status-icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            class="svg"
            :class="{
              applied: item.status === 'applied',
              awaiting: item.status === 'awaiting'
            }"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
            />
          </svg>
        </div>
        <div class="status-info">{{ item.info }}</div>
        <div class="status-desc">{{ item.desc }}</div>
      </div>
    </div>
    <div class="overview-center"></div>
    <div class="overview-right">
      <div
        class="status-container"
        v-for="item in overviewLeft"
        :key="item.info"
      >
        <div class="status-icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            class="svg"
            :class="{
              applied: item.status === 'applied',
              awaiting: item.status === 'awaiting'
            }"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
            />
          </svg>
        </div>
        <div class="status-info">{{ item.info }}</div>
        <div class="status-desc">{{ item.desc }}</div>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.ship-overview {
  background: var(--main-bg);
  min-width: 100vw;
  min-height: 100vh;

  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-areas: "left center  center  right";
}
.overview {
  &-left {
    grid-area: left;
    padding-top: 4rem;
  }
  &-center {
    grid-area: center;
  }
  &-right {
    grid-area: right;
    padding-top: 4rem;
  }
}

.status-container {
  color: var(--white);
  padding: 0.5rem 0.2rem;
  text-align: left;
  font-size: 0.6rem;

  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 20px);
  grid-template-areas:
    "icon information information information"
    "icon desc desc desc";
}
.status {
  &-icon {
    grid-area: icon;
    display: flex;
    justify-content: center;
    align-items: center;
    .svg {
      &.applied {
        fill: var(--success);
      }
      &.awaiting {
        fill: var(--warning);
      }
      width: 30px;
      fill: var(--light-color);
    }
  }
  &-info {
    grid-area: information;
    text-transform: uppercase;
  }
  &-desc {
    color: var(--light-color);
    grid-area: desc;
  }
}
</style>

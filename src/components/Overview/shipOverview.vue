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
  overviewRight = [
    {
      label: "Inertial",
      value: 87,
      position: "7.68 km/s"
    },
    {
      label: "Altitude",
      value: 20,
      position: "390.0 km"
    },
    {
      label: "Apogee",
      value: 50,
      position: "404.4 km"
    },
    {
      label: "Perigee",
      value: 77,
      position: "304.4 km"
    },
    {
      label: "Inclination",
      value: 59,
      position: "51.67°"
    },
    {
      label: "Range to ISS",
      value: 100,
      position: "0.02 km"
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
    <div class="overview-center">
      <div class="title">VEHICLE OVERVIEW</div>
      <div class="card">
        <div class="svg">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 158 134"
          >
          <defs>
            <linearGradient id="grad" x1="0%" y1="50%" x2="75%" y2="75%" >
                        <stop offset="0%" stop-color="var(--warning)"/>
                        <stop offset="10%" stop-color="var(--warning)"/>
                        <stop offset="20%" stop-color="var(--warning)"/>
                        <stop offset="40%" stop-color="var(--success)"/>
                        <stop offset="50%" stop-color="var(--success)"/>
                        <stop offset="50%" stop-color="var(--white)"/>
                        <stop offset="100%" stop-color="var(--white)"/>
            </lineargradient>
            </defs> 
            <path
              fill="var(--white)"
              fill-rule="evenodd"
              d="M80.5 3h-.254l.003 1a84.354 84.354 0 01.503 0l.003-1H80.5zm3.798.084a84.934 84.934 0 00-.504-.02l-.038.999.497.02.045-.999zm-7.092-.02l-.504.02.045 1 .498-.021-.039-1zm10.63.252a84.687 84.687 0 00-.503-.042l-.08.997c.166.013.332.027.497.042l.087-.997zm-14.17-.042l-.502.042.086.997c.166-.015.331-.029.497-.042l-.08-.997zm17.696.423a84.306 84.306 0 00-.502-.063l-.122.992.495.063.129-.992zM70.14 3.634l-.501.063.128.992a82.9 82.9 0 01.495-.063l-.122-.992zm24.727.593a81.809 81.809 0 00-.499-.085l-.164.986.493.084.17-.985zm-28.235-.085l-.499.085.17.985.493-.084-.164-.986zm31.715.764a82.82 82.82 0 00-.495-.106l-.207.978.49.105.212-.977zM63.149 4.8c-.166.034-.33.07-.495.106l.212.977c.163-.036.326-.07.49-.105l-.207-.978zm38.645.934a91.019 91.019 0 00-.49-.128l-.249.969c.162.041.323.083.484.126l.255-.967zm-42.097-.128a82.33 82.33 0 00-.49.128l.254.967c.161-.043.323-.085.484-.126l-.248-.969zm45.505 1.104l-.485-.149-.29.957.479.147.296-.955zM56.283 6.56l-.485.149.297.955c.159-.05.319-.098.478-.147l-.29-.957zm52.281 1.273a69.735 69.735 0 00-.478-.17l-.331.943.472.168.337-.941zm-55.65-.17l-.478.17.338.94.472-.167-.332-.943zm58.96 1.44a69.279 69.279 0 00-.47-.191l-.373.928.465.188.378-.926zm-62.278-.191l-.47.19.379.926.464-.188-.373-.928zm-3.26 1.394l-.461.21.42.909c.15-.07.302-.14.455-.209l-.414-.91zm68.789.21l-.461-.21-.413.91.455.209.419-.908zm-71.984 1.327l-.451.231.459.889.446-.23-.454-.89zm75.17.231c-.151-.077-.301-.155-.452-.231l-.453.89.446.23.459-.889zm-78.293 1.447c-.148.083-.294.167-.441.251l.498.867.436-.248-.493-.87zm81.405.251a67.023 67.023 0 00-.44-.252l-.493.87.435.249.498-.867zm-84.45 1.565c-.144.09-.287.18-.43.272l.538.843c.14-.09.282-.179.423-.268l-.531-.847zm87.484.272l-.429-.272-.532.847.424.268.537-.843zM34.013 17.29c-.14.096-.278.193-.417.29l.575.819.411-.287-.57-.822zm93.391.29a74.853 74.853 0 00-.416-.29l-.57.822c.138.095.275.19.411.287l.575-.818zm-96.26 1.796l-.402.31.612.79.397-.305-.606-.795zm99.114.31l-.402-.31-.607.795.397.306.612-.791zM28.376 21.594c-.13.109-.26.218-.388.328l.648.761.383-.323-.643-.766zm104.636.328c-.129-.11-.258-.22-.387-.328l-.643.766.382.323.648-.761zM25.713 23.937l-.372.345.683.73.367-.34-.678-.735zm109.946.346c-.123-.116-.247-.231-.372-.346l-.678.735.367.34.683-.73zm-112.495 2.12l-.356.363.717.697.35-.358-.712-.701zm115.028.363a71.276 71.276 0 00-.355-.362l-.712.701.35.358.717-.697zM20.734 28.99c-.113.126-.225.252-.337.38l.75.66c.11-.124.22-.249.332-.373l-.745-.667zm119.869.38a42.336 42.336 0 00-.337-.38l-.745.667c.112.124.222.249.333.374l.749-.662zm-122.17 2.32l-.319.395.78.624.315-.39-.777-.63zm124.453.395a44.33 44.33 0 00-.318-.395l-.776.63.313.39.781-.625zM16.265 34.498c-.1.137-.2.273-.298.41l.81.586.295-.405-.807-.59zm128.769.41a73.967 73.967 0 00-.299-.41l-.806.591.294.405.811-.586zM14.239 37.412l-.277.424.839.544c.09-.14.182-.279.273-.418l-.835-.55zm132.8.424a73.654 73.654 0 00-.278-.424l-.835.55.274.418.839-.544zM12.362 40.424l-.255.438.865.5.252-.431-.862-.507zm136.532.438c-.085-.147-.17-.293-.256-.438l-.862.507c.085.144.169.287.252.432l.866-.501zm1.698 3.116l-.232-.45-.887.462.097.187c.045.086.089.171.132.257l.89-.456zm-139.951-.45c-.079.15-.156.3-.233.45l.89.456c.076-.149.152-.296.23-.444l-.887-.463zm141.488 3.65c-.07-.155-.139-.309-.21-.462l-.909.416.206.455.913-.41zM9.081 46.715l-.21.462.913.409.206-.455-.91-.416zm144.415 3.737a76.88 76.88 0 00-.185-.472l-.93.368c.062.155.122.31.182.465l.933-.36zM7.689 49.981c-.062.157-.124.315-.184.472l.932.361c.06-.155.12-.31.182-.465l-.93-.368zm147 3.815l-.159-.48-.948.318.097.292.06.181.95-.31zm-148.218-.48l-.16.48.95.312.158-.474-.948-.318zm149.232 3.882a77.88 77.88 0 00-.133-.488l-.964.267.132.481.965-.26zM5.431 56.71l-.134.488.966.26.131-.48-.963-.268zm151.103 3.94a41.41 41.41 0 00-.107-.495l-.976.216c.035.162.071.324.105.487l.978-.208zm-151.96-.495l-.108.495.978.208.106-.487-.977-.216zm152.606 3.986l-.081-.5-.986.163.037.23.042.262.988-.155zm-153.279-.5l-.08.5.988.155c.025-.164.052-.328.079-.491l-.987-.163zm153.736 4.02a82.986 82.986 0 00-.053-.502l-.994.11a25.137 25.137 0 01.052.495l.995-.102zM3.417 67.16c-.019.167-.037.335-.054.502l.995.103.053-.495-.994-.11zm154.489 4.043a42.398 42.398 0 00-.027-.506l-.998.057.026.498.999-.05zM3.121 70.697c-.01.168-.018.336-.027.505l1 .049c.007-.166.016-.332.026-.498l-.999-.056zm154.866 3.802l-.001-.255-1 .004.001.251-.001.251 1 .004.001-.105v-.15zM3.014 74.244a67.589 67.589 0 000 .51l1-.004a67.81 67.81 0 010-.502l-1-.004zm154.865 4.058l.017-.303.01-.203-.999-.049a82.05 82.05 0 01-.026.498l.998.057zM3.094 77.797l.027.505.999-.057-.027-.498-.999.05zm154.49 4.042l.053-.502-.995-.103-.052.496.994.11zm-154.22-.502c.016.167.034.335.053.502l.994-.11-.053-.495-.995.103zm153.756 3.89l.022-.131.038-.239-.988-.155-.045.278-.034.214.986.163.021-.13zm-153.3-.37l.081.5.987-.163a65.488 65.488 0 01-.08-.492l-.987.155zm152.607 3.986c.037-.165.072-.33.107-.495l-.978-.208c-.034.163-.07.325-.105.487l.976.216zM4.466 88.348c.035.165.07.33.107.495l.977-.216a65.847 65.847 0 01-.106-.487l-.978.209zm151.104 3.94l.133-.488-.965-.26-.132.48.964.268zM5.297 91.8l.134.488.963-.267-.131-.481-.966.26zm149.233 3.883l.159-.481-.95-.311-.157.473.948.319zM6.311 95.202l.16.48.948-.318a65.448 65.448 0 01-.157-.473l-.95.31zm147 3.815l.185-.472-.933-.36c-.06.154-.12.31-.182.464l.93.368zM7.505 98.545c.06.158.122.315.184.472l.93-.368-.182-.465-.932.361zm144.414 3.737c.071-.153.14-.307.21-.461l-.913-.409-.206.455.909.415zm-143.047-.461l.209.462.91-.416a81.51 81.51 0 01-.207-.455l-.912.409zm141.488 3.65l.09-.174.142-.276-.89-.456c-.075.148-.152.296-.229.443l.887.463zm-139.952-.45l.233.45.886-.463a57.745 57.745 0 01-.23-.443l-.89.456zm1.699 3.116l.255.438.862-.508a60.737 60.737 0 01-.252-.431l-.865.501zm136.531.438l.08-.137.176-.301-.866-.501c-.083.144-.167.288-.252.431l.862.508zm-134.676 2.587l.277.424.835-.55a60.096 60.096 0 01-.273-.418l-.84.544zm132.799.425l.278-.425-.839-.544-.274.418.835.551zM15.967 114.09c.098.137.198.274.298.41l.807-.591a42.096 42.096 0 01-.295-.405l-.81.586zm128.978.122l.089-.122-.811-.585-.294.404.806.591.21-.288zm-126.831 2.702l.318.396.777-.631-.314-.389-.781.624zm124.454.396l.156-.193.162-.203-.781-.624-.174.217-.139.172.776.631zm-122.171 2.32l.337.379.745-.667a62.45 62.45 0 01-.332-.374l-.75.662zm119.869.379l.337-.379-.749-.662c-.111.125-.221.25-.333.374l.745.667zm-117.458 2.223l.355.363.713-.702a62.283 62.283 0 01-.35-.358l-.718.697zm115.029.363l.355-.363-.717-.697-.227.233-.123.125.712.702zm-112.496 2.121l.372.345.678-.735a65.486 65.486 0 01-.367-.341l-.683.731zm109.946.345l.372-.345-.683-.731-.367.341.678.735zm-107.299 2.016c.129.109.258.219.388.327l.643-.766a65.28 65.28 0 01-.383-.323l-.648.762zm104.85.148l.174-.148-.648-.762-.1.085-.282.238.643.766.213-.179zm-102.096 2.087l.403.309.606-.795a65.292 65.292 0 01-.397-.305l-.612.791zm99.114.309l.402-.309-.612-.791a59.58 59.58 0 01-.397.305l.607.795z"
              clip-rule="evenodd"
            />
            <path
              fill="var(--white)"
              d="M3 74.058h5.132v.947H3zM152.868 74.058H158v.947h-5.132zM146.559 111.922l-4.205-2.715-.589.776 4.205 2.715z"
            />
            <path
              fill="url(#grad)"
              fill-opacity="1"
              fill-rule="evenodd"
               class="circle"
              d="M126.623 128.451C142.786 115.583 153 96.314 153 74.926 153 36.553 120.122 5 79 5S5 36.553 5 74.926c0 22.462 11.266 42.587 28.856 55.415l-3.493 3.632C11.88 120.259 0 98.908 0 74.926 0 33.546 35.37 0 79 0s79 33.545 79 74.926c0 22.944-10.874 43.479-28 57.223l-3.377-3.698z"
              clip-rule="evenodd"
            />
          </svg>
        </div>
        <div class="card-info">PPO2</div>
        <div class="card-value ">2.69</div>
        <div class="card-label">psia</div>
      </div>
      <div class="card"></div>
      <div class="card"></div>
      <div class="card"></div>
    </div>
    <div class="overview-right">
      <div
        class="status-container"
        v-for="item in overviewRight"
        :key="item.info"
      >
        <div class="status-icon fz-2x">{{ item.position }}</div>
        <div class="status-info">{{ item.label }}</div>
        <div class="status-desc">
          <div class="value-container">
            <div class="value" :style="{ width: item.value + 'px' }"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.fz-2x {
  font-size: 1rem;
  text-align: right;
}
.ship-overview {
  background: var(--main-bg);
  min-width: 100vw;
  min-height: 100vh;

  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-areas: "left center  center center  right";
  grid-gap: 5px;
}
.overview {
  &-left {
    grid-area: left;
    padding-top: 4rem;
  }
  &-center {
    grid-area: center;
    padding-top: 4rem;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
  }
  &-right {
    grid-area: right;
    padding-top: 4rem;
    .status-container {
      grid-template-areas:
        "information information icon"
        "desc desc icon";

      &:nth-of-type(5) {
        margin-top: 5rem;
      }
    }
    .status-icon {
      justify-content: flex-end;
    }
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
.value-container {
  width: 100%;
  height: 5px;
  background: var(--light-color);
  opacity: 0.8;
  border-radius: 5px;
  .value {
    background: var(--secondary-color);
    height: 5px;
    border-radius: 5px;
  }
}

.card {
  width: 100%;
  min-height: 150px;
  max-height: 151px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 5px;
  color: var(--white);
  display: grid;
  place-items: center;
  position: relative;
  &-info {
    font-size: 0.6rem;
    padding-top: 0.5rem;
  }
  &-value {
    font-size: 1.5rem;
  }
  &-label {
    font-size: 0.6rem;
    color: var(--light-color);
  }
  .svg {
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    padding: 0.3rem;
    svg {
      width: 100%;
      height: 100%;
    }
    .circle {
      stroke-width: 1;
      stroke: #fec558;
      stroke-dashoffset: 138.5;
      stroke-dasharray: 230;
      animation: circle_stroke 5s ease-in forwards;
    }

    @keyframes circle_stroke {
      0% {
        stroke-dashoffset: 138.5;
        fill-opacity: 0;
      }
      100% {
        stroke-dashoffset: 0;
        fill-opacity: 1;
        stroke-dasharray: 0;
      }
    }
  }
}
.title {
  font-size: 2rem;
  font-weight: 900;
  color: var(--white);
  grid-area: span 1 / span 4;
}
</style>

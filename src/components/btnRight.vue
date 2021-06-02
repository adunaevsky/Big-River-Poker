<template>
  <svg
    class="lblBase lblSizeSmall"
    :class="{
      rFillDeal: specs.clr === 'red',
      rFillEffect: specs.clr === 'green',
    }"
    xmlns="http://www.w3.org/2000/svg"
    viewBox="0 0 175.4 185"
  >
    <g v-if="specs.label === 'DEAL' || specs.label === 'FOLD'">
      <rect
        class="sideBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 1"
        x="10"
        y="10"
        width="800.4"
        height="170"
        rx="85"
        ry="85"
        @click="deal"
      />
      <text
        class="sideBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="40"
        x="90"
        y="105"
        fill="#fff"
        @click="deal"
      >
        {{ specs.label }}
      </text>

      <rect
        class="bottomBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 0.8"
        x="30"
        y="10"
        width="140"
        height="370"
        rx="70"
        ry="70"
        @click="deal"
      />
      <text
        class="bottomBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="30"
        x="100"
        y="75"
        fill="#fff"
        @click="deal"
      >
        {{ specs.label }}
      </text>
    </g>

    <g v-else>
      <g class="sideBtn">
        <!-- 1x 2x START -->
        <rect
          c
          style="stroke: #fff; stroke-width: 6; opacity: 1"
          x="5"
          y="5"
          width="800.4"
          height="65"
          rx="35"
          ry="35"
          @click="ride(1)"
        />
        <text
          class="sideBtn"
          style="opacity: 0.8"
          text-anchor="middle"
          font-weight="bold"
          font-size="40"
          x="50"
          y="50"
          fill="#fff"
          @click="ride(1)"
        >
          1x
        </text>
        <rect
          style="stroke: #fff; stroke-width: 6; opacity: 1"
          x="85"
          y="5"
          width="800.4"
          height="65"
          rx="35"
          ry="35"
          @click="ride(2)"
        />

        <text
          class="sideBtn"
          style="opacity: 0.8"
          text-anchor="middle"
          font-weight="bold"
          font-size="40"
          x="125"
          y="50"
          fill="#fff"
          @click="ride(2)"
        >
          2x
        </text>
        <!-- 1x 2x END -->

        <rect
          style="stroke: #fff; stroke-width: 6; opacity: 1"
          x="10"
          y="80"
          width="800.4"
          height="90"
          rx="55"
          ry="55"
          @click="ride(3)"
        />
        <text
          v-show="!specs.ride3"
          class="sideBtn"
          style="opacity: 0.8"
          text-anchor="middle"
          font-weight="bold"
          font-size="40"
          x="50"
          y="136"
          fill="#fff"
          @click="ride(3)"
        >
          3x
        </text>

        <text
          v-show="specs.ride3"
          class="sideBtn"
          style="opacity: 0.8"
          text-anchor="middle"
          font-weight="bold"
          font-size="80"
          x="95"
          y="150"
          fill="#fff"
          @click="ride(3)"
        >
          3x
        </text>

        <rect
          v-show="!specs.ride3"
          style="stroke: #fff; stroke-width: 6; opacity: 1"
          x="85"
          y="80"
          width="800.4"
          height="90"
          rx="55"
          ry="55"
          @click="ride('all')"
        />

        <text
          v-show="!specs.ride3"
          class="sideBtn"
          style="opacity: 0.8"
          text-anchor="middle"
          font-weight="bold"
          font-size="40"
          x="130"
          y="136"
          fill="#fff"
          @click="ride('all')"
        >
          3x{{specs.ride2 ? '2' : '3'}}
        </text>
      </g>

      <rect
        class="bottomBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 0.8"
        x="30"
        y="10"
        width="60"
        height="370"
        rx="30"
        ry="30"
        @click="ride(3)"
      />
      <text
        v-show="!specs.ride3"
        class="bottomBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="30"
        x="60"
        y="55"
        fill="#fff"
        @click="ride(3)"
      >
        3x
      </text>

      <text
        v-show="specs.ride3"
        class="bottomBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="30"
        x="60"
        y="75"
        fill="#fff"
        @click="ride(3)"
      >
        3x
      </text>

      <rect
        v-show="!specs.ride3"
        class="bottomBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 0.8"
        x="30"
        y="70"
        width="60"
        height="370"
        rx="30"
        ry="30"
        @click="ride('all')"
      />

      <text
        v-show="!specs.ride3"
        class="bottomBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="30"
        x="60"
        y="115"
        fill="#fff"
        @click="ride('all')"
      >
        3x{{specs.ride2 ? '2' : '3'}}
      </text>

      <rect
        class="bottomBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 0.8"
        x="100"
        y="10"
        width="60"
        height="370"
        rx="30"
        ry="30"
        @click="ride(1)"
      />
      <text
        class="bottomBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="30"
        x="130"
        y="55"
        fill="#fff"
        @click="ride(1)"
      >
        1x
      </text>

      <rect
        class="bottomBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 0.8"
        x="100"
        y="70"
        width="60"
        height="370"
        rx="30"
        ry="30"
        @click="ride(2)"
      />
      <text
        class="bottomBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="30"
        x="130"
        y="115"
        fill="#fff"
        @click="ride(2)"
      >
        2x
      </text>
    </g>
  </svg>
</template>

<script>
export default {
  name: "btn",
  props: ["specs"],
  methods: {
    deal() {
      this.$emit("play", 0);
    },
    ride(n) {
      if (n === "all") {
        this.$emit('autoPlay');
      } else {
        this.$emit("play", n);
      } //console.log("ride", n, "got me!!!");
    },
  },
};
</script>

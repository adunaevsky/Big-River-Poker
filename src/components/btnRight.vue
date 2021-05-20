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
    <g v-if="specs.label === 'DEAL' || specs.label === 'PULL'">
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

      <g   class="sideBtn">

  <rect
       c
        style="stroke: #fff; stroke-width: 6; opacity: 1"
        x="5"
        y="5"
        width="800.4"
        height="65"
        rx="35"
        ry="35"
      />


 <!--      <circle
      
        cx="40"
        cy="40"
        r="37"
        stroke="black"
        stroke-width="3"
        fill="red"
        
        @click="ride(1)"
        
        style="stroke: #fff; stroke-width: 6; opacity: 1"
      /> -->
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
 <!--      <circle
      
        cx="130"
        cy="40"
        r="37"
        stroke="black"
        stroke-width="3"
        class="sideBtn"
        
        style="stroke: #fff; stroke-width: 6; opacity: 1"
        @click="ride(2)"
      /> -->


        <rect
       c
        style="stroke: #fff; stroke-width: 6; opacity: 1"
        x="85"
        y="5"
        width="800.4"
        height="65"
        rx="35"
        ry="35"
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
<!-- 
      <circle
      
        cx="130"
        cy="40"
        r="40"
        stroke="black"
        stroke-width="3"
        fill="red"
        
        style="stroke: #fff; stroke-width: 6; opacity: 1"
        @click="ride(2)"
      /> -->
         <rect
       c
        style="stroke: #fff; stroke-width: 6; opacity: 1"
        x="10"
        y="80"
        width="800.4"
        height="90"
        rx="55"
        ry="55"
      />
      <text
        class="sideBtn"
        style="opacity: 0.8"
        text-anchor="middle"
        font-weight="bold"
        font-size="80"
        x="95"
        y="150"
        fill="#fff"
        @click="ride(2)"
      >
        3x
      </text>

   






</g>
      <rect
        class="bottomBtn"
        style="stroke: #fff; stroke-width: 6; opacity: 0.8"
        x="30"
        y="10"
        width="140"
        height="370"
        rx="70"
        ry="70"
        @click="ride(1)"
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
        @click="ride(1)"
      >
        {{ specs.label }} B
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
      this.$emit("deal", 0);
    },
    ride(n) {
      console.log("ride", n, "got me!!!");
    },
  },
};
</script>

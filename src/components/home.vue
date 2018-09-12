<template>
  <v-container fluid>
    <br><br>
    <div style="position: relative; left: 50%; transform: translateX(-50%); display: inline-block;">
      <div style="display: flex;">
        <div class="fas fa-cloud fa-8x white--text" style="margin-top: 30px; margin-right: 30px;"></div>
        <div>
          <div class="white--text weather-desc">Cloudy</div>
          <div style="display: inline-block;" class="white--text readings">
            <div class="fas fa-thermometer-three-quarters fa-lg reading-icon"></div>
            <div style="margin: 0 20px; display: inline-block;">29.2</div>
            <div class="fas fa-tint fa-lg reading-icon"></div>
            <div style="margin: 0 20px; display: inline-block;">73%</div>
          </div>
        </div>
      </div>
    </div>

    <div style="margin-top: 80px; font-size: 30px; text-align: center; margin-bottom: -20px;" class="white--text">
      <v-layout row>
        <v-flex xs3 style="border-right: 1px solid white;">
          <div class="indicator">PSI</div>
          <div class="green darken-1 psi-block">
            23
          </div><br>
          <div style="margin-bottom: 20px;" class="indicator">Good</div>
        </v-flex>
        <v-flex xs3 style="border-right: 1px solid white;">
          <div class="indicator">RAIN</div>
          <div class="transparent psi-block">
          0
          </div>
          <div class="indicator">mm</div>
        </v-flex>
        <v-flex xs3 style="border-right: 1px solid white;">
          <div class="indicator">DENGUE</div>
          <div style="position: relative; display: inline-block; margin: 14px 0;">
          <div class="blue lighten-2 indicator-circle"></div>
          </div>
        </v-flex>
        <v-flex xs3>
          <div class="add-icon-container">
            <div class="fas fa-plus fa-2x black--text add-icon"></div>
          </div>
          <div class="black--text indicator">ADD</div>
        </v-flex>
      </v-layout>

      <div class="white black--text" style="margin: 0 -30px; height: 600px; font-weight: 700;">
        <div style="padding: 20px 30px; text-align: left;">
          <span class="blue--text text--lighten-3">Tide</span><span class="grey--text text--lighten-1"> · </span> <span class="orange--text text--lighten-3">Sunrise & Sunset</span>
        </div>
        <div>
          <div class="grey--text" style="font-weight: 400; font-size: 48px;">
            {{ new Date().getDay() }} {{ new Date().toLocaleString('en-us', { month: "long" }) }}
          </div>
          <div style="left: 50%; display: inline-block;">
          <div class="orange" style="position: absolute; transform: translateX(-50%); height: 60px; width: 60px; border-radius: 30px; z-index: 2;"></div>
          </div>
          <div style="position: absolute; height: 400px; width: 1px; left: 50%; z-index: 1; transform: translateY(-100px);" class="grey lighten-2"></div>
          <div style="height: 300px;"></div>
          <div style="position: absolute; height: 30px; width: 30px; display: inline-block; transform: rotate(45deg) translateX(-50%)" class="grey lighten-3"></div>
          <div class="grey--text grey lighten-3" style="padding: 20px 0px;">
            {{ new Date().toLocaleString('en-US', { hour: 'numeric', minute: 'numeric', hour12: true }).toLowerCase() }}
          </div>
        </div>
      </div>

    </div>

  </v-container>

</template>

<script>
export default {
  props: {

  },
  data() {
      return {
        Date,
      }
  }
}
</script>

<style>
  .weather-desc {
    font-size: 72px;
  }
  .readings {
    font-size: 30px;
  }
  .psi-block {
    display: inline-block;
    border-radius: 10px;
    font-size: 72px;
    padding: 0px 20px;
    font-weight: 300;
    margin: 10px 0;
  }
  .indicator-circle {
    height: 100px;
    width: 100px;
    border-radius: 50px;
    border: 6px solid white !important;
  }
  .add-icon-container {
    border: 3px solid black;
    display: inline-block;
    padding: 16px;
    border-radius: 50px;
    margin: 20px 0;
  }
  .add-icon {
    height: 62px;
    width: 62px;
  }

  @media only screen
  and (max-device-width : 812px) {
    .weather-desc {
      font-size: 60px;
    }
    .readings {
      font-size: 24px;
    }
    .reading-icon {
      font-size: 22px;
    }
    .indicator {
      font-size: 16px;
    }
    .psi-block {
      font-size: 30px;
      padding: 0 10px;
    }
    .indicator-circle {
      height: 60px;
      width: 60px;
      border: 4px solid white !important;
    }
    .add-icon-container {
      border: 1px solid black;
      display: inline-block;
      padding: 4px;
      border-radius: 50px;
      margin: 30px 0 10px 0;
      height: 40px;
      width: 40px;
    }
    .add-icon {
      height: 30px;
      width: 30px;
      font-size: 16px;
      transform: translateY(-12px);
    }
  }
</style>

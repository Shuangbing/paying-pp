<template>
  <div class="main">
    <div v-show="settingShow" id="paying-setting">
      <span>時給</span>
      <input type="number" v-model="perhour" />
      <button @click="setupPerhour">設定</button>
    </div>
    <div v-show="!settingShow" id="paying-count">
      <h1>¥{{paying}}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "main",
  props: {},
  data: () => {
    return {
      settingShow: true,
      perhour: 1500,
      paying: 0,
      timeCount: 0
    };
  },
  methods: {
    setupPerhour() {
      this.settingShow = false;
      setInterval(
        function() {
          this.timeCount = this.timeCount + 1;
          this.paying = ((this.perhour / 3600) * this.timeCount).toFixed(2);
        }.bind(this),
        1000
      );
    }
  }
};
</script>

<style>
.main {
  position: absolute;
  width: 100px;
  height: 50px;
  top: 50%;
  left: 50%;
  margin-left: -50px; /* margin is -0.5 * dimension */
  margin-top: -50px;
}
</style>
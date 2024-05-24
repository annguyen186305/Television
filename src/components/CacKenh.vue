<template>
<div class="kenh">
    <button @click="kenhDuocChon" v-if="hidDen === false" class="kenhButton">
      <img :src="hinhAnh"  alt=""  class="kenhImage">
      <p v-if="hienThiTieuDe === true" class="kenhTitle">
        {{ tenKenh }}
      </p>
    </button>
</div>
</template>

<script>
export default {
  name: "CacKenh",
  props:{
    tenKenh: String,
    videoURL:String,
    hinhAnh: String,
    hidDen: Boolean,
    hienThiTieuDe:Boolean,
  },
  methods: {
    kenhDuocChon(){
      console.log(this.videoURL)
    this.$emit('kenhDuocChon', this.videoURL)
    }
  }
}
</script>

<style scoped>
.kenh{
  width: 250px;
  height: 150px;
  font-size: 50px
}
.kenhButton{
  display: flex;
  align-items: center;
  margin-left: 50px;
  margin-top: 30px;
  width: 200px;
  height: 100px;
}
.kenhImage{
  margin-right: 20px;
  width: 120px;
  height : 90px;
}
.kenhTitle{
  margin: 0;
  font-size: inherit;
}
</style>
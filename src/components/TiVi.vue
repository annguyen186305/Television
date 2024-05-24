<template>
<div class="TiVi">
  <h1>TiVi Của An Nguyễn</h1>
  <div class="videoAndListVideo">
  <iframe  :src="onVideoURL"
          frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin" allowfullscreen
           class="iframe">
  </iframe>

    <div class="CacKenh">
      <CacKenh v-for="(video, index) in danhSachVideo"
               :key="index"
               :tenKenh="video.tenKenh"
               :videoURL="video.url"
               :hinhAnh="video.anh"
               :hidDen="video.hidDen"
               :hienThiTieuDe="video.hienThiTieuDe"
               @kenhDuocChon="kenhDuocBat">
      </CacKenh>
    </div>
  </div>
</div>
</template>

<script>
import CacKenh from "@/components/CacKenh.vue";

export default {
  name: "TiVi",
  props:{
    tenTivi:String
  },
  components: {
    CacKenh
  },
  data () {
    return {
      onVideoURL:'',
      danhSachVideo: [
        {
          hidDen:false,
          hienThiTieuDe:true,
          url: 'https://www.youtube.com/embed/FMFMTC4k62c',
          tenKenh: 'VTV1',
          anh:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfyVpo8edGOo-0Accvg26mfeP1pvdesbKR6A&s'
        },
        {
          hidDen: false,
          hienThiTieuDe:true,
          url: 'https://www.youtube.com/embed/Z6znRApNeYY?si=RZCli4Zh6DrOj61n',
          tenKenh: 'VTV2',
          anh:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRr5QdkhXfT8lwg3H7xXWbZrwHPP6jwVA2xGg&s'
        },
        {
          hidDen: false,
          hienThiTieuDe:true,
          url: 'https://www.youtube.com/embed/okoEFoqtfjc',
          tenKenh: 'VTV3',
          anh:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQptC0HpO4l0HePe-BGrHHSVFfcn8EERtmu-A&s'
        }
      ]
    }
  },
  methods: {
    kenhDuocBat(VideoURL) {
      console.log(VideoURL)
      this.onVideoURL = VideoURL;
    }
  }
}
</script>

<style scoped>
.TiVi{
  padding: 10px;
  margin: 100px;
  width: 1200px;
  height: 650px;
  border: 5px solid cadetblue;
  background-color: wheat
}
.videoAndListVideo{
  display: flex;
  align-items: flex-start;
  margin: 30px;

}
.iframe{
  flex-grow: 1;
  max-width: calc(100% - 300px);
  height:500px;
  border: 3px solid black;
}
.CacKenh {
  margin-left: 20px;
}
</style>
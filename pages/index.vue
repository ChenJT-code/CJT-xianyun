<template>
  <div class="container">
    <!-- 幻灯片 -->
    <!-- el-carousel-item 对应每一张图片 -->
    <el-carousel :interval="5000" arrow="always">
         <!-- interval 间隔 -->
      <!-- 获取的来的都是相对路径,需要拼接数据库的路径才行, $axios.default.baseURL -->
      <el-carousel-item v-for="(item, index) in banners" :key="index">
        <div
          class="banner-image"
          :style="`
                background:url(${item.url}) center center no-repeat;
                background-size:contain contain;
                `"
        ></div>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
    data(){
        return{
            banners:[
                {
                    url:"http://pic.rmb.bdstatic.com/261eff52c418c89a79d0b5a59ec143de.jpeg"
                },
                 {
                    url:"http://img0.imgtn.bdimg.com/it/u=1722683143,3909236625&fm=26&gp=0.jpg"
                },
                 {
                    url:"http://05.imgmini.eastday.com/mobile/20180517/c0f4b98ce9bf70ea03497870fca1e0f4_wmk.jpeg"
                }
            ]
        }
    }
};
</script>

<style scoped lang="less">
.container{
    min-width:1000px;
    margin:0 auto;
    position:relative;

    /deep/ .el-carousel__container{
        height:700px;
    }

    .banner-image{
        width:100%;
        height:100%;
    }
}
</style>
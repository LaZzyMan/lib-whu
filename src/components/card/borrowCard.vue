<template>
  <div class='borrow-card' :class="{ 'selected': isSelected }" @click=onClick>
    <div class='circle'/>
    <div class='line'/>
    <div class='title'>
      <span class='name'>{{name}}</span>
    </div>
    <div class='info'>
      <span class='author'>{{author}}&nbsp;著</span>
    </div>
    <div class='info'>
      <span class='position'>{{position}}</span>
      <span class='time'>{{fromTime}}至{{toTime}}</span>
    </div>
    <button class='ratio'>
      <image :class="{ 'ratio-selected': isSelected }" src='https://system.lib.whu.edu.cn/mp-static/131/椭圆 11@3x.png'/>
    </button>
  </div>
</template>

<script>
export default {
  name: 'BorrowCard',
  props: {
    key: {
      type: Number,
      required: true,
      default: 0,
    },
    name: {
      type: String,
      required: true,
      default: '',
    },
    author: {
      type: String,
      required: true,
      default: '',
    },
    position: {
      type: String,
      required: true,
      default: '',
    },
    fromTime: {
      type: String,
      required: true,
      default: '',
    },
    toTime: {
      type: String,
      required: true,
      default: '',
    },
    isSelected: {
      type: Boolean,
      required: true,
      default: false,
    },
  },
  data: {
  },
  computed: {
    index() {
      return (this.key + 1).toString();
    },
  },
  methods: {
    onClick() {
      this.$emit('click');
    },
  },
};
</script>

<style lang="scss" scoped>
.borrow-card{
  margin-top: 2%;
  margin-bottom: 2%;
  border-style: solid;
  border-radius: 5px;
  border-width: 1px;
  border-color: grey;
  padding-left: 5%;
  padding-bottom: 3%;
  padding-top: 3%;
  padding-right: 3%;
  background-color: white;
  position: relative;
  .line{
    width: 1px;
    height: 85%;
    border-right-style: solid;
    border-color: #7aa6e2;
    border-width: 5rpx;
    left: -4.3vw;
    top: 2vh;
    opacity: 0.7;
    position: absolute;
  }
  .circle{
    position: absolute;
    width: 28rpx;
    height: 28rpx;
    background-color: #7aa6e2;
    left: -5.5vw;
    top: -0.2vh;
    border-radius: 14rpx;
  }
  .title{
    display: flex;
    font-size: 30rpx;
    align-items: center;
    font-weight: bold;
    color: #525252;
    margin-top: 1.5vh;
    margin-bottom: 1.5vh;
    .name{
      margin-right: 4vw;
    }
    .author{
      font-size: 24rpx;
      font-weight: normal;
      color: #777777;
    }
  }
  .info{
    display: flex;
    font-size: 25rpx;
    color: #777777;
    justify-content: space-between;
  }
  .ratio{
    width: 5vw;
    height: 5vw;
    position: absolute;
    padding: 0px;
    background: none;
    border-width: 5rpx;
    border-style: solid;
    border-color: #7aa6e2;
    border-radius: 2.5vw;
    top: 3vh;
    right: 2vw;
    image{
      display: none;
      width: 100%;
      height: 100%;
      position: absolute;
      left: 0;
    }
    .ratio-selected{
      display: block;
    }
  }
}
.selected{
  background-color: #E3EFFF;
}
</style>

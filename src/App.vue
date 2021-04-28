<template>
  <div class="order">
    <!-- header start -->
    <div class="header">
      <div class="left">
        <img src="@/assets/order/back.png" alt />
        <img src="@/assets/order/out.png" alt />
      </div>

      <div>
        <span>淘宝天猫</span>
        <img src="@/assets/order/down.png" alt />
      </div>

      <div class="right">
        <img src="@/assets/order/search.png" alt />
        <img src="@/assets/order/reload.png" alt />
      </div>
    </div>
    <!-- header end -->

    <!-- title start -->
    <div class="title">
      <span>我的订单</span>
      <img src="@/assets/order/down.png" alt />
    </div>
    <!-- title end -->

    <div class="main">
      <!-- tab start -->
      <div class="tab">
        <a class="active" href="javascript:void(0)">全部</a>
        <a href="javascript:void(0)">已付款</a>
        <a href="javascript:void(0)">订单取消</a>
        <a href="javascript:void(0)">订单收获</a>
        <a href="javascript:void(0)">收获</a>
      </div>

      <!-- order list start -->
      <div class="tab-content">
        <div class="order-info order-info-complete">
          <p>父订单号: 4141522222</p>
          <p class="order-number">
            <span>订单号: 5241144111</span>
            <span class="label">PLUS会员</span>
          </p>
          <p>
            <span>下单: 2021-04-28 22:36:42</span>
            <span>完成: 2021-04-28 22:36:42</span>
          </p>
          <p>预估结算时间: 2020-07-20</p>

          <div class="order-goods">
            <img src="@/assets/order/goods.png" alt />
            <div>
              <p class="goods-name">
                <span class="label">跨店</span>
                <span>
                  HUAWEI Mate X2 5G 全网通 256GB（冰晶
                  蓝）
                </span>
              </p>

              <div class="proportion">
                <span>佣金比例: 1.00%</span>
                <span>分成比例: 100.00%</span>
              </div>
            </div>
          </div>

          <div class="price-info">
            <div>
              <p>购买数量</p>
              <p>1</p>
            </div>
            <div>
              <p>计佣金额</p>
              <p>￥12.80</p>
            </div>
            <div>
              <p>计佣佣金</p>
              <p>￥12.80</p>
            </div>
          </div>
        </div>

        <div class="order-info order-info-paid">
          <p>父订单号: 4141522222</p>
          <p class="order-number">订单号: 5241144111</p>
          <p>
            <span>下单: 2021-04-28 22:36:42</span>
            <span>完成: 2021-04-28 22:36:42</span>
          </p>
          <p>预估结算时间: 2020-07-20</p>

          <div class="order-goods">
            <img src="@/assets/order/goods.png" alt />
            <div>
              <p class="goods-name">
                <span class="label">跨店</span>
                <span>
                  HUAWEI Mate X2 5G 全网通 256GB（冰晶
                  蓝）
                </span>
              </p>

              <div class="proportion">
                <span>佣金比例: 1.00%</span>
                <span>分成比例: 100.00%</span>
              </div>
            </div>
          </div>

          <div class="price-info">
            <div>
              <p>购买数量</p>
              <p>1</p>
            </div>
            <div>
              <p>计佣金额</p>
              <p>￥12.80</p>
            </div>
            <div>
              <p>计佣佣金</p>
              <p>￥12.80</p>
            </div>
          </div>
        </div>

        <div class="order-info order-info-invalid">
          <p>父订单号: 4141522222</p>
          <p class="order-number">
            <span>订单号: 5241144111</span>
            <span class="label">PLUS会员</span>
          </p>

          <div class="tips">
            <img src="@/assets/order/tips.png" alt />
            <span>订单无效,无效原因: 取消</span>
          </div>

          <div class="order-goods">
            <img src="@/assets/order/goods.png" alt />
            <div>
              <p class="goods-name">
                <span class="label">跨店</span>
                <span>
                  HUAWEI Mate X2 5G 全网通 256GB（冰晶
                  蓝）
                </span>
              </p>

              <div class="proportion">
                <span>佣金比例: 1.00%</span>
                <span>分成比例: 100.00%</span>
              </div>
            </div>
          </div>

          <div class="price-info">
            <div>
              <p>购买数量</p>
              <p>1</p>
            </div>
            <div>
              <p>计佣金额</p>
              <p>￥12.80</p>
            </div>
            <div>
              <p>计佣佣金</p>
              <p>￥12.80</p>
            </div>
          </div>
        </div>
      </div>

      <!-- tab end -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'order',
  data() {
    return {}
  },
  mounted() {},
  methods: {},
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
img,
a,
span {
  display: inline-block;
  vertical-align: middle;
}
a {
  text-decoration: none;
}
.label {
  height: 13px;
  width: 30px;
  background: #ff2e6b;
  border-radius: 13px;
  font-size: 8px;
  font-weight: bold;
  color: #ffffff;
  text-align: center;
  line-height: 15px;
  font-family: -apple-system-font, sans-serif;
}
</style>

<style scoped lang="scss">
// header
.header {
  height: 40px;
  display: flex;
  justify-content: space-between;
  align-content: center;
  height: 40px;
  line-height: 40px;
  background: #ff2e6b;

  padding: 0 10px;
  span {
    font-size: 15px;
    font-weight: 500;
    color: #fefefe;
    margin-right: 5px;
  }
  .left img,
  .right img {
    width: 18px;
    height: 18px;
  }
  .left img {
    margin-right: 10px;
  }
  .right img {
    margin-left: 10px;
  }
}
// title
.title {
  height: 50px;
  line-height: 35px;
  background: #ff2e6b;
  text-align: center;
  position: relative;
  span {
    font-size: 15px;
    font-weight: 500;
    color: #fefefe;
  }
  img {
    transform: rotate(180deg);
    -ms-transform: rotate(180deg); /* IE 9 */
    -moz-transform: rotate(180deg); /* Firefox */
    -webkit-transform: rotate(180deg); /* Safari 和 Chrome */
    -o-transform: rotate(180deg); /* Opera */
    position: absolute;
    left: 50%;
    margin-left: 3px;
    bottom: 8px;
    height: 9px;
  }
}
// mian
.main {
  margin-top: -10px;
  position: relative;
  z-index: 9;
  background: #fff;
  border-radius: 10px 10px 0 0;
}
// tab
.tab {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 50px;
  line-height: 50px;
  a {
    height: 26px;
    padding: 0 7px;
    line-height: 26px;
    color: #fff;
    font-size: 14px;
    font-weight: 500;
    color: #333333;
    border-radius: 13px;
    outline: none;
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  }
  a.active {
    background: #ff2e6b;
    color: #fff;
  }
}
// order list
.tab-content {
  margin: 0 10px;
  background: #ffffff;
  box-shadow: 0px -1px 4px 0px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  padding: 14px;

  .order-info {
    font-size: 11px;
    font-weight: bold;
    color: #333333;
    margin-bottom: 14px;
    border-bottom: 1px solid #f4f4f4;
    position: relative;
    padding-bottom: 20px;
    &:last-child {
      border-bottom: none;
    }
    &::before {
      position: absolute;
      right: -14px;
      top: -14px;
      width: 48px;
      height: 48px;
    }
    &-complete::before {
      content: url('./assets/order/complete.png');
    }
    &-paid::before {
      content: url('./assets/order/paid.png');
    }
    &-invalid::before {
      content: url('./assets/order/invalid.png');
    }

    & > p {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    & > .order-number {
      display: block;
      margin-bottom: 10px;
      span {
        vertical-align: middle;
        &:nth-child(1) {
          margin-right: 10px;
        }
      }
      .label {
        width: 50px;
      }
    }

    .order-goods {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      & > img {
        width: 59px;
        height: 59px;
        margin-right: 8.5px;
      }
      .goods-name {
        display: flex;
        justify-content: flex-start;
        align-items: flex-start;
        margin-bottom: 10px;
        margin: 3px 0 10px 0;

        span:nth-child(2) {
          width: calc(100% - 33px);
          margin-left: 3px;
          margin-top: -2px;
          display: -webkit-box;
          -webkit-box-orient: vertical;
          -webkit-line-clamp: 2;
          overflow: hidden;
        }
      }
      .proportion {
        font-size: 11px;
        font-family: PingFang SC;
        font-weight: bold;
        color: #333333;
        span {
          margin-right: 30px;
        }
        span:nth-child(2) {
          margin-right: 0;
        }
      }
    }
    .price-info {
      padding: 0 35px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 11px;
      font-weight: bold;

      p:nth-child(1) {
        color: #a2a2a2;
        margin: 16px 0 3px;
      }

      p:nth-child(2) {
        color: #333;
      }
    }
    .tips {
      display: none;
    }

    &-invalid {
      & > .order-number {
        color: #fea22a;
        .label {
          background: #b9bbc2;
        }
      }

      .price-info {
        p:nth-child(1) {
          color: #a2a2a2;
        }

        p:nth-child(2) {
          color: #a2a2a2;
        }
      }
      .tips {
        display: block;
        width: 328px;
        height: 25px;
        background: #fea22a;
        font-size: 9px;
        font-weight: bold;
        color: #ffffff;
        margin-bottom: 10px;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        img {
          width: 10px;
          margin: 0 5px;
        }
      }
    }
  }
}
</style>


<template>
    <div class="header">
      <div class="fixbox">
      <div class="h_top">
        <a @click="goback" class="iconfont icon-jiantou-copy"></a>
        <h1>{{title}}</h1>
        <div>
          <router-link to="/CinemaMap" class="iconfont icon-location"></router-link>
          <a class="iconfont icon-sousuo"></a>
        </div>
      </div>
      <div class="h_cen">
        <tab bar-active-color="#ff495f" active-color="#ff495f" default-color="#5f615f" custom-bar-width="217px">
          <tab-item @on-item-click="goto(index)" v-for="(a,index) in nav1" :key="index">{{a.day}}<span>{{a.date}}</span></tab-item>
        </tab>
      </div>
      <div class="h_bot">
        <ul class="navbox2">
          <li @click="show(index)" v-for="(n,index) in nav" :key="index" :class="{chose:active==index}">
            <span>{{n}}<i class="iconfont icon-arrLeft-fill" ></i></span>
          </li>
        </ul>
      </div>
      </div>
      <div class="selections" ref="selections" v-if="isshow">
        <div v-show="active==0" class="secbox area">
          <ul class="list">
          <li><div class="active_div">不限区域</div></li>
          <li><div>灞桥区</div></li>
          <li><div>碑林区</div></li>
          <li><div>高陵县</div></li>
          <li><div>高新区</div></li>
          <li><div>户县</div></li>
          <li><div>经开区</div></li>
          <li><div>蓝田县</div></li>
          <li><div>莲湖区</div></li>
          <li><div>临潼区</div></li>
          <li><div>曲江新区</div></li>
          <li><div>市区</div></li>
          <li><div>未央区</div></li>
          <li><div>新城区</div></li>
          <li><div>西咸新区</div></li>
          <li><div>阎良区</div></li>
          <li><div>雁塔区</div></li>
          <li><div>长安区</div></li>
        </ul>
        </div>
        <div v-show="active==1" class="secbox area rank">
          <ol>
            <li class="active_one">
              <div>
              <i class="iconfont icon-duigou"></i>
              <span>全部</span>
              </div>
              <div class="tiaonum">
                101
              </div>
            </li>
            <li>
              <div>
              <i class="iconfont icon-duigou"></i>
              <span>万达影城</span>
              </div>
              <div class="tiaonum">
                10
              </div>
            </li>
            <li>
              <div>
                <i class="iconfont icon-duigou"></i>
                <span>CGV影城</span>
              </div>
              <div class="tiaonum">
                4
              </div>
            </li>
            <li>
              <div>
                <i class="iconfont icon-duigou"></i>
                <span>大地影院</span>
              </div>
              <div class="tiaonum">
                4
              </div>
            </li>
            <li>
              <div>
                <i class="iconfont icon-duigou"></i>
                <span>横店电影城</span>
              </div>
              <div class="tiaonum">
                3
              </div>
            </li>
            <li>
              <div>
                <i class="iconfont icon-duigou"></i>
                <span>太平洋电影城</span>
              </div>
              <div class="tiaonum">
                3
              </div>
            </li>
            <li>
              <div>
                <i class="iconfont icon-duigou"></i>
                <span>耀莱成龙国际影城</span>
              </div>
              <div class="tiaonum">
                3
              </div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>奥斯卡国际影城</span>
              </div>
              <div class="tiaonum">2</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>博纳国际影城</span>
              </div>
              <div class="tiaonum">2</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>橙天嘉禾影城</span>
              </div>
              <div class="tiaonum">2</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>恒大影城</span>
              </div>
              <div class="tiaonum">2</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>曲江国际影城</span>
              </div>
              <div class="tiaonum">2</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>欢乐小马电影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>卢米埃影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>SFC上影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>UMK国际影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>文投国际影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>沃美影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>幸福蓝海国际影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>中影国际影城</span>
              </div>
              <div class="tiaonum">1</div>
            </li>
            <li>
              <div><i class="iconfont icon-duigou"></i>
                <span>其他</span>
              </div>
              <div class="tiaonum">56</div>
            </li>
          </ol>
        </div>
        <div v-show="active==2" class="secbox area myrecent">
          <ol>
            <li class="active_one">
              <i class="iconfont icon-duigou"></i>
              <span>离我最近<b>(已定位)</b></span>
            </li>
            <li>
              <i class="iconfont icon-duigou"></i>
              <span>价格最低</span>
            </li>
          </ol>
        </div>
        <div v-show="active==3" class="secbox area timesec">
          <ul class="list">
            <li><div class="active_div">不限时段</div></li>
            <li><div>9-11点</div></li>
            <li><div>11-13点</div></li>
            <li><div>13-15点</div></li>
            <li><div>15-17点</div></li>
            <li><div>17-19点</div></li>
            <li><div>19-21点</div></li>
            <li><div>21-23点</div></li>
            <li><div>23点以后</div></li>
          </ul>
        </div>
        <div v-show="active==4" class="secbox area special">
          <ul class="list">
            <li><div class="active_div">不限</div></li>
          </ul>
          <h3 class="TStit">影院特色</h3>
          <ul class="list">
            <li><div>退票</div></li>
            <li><div>改签</div></li>
            <li><div>影城卡</div></li>
            <li><div>观影小食 </div></li>
            <li><div>IMAX厅</div></li>
            <li><div>巨幕厅</div></li>
            <li><div>中国巨幕</div></li>
            <li><div>realD厅</div></li>
            <li><div>4K厅</div></li>
            <li><div>4DX厅</div></li>
            <li><div>4D厅</div></li>
            <li><div>杜比厅</div></li>
            <li><div>可停车</div></li>
            <li><div>艺术影厅</div></li>
            <li><div>激光厅</div></li>
            <li><div>MX4D厅</div></li>
            <li><div>DTS临时展厅</div></li>
          </ul>
          <h3 class="TStit">会员专享</h3>
          <ul class="list vip">
            <li>
              <div>
                <p>定制票纸纪念语</p>
                <span>黑钻、黄金会员专享</span>
              </div>
            </li>
            <li>
              <div>
                <p>定制专属取票语</p>
                <span>黑钻会员专享</span>
              </div>
            </li>
          </ul>
        </div>
        <div class="bg" @click="hide"></div>
      </div>
    </div>
</template>

<script>
    import TabItem from "vux/src/components/tab/tab-item";
    import Tab from "vux/src/components/tab/tab";
    export default {
        name: "CinemaHeader",
      components: {Tab, TabItem},
      props:["title"],
      data(){
            return {
              flag:0,
              active:6,
              nav1:[
                {"day":"今天",
                  "date":"09-18"

                },{"day":"明天",
                  "date":"09-19"

                },{"day":"后天",
                  "date":"09-20"

                },{"day":"周五",
                  "date":"09-21"

                },{"day":"周六",
                  "date":"09-22"

                },{"day":"周日",
                  "date":"09-23"

                },{"day":"周一",
                  "date":"09-24"
                }
              ],
              nav:["区域","品牌","离我最近","时段","特色"],
              isshow:true,
            }
        },
        methods:{
          show(n){
            if(this.active==n){
              this.active=6
              this.$refs.selections.style.display = "none";
              $(".navbox2 li").css({"color":"#323332"});
            }else{
              this.$refs.selections.style.display = "block";
              // $(".selections").toggleClass("show")
              this.active = n;
              $(".navbox2 li").css({"color":"#323332"});
              $(".navbox2 li").eq(n).css({"color":"#ff495f"})
              $(".navbox2 li").eq(n).find(".iconfont").addClass("animated rotateIn")
            }
          },
          hide(){
            this.$refs.selections.style.display = "none";
            $(".navbox2 li").css({"color":"#323332"});
          },
          chose(m){
            this.flag = m
          },
          goto(n){
            this.$emit("child-say",n)
          },
          goback(){
            this.$router.go(-1)
          }
        }
    }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
c(k){
  (k/75)rem
}
a:link{text-decoration: none!important;  }
a:visited{text-decoration: none!important;  }
a:hover{text-decoration: none!important;  }
a:active{text-decoration: none!important;  }
a:focus{text-decoration: none!important;  }
.header{
  width 100%
  position fixed
  top 0
  left 0
  z-index 999

  .h_top{
    height c(100)
    border-bottom 2px solid #efefef
    display flex
    padding:0 c(33) 0 c(42)
    box-sizing border-box
    align-items center
    font-size c(38)
    color #000000
    justify-content space-between
    font-weight 600
    background #ffffff
    h1{
      font-size c(33)
    }
    .iconfont {
      font-size c(38)
      color #000000
    }
  }
  .h_cen{
    height c(83)
    border-bottom 5px solid #f9f7f9
    tab-item:first-child{
      color #ff4c62
    }
    .navbox{
      height:100%
      display flex
      overflow-x scroll
      li{
        flex-shrink 0
        line-height c(83)
        width c(217)
        font-size c(27)
        color #5f615f
        text-align center
      }
      .li_active{
        color #ff4c62
        border-bottom: 4px solid #ff4c62;
      }
    }
  }
  .h_bot{
    height c(95)
    border-bottom 2px solid #f9f7f9
    background #ffffff
    .navbox2{
      display flex
      height 100%
      align-items center
      li{
        width 25%
        line-height c(40)
        font-size c(27)
        color #393939
        border-right 1px solid #f1f1f1
        text-align center
        white-space nowrap
        overflow hidden
        text-overflow ellipsis

      }
      .chose{
        color #ff495f
      }
    }
  }
  .selections {
    height 2500px
    position relative
    display none
    .bg{
      width 100%
      height 2500px
      background rgba(0,0,0,.4)
      position absolute
      left 0
      top 0
    }
    .secbox{
      position absolute
      left 0
      top 0
      z-index 50
    }
    .area {
      background #fff
      width 100%
      height c(483)
      .list {
        display flex
        padding c(23)
        box-sizing border-box
        flex-wrap wrap
        li {
          width 25%
          padding c(8)
          box-sizing border-box
          div {
            padding c(17) c(22)
            border-radius 5px
            font-size c(27)
            text-align center
            color #363636
            border 1px solid #e8e8e8
            white-space nowrap
            overflow hidden
            text-overflow ellipsis
          }
          .active_div{
            color #ff576d
            border 1px solid #ff576d
          }
        }
      }
    }
    .rank{
        height c(640)
        overflow-y scroll
        ol{
          li{
            line-height c(82)
            color #2a2a2a
            font-size c(28)
            border-bottom 2px solid #f3f3f3
            padding 0 c(18)
            box-sizing border-box
            display flex
            justify-content space-between
            b{
              font-weight 100
            }
          }
          .active_one{
            color #ff6175
          }
      }
    }
    .myrecent{
      /*display block*/
      height c(178)
      ol{
        li{
          line-height c(82)
          color #2a2a2a
          font-size c(28)
          border-bottom 2px solid #f3f3f3
          padding-left c(18)
          b{
            font-weight 100
          }
        }
        .active_one{
          color #ff6175
        }
      }
    }
    .timesec{
      height c(310)
      z-index 100
      /*display block*/
    }
    .special{
      height c(640)
      /*display block*/
      overflow-y scroll
      .TStit{
        margin 0 c(32)
        border-top:1px solid #f3f3f3
        padding-top c(38)
        padding-bottom c(3)
        font-size c(27)
        color #9a9a9a
      }
      .vip{
        li{
          width 33.33%
          div{
            padding c(17) 0
          }
        }
        span{
          font-size c(22)
          color #fea952
        }
      }
    }
  }
  .show{
    display block
  }
  .fixbox{
    background #ffffff
  }
}
.icon-arrLeft-fill{
    /*color #9c9a9c*/
    font-size c(25)
    margin-left c(2)
}
</style>

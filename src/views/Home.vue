<template>
  <div class="home">
    <header @mouseover="mouseIn" @mouseleave="mouseOut">
      <div class="logo"> 
        <img src="../assets/icon/牛油果.png" alt="">
      </div>
      <div class="right">
        <ul>
          <li>
            <a href="#">
              <span>牛油果</span>
            </a>
          </li>
          <li>
            <a href="#">
              <span>作品</span>
            </a>
          </li>
          <li>
            <a href="#">
              <span>联系</span>
            </a>
          </li>
          
          <li :class="{off: isShow == false,on:isShow == true}">
            <a href="#">
              <span>分享</span>
            </a>
          </li>
          <li :class="{off: isShow == false,on:isShow == true}">
            <a href="#">
              <span>公告</span>
            </a>
          </li>
          <li @click="showAll">
            <div class="one"></div>
            <div class="two"></div>
            <div class="three"></div>
          </li>
        </ul>
      </div>
      <div class="search">
        <img src="../assets/icon/问号.png" alt="">
      </div>
    </header>
    <main>
      <div class="pic">
        <img class="img" src="../assets/images/下载.png" alt="">
      </div>
      <div class="container">
        <div class="box" >
          <ul >
            <li v-for="item in Data" :key="item.id">
              <a href="#">
                <div class="blur">
                <div class="name">{{item.name}}
                    <div class="txt1">{{item.txt1}}</div>
                    <div class="txt2">{{item.txt2}}</div>
                </div>
                <div class="url">{{item.url}}</div>
              </div>
              <img :src="item.imgUrl" alt="">
              </a>
            </li>
          </ul>
          
        </div>
      </div>
    </main>
    <div class="more">
      <a href="#">
        <span>mOre works</span>
      </a>
    </div>
    <div class="contact">
      <h2>缔造高品质数字化体验</h2>
      <h3>11年专注高端网站设计，匠心如初</h3>
      <div class="phone">
        <span>&nbsp;&nbsp;1371-4404-889 | 0755-86658621&nbsp;&nbsp;</span>
      </div>
      <div class="mail">
        <a href="#"> 
          <span>微信：renayuen</span>
        </a>
      </div>
      <a class="mail">
        <span>rena@sumaart.com</span>
      </a>
      <a class="mail">
        <span>QQ:2115634603</span>
      </a>
      <div class="person">
        <span>阮小姐 / 设计顾问</span>
      </div>
      <div class="text">
        <h1>深圳网站建设公司</h1>
				素马是一家<strong>具有策略思维及追求设计气质</strong>的互联网品牌设计公司，提供完整的<strong>数字体验设计、开发、运维</strong>服务 - 包括：企业网站建设、小程序开发、UI设计、用户体验设计、VI设计等。在全国、江苏、北京、上海、广州、重庆、杭州、武汉、成都、香港乃致海外均有优秀的客户案例。
      </div>
      <div class="fansLogo">
        <ul>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_10.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_09.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_01.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_02.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_03.png
" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_04.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_05.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_06.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_07.png" alt="">
          </li>
          <li>
            <img src="https://www.sumaarts.com/media/fanslogo/logo_08.png" alt="">
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import Data from '../mock'
export default {
  name: 'Home',
  data(){
    return{
      Data, // 首页数据
      isShow:false
    }
  },
  methods:{
    scrollRun(){
      var header = document.querySelector('header')
      var scroll = document.querySelector('.img').getBoundingClientRect().top
      var w = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth
      console.log(w);
      if(scroll<0 && w>375){
          header.style.padding = '10px 0'
      }else if(scroll<0 && w<=375){
         header.style.padding = '10px 10px'  
      }else if(scroll>0 && w >375){
        header.style.padding = '20px 0px'  
      }else if(scroll>0 && w <=375){
        header.style.padding = '20px 10px'  
      }
    },
    mouseIn(){
      var header = document.querySelector('header')
      if(header.style.padding == "10px 0px"){
        header.style.padding = '20px 0'
      }
       
    },
    mouseOut(){
      var header = document.querySelector('header')
      var scroll = document.querySelector('.img').getBoundingClientRect().top
      if(scroll<0 && header.style.padding == "20px 0px"){
        header.style.padding = '10px 0'
      }
    },
    showAll(){
      this.isShow = ! this.isShow
      
       
    }
  },
  mounted(){
    window.addEventListener('scroll',this.scrollRun)
  },
  destoryed(){
    window.removeEventListener('scroll', this.scrollRun)
  },
  components: {
   
  },
}
</script>
<style scoped lang='less'>
@media screen and (min-width:769px) {
  .home{
  width: 100%;
  position: relative;
  header,main,footer,.more,.contact{
    width: 90%;
    margin: 0 5%;
  }
  header{
    position: fixed;
    top: 0;
    opacity: 1;
    display: flex;
    padding: 20px 0;
    background-color: #fff;
    z-index: 2;
    transition: all ease 1s;
    .logo{
      img{
        margin: 0 40px 0 10px;
        width: 40px;
        height: 40px;
      }
    }
    .right{
      font-size: 16px;
      font-weight: 100;
      ul{
        display: flex;
        justify-content: center;
        li:nth-child(6){
          width: 20px;
          height: 10px;
          margin-top: 15px;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          .one,.two{
            background-color: #333;
            width: 20px;
            height: 2px;
            border-radius: 1px;
            transition: all ease 0.5s;
          }
          .three{
            width: 10px;
            height: 2px;
            background-color: #333;
            border-radius: 1px;
            transition: all ease 0.5s;
          }
        }
        li:nth-child(6):hover{
          .one{
            background-color: #333;
            width: 17px;
            height: 2px;
            border-radius: 1px;
            transition: all ease 0.5s;
          }
          .two{
            background-color: #333;
            width: 9px;
            height: 2px;
            transition: all ease 0.5s;
            border-radius: 1px;
          }
          .three{
            width: 20px;
            height: 2px;
            transition: all ease 0.5s;
            background-color: #333;
            border-radius: 1px;
          }
        }
        .on{
          transition: all ease 1s;
          margin-right: 20px;
          a{
            span{
              display: inline-block;
              line-height: 40px;
              height: 40px;
            }
          }
        }
        .off{
          margin: 0;
          overflow: hidden;
          transition: all ease 1s;
          width: 0;
          a{
            span{
               display: inline-block;
              line-height: 40px;
              height: 40px;
            }
          }
        }
        li{
          transition: all ease 1s;
          margin-right: 20px;
          a{
            span{
              display: inline-block;
              line-height: 40px;
              height: 40px;
            }
          }
        }
      }
    }
    .search{
      margin-left: auto;
      img{
        width: 26px;
        height: 26px;
      }
    }
  }
  main{
    .pic{
      padding-top: 150px;
      width: 100%;
      img{
        width: 500px;
        height: 500px;
        display: block;
        margin: 0 auto;
      }
    }
    .container{
      width: 100%;
      padding-top: 40px;
      .box{

        ul{
          display: grid;
          grid-template-columns: minmax(0, 1fr) minmax(0, 1fr) minmax(0, 1fr) minmax(0, 1fr);
          // grid-template-rows: 300px 300px 300px 300px;
          grid-row-gap: 20px;
          grid-column-gap: 20px;
          grid-auto-flow: dense;
           
          li{
            overflow: hidden;
            position: relative;
            .blur{
              opacity: 0;
              position: absolute;
              background-color: rgba(255, 255, 255, 0.766);
              width: 100%;
              padding: 20px;
              box-sizing: border-box;
              height: 100%;
              display: flex;
              flex-direction: column;
              justify-content: space-between;
              color: #5b5b5b;
              transition: all ease 0.5s;
              .name{
                
                font-size: 18px;
                font-weight: 300;
                div{
                  font-size: 12px;
                }
              }
              .url{
                font-size: 16;
                font-weight: 300;
              }
            }
            img{
              display: block;
              width: 100%;
            }
          }
          li:hover .blur{
            opacity: 100;
            // background-color: red;
          }
          li:nth-child(7){
            grid-column-start: 3;
            grid-column-end: 5;
            grid-row-start: 2;
            grid-row-end: 4;
          }
          li:nth-child(8){
            grid-column-start: 1;
            grid-column-end: 2;
            grid-row-start: 3;
            grid-row-end: 5;
          }
          li:nth-child(11){
            grid-column-start: 3;
            grid-column-end: 4;
            grid-row-start: 4;
            grid-row-end: 6;
          }
          li:nth-child(18){
            grid-column-start: 3;
            grid-column-end: 4;
            grid-row-start: 6;
            grid-row-end: 8;
          }
        }
        
      }
      
    }
  }
  .more{
    padding-top: 40px;
    span{
      display: block;
      padding: 10px;
      text-align: center;
    }
  }
  .contact{
    padding-top: 80px;
    color: #000;
    text-align: center;
    h2{
      font-weight: 300;
      font-size: 30px;
    }
    h3{
      font-weight: 300;
      font-size: 16px;

    }
    .phone{
      font-weight: 300;
      font-size: 18px;
      margin: 30px 0 20px 0;
      span{
        padding: 10px 0;
        border-top: 1px solid #000;
        border-bottom: 1px solid #000;
      }
    }
    .mail{
      font-weight: 300;
      display: block;
      color: #000;
      font-size: 16px;
    }
    .person{
      font-size: 14px;
      margin-top: 10px;
    }
    .text{
      margin: 120px auto 0 auto;
      width: 700px;
      color: #9e9e9e;
      font-size: 18px;
      font-weight: 300;
      h1{
        font-size: 21.6px;
        font-weight: 300;
        color: #333;
      }
      strong{
        font-weight: 300;
        text-decoration: underline;
      }
    }
    .fansLogo{
      padding: 20px;
       ul{
      display: flex;
      flex-flow: wrap;
      justify-content: space-around;
      li{
        margin: 0 10px;
        img{
          height: 30px;
        }
      }
    }
    }
  }
}
}
@media screen and (max-width:768px) {
.home{
  // width: 100%;
  position: relative;
  header{
    width: 100%;
    position: fixed;
    top: 0;
    display: flex;
    padding: 20px 10px;
    justify-content: space-between;
    background-color: #fff;
    box-sizing: border-box;
    transition: all ease 1s;
    .logo{
      img{
        margin: 2px 20px;
        width: 36px;
        height: 36px;
      }
    }
    .right{
      font-size: 16px;
      font-weight: 100;
      margin-left: auto;
      ul{
        display: flex;
        justify-content: center;
        li{
          margin-right: 10px;
          a{
            span{
              display: inline-block;
              line-height: 40px;
              height: 40px;
            }
          }
        }
      }
    }
    .search{
      display: none;
      margin-left: auto;
      img{
        width: 26px;
        height: 26px;
      }
    }
  }
  main{
    .pic{
      padding: 80px 10px 40px 10px;
      // width: 100%;
      text-align: center;
      img{
        width: 340px;
        height: 340px;
        display: block;
        margin: 0 auto;
      }
    }
    .container{
      width: 100%;
      padding: 20px 10px 0 10px;
      box-sizing: border-box;
      .box{
        // border: 1px solid #000;
        width: 100%;
        ul{
          display: grid;
          grid-template-columns:auto auto;
          // grid-template-rows: 300px 300px 300px 300px;
          grid-auto-flow: dense;
           
          li{
            // display: list-item;
            .blur{
              display: none;
            }
            padding: 10px;
            overflow: hidden;
            img{
              width: 100%;
            }
          }
          li:nth-child(7){
            img{
              height: 100%;
            }
          }
          li:nth-child(11){
            grid-column-start: 1;
            grid-column-end: 2;
            grid-row-start: 7;
            grid-row-end: 9;
          }
          li:nth-child(18){
            grid-column-start: 1;
            grid-column-end: 2;
            grid-row-start: 10;
            grid-row-end: 12;
          }
        }
        
      }
      
    }
  }
  .more{
    
    span{
      font-size: 20px;
      display: block;
      padding: 10px;
      text-align: center;
    }
  }
  .contact{
    padding-top: 80px;
    color: #000;
    text-align: center;
    h2{
      font-weight: 300;
      font-size: 30px;
    }
    h3{
      font-weight: 300;
      font-size: 16px;

    }
    .phone{
      font-weight: 300;
      font-size: 18px;
      margin: 30px 10px 10px 10px;
      border-top: 1px solid #000;
      border-bottom: 1px solid #000;
      padding: 10px;
    }
    .mail{
      font-weight: 300;
      display: block;
      color: #000;
      font-size: 16px;
    }
    .person{
      font-size: 14px;
      margin-top: 10px;
    }
    .text{
      display: none;
      margin: 120px auto 0 auto;
      color: #9e9e9e;
      font-size: 18px;
      font-weight: 300;
      h1{
        font-size: 21.6px;
        font-weight: 300;
        color: #333;
      }
      strong{
        font-weight: 300;
        text-decoration: underline;
      }
    }
    .fansLogo{
      padding: 20px;
       ul{
      display: flex;
      flex-flow: wrap;
      justify-content: space-around;
      li{
        margin: 0 10px;
        img{
          height: 30px;
        }
      }
    }
    }
  }
}
}
</style>
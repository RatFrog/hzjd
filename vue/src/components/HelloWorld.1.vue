    <template>
      <div id="app">
        <!-- 头部导航 -->
        <header class="header">
        <el-row>
            <el-col :span="24">
              <el-menu default-active="/index" class="el-menu-demo" mode="horizontal" :router="true">
                <el-menu-item index="/index">网站首页</el-menu-item>
                <el-menu-item index="/success">成功案例</el-menu-item>
                <el-menu-item index="/category">产品中心</el-menu-item>
                <el-menu-item index="/news">新闻中心</el-menu-item>
                <el-menu-item index="/about">关于我们</el-menu-item>
              </el-menu>
            </el-col>
        </el-row>
        </header>
        <div style="position: relative;height: 0px;width: 100%;"></div>

        <main  class="main">
              <!-- 左侧导航 -->
            <div class="main-left">
              <el-menu default-active="/activePublic" class="el-menu-vertical-demo" @select="">
                <el-menu-item index="/activePublic" :class="{'isActive': active}">编辑模式</el-menu-item>
                <el-menu-item index="/activeManage" :class="{'isActive': !active}">网页模式</el-menu-item>
              </el-menu>
            </div>

              <!-- 右侧主内容区 -->
              <div  class="main-right" >
                <!-- 视图 -->
                <router-view class="view"></router-view>
              </div>
        </main>
      </div>
    </template>

    <script>
    import Vue from 'vue'
    import Element from 'element-ui'
    import 'element-ui/lib/theme-default/index.css'

    Vue.use(Element)

    export default {
      name: 'app',
      data: function (){
        return {
          active:true
        }
      }
    }
    </script>

    <style>
      body{margin: 0;}
    #app {
      min-width: 1200px;
      margin: 0 auto;
      font-family: "Helvetica Neue","PingFang SC",Arial,sans-serif;
    }
    /* 头部导航 */
    .header{z-index: 1000;min-width: 1200px;transition: all 0.5s ease;  border-top: solid 4px #3091F2;  background-color: #fff;  box-shadow: 0 2px 4px 0 rgba(0,0,0,.12),0 0 6px 0 rgba(0,0,0,.04);  }
    .header.header-fixed{position: fixed;top: 0;left: 0;right: 0;}
    .header .el-menu-demo{padding-left: 300px!important;}

    /* 主内容区 */
      .main{    display: -webkit-box;  display: -ms-flexbox;  display: flex;  min-height: 800px;  border: solid 40px #E9ECF1;  background-color: #FCFCFC;  }
      .main .main-left{text-align: center;width: 200px;float: left;}
      .main .main-right{-webkit-box-flex: 1;  -ms-flex: 1;  flex: 1;  background-color: #fff; padding: 0px 0px; }
      .main .el-menu{background-color: transparent!important;}
    </style>
<template>
  <div id="app" v-bind:class="[state]">
    <header class="header">
      <div class="box">
        <h1>Lzs's Blog</h1>
        <h3>1242354353245</h3>
        <p class="socials">
            <a href="https://github.com/lzs816" target="_blank" class='icon github'></a>
            <a href="https://weibo.com/u/5525994426" target="_blank" class='icon sina'></a>
            <a href="https://twitter.com/dangerous_cl"  target="_blank" class='icon twitter'></a>
        </p>
      </div>
      <i class="icon-down" v-on:click="rollDown"></i>
      <i class="icon-up" v-on:click="rollUp"></i>
    </header>
    <nav class="navbar">
      <ul class="nav">
        <li><router-link to='/home'>首页</router-link></li>
        <li><router-link to='/posts'>文章</router-link></li>
        <li><router-link to='/gallery'>作品</router-link></li>
        <li><router-link to='/about'>关于</router-link></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      state: ""
    };
  },
  components: {},
  methods: {
    rollDown: function() {
      this.state = "roll-down";
    },
    rollUp: function() {
      this.state = "roll-up";
    },
    handleScroll() {
      console.log(1)
    }
  }
};
</script>

<style lang="less" scoped>
.roll-down {
  transform: translate3d(0, -100%, 0);
}
.roll-up {
  transform: translate3d(0, 0, 0);
}
#app {
  transition: transform 1s;
  width: 100%;
  height: 100%;
  .header {
    position: relative;
    width: 100%;
    height: 100%;
    background: url("./assets/images/theme10.jpg") no-repeat center;
    background-size: cover;
    .box {
      position: absolute;
      top: 40%;
      left: 50%;
      width: 7.5rem;
      transform: translate(-50%, -50%);
      h1 {
        color: white;
        text-align: center;
      }
      h3 {
        color: white;
        text-align: center;
        margin-top: 10px;
      }
      .socials {
        margin: 30px auto 0 auto;
        overflow: hidden;
        width: 210px;
        .icon {
          float: left;
          width: 30px;
          height: 30px;
          margin: 0 20px;
          background-size: 100% 100%;
          border-radius: 5px;
        }
        .github {
          background-image: url("./assets/images/github-10-xxl.png");
        }
        .sina {
          background-image: url("./assets/images/sina-logo.png");
        }
        .twitter {
          background-image: url("./assets/images/Twitter-logo.png");
        }
      }
    }
    .icon-down {
      position: absolute;
      bottom: 5%;
      left: 50%;
      display: block;
      margin: 10px;
      background-image: url("./assets/images/Arrowhead-Down.png");
      background-size: 100% 100%;
      animation: pull-down 1s linear infinite;
      cursor: pointer;
    }
    .icon-down::before {
      content: "Click me";
      position: absolute;
      left: 50%;
      top: 0;
      transform: translate(-50%, -150%);
      color: white;
      white-space: nowrap;
      text-align: center;
      font-weight: 600;
    }
    .icon-up {
      position: absolute;
      top: 200%;
      left: 10px;
      z-index: 2;
      display: block;
      width: 60px;
      height: 60px;
      background-image: url("./assets/images/rocket.png");
      background-size: 100% 100%;
      transform: translate(0, calc(-100% - 0.5rem));
      cursor: pointer;
      opacity: 0.2;
    }
  }
  .navbar {
    width: 100%;
    height: 100px;
    background-color: black;
    .nav {
      width: 7.5rem;
      height: 100%;
      display: flex;
      margin: 0 auto;
      list-style: none;
      li {
        flex: 1;
        height: 100%;
        line-height: 100px;
        text-align: center;
        color: white;
        a {
          position: relative;
          display: block;
          width: 100%;
          height: 100%;
          color: white;
        }
        .router-link-active::before {
          content: "[";
          position: absolute;
          top: 0;
          left: 6px;
          height: 100%;
          font-size: 28px;
        }
        .router-link-active::after {
          content: "]";
          position: absolute;
          top: 0;
          right: 6px;
          height: 100%;
          font-size: 28px;
        }
      }
    }
  }
}
@keyframes pull-down {
  from {
    transform: translate3d(-50%, 0, 0);
    opacity: 0.6;
  }
  to {
    transform: translate3d(-50%, 20px, 0);
    opacity: 0.2;
  }
}
</style>
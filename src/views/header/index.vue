<template>
  <div class="navbar-header">
    <ul class="nav">
      <li v-for="col in navlis" :key="col.prop" :class="col.prop === selectedlLi ? 'selectedlLi' : ''" @click="handleClickFunc(col.prop)">{{col.label}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'Header', // 头部组件
  data () {
    return {
      navlis: [
        {
          prop: 1,
          label: '网站首页'
        },
        {
          prop: 2,
          label: '荣誉资质'
        },
        {
          prop: 3,
          label: '公司业务'
        },
        {
          prop: 4,
          label: '精彩案例'
        },
        {
          prop: 5,
          label: '关于我们'
        },
        {
          prop: 6,
          label: '合作伙伴'
        }
      ],
      selectedlLi: 1
    }
  },
  methods: {
    handleClickFunc (key) {
      this.selectedlLi = key
    }
  }
}
</script>
<style scoped>
.navbar-header {
  box-sizing: border-box;
  display: inline-block;
}
.nav {
  float: left;
  margin: 0 auto;
}
.nav li {
  box-sizing: border-box;
  display: block;
  width: 100%;
  padding: 10px 30px;
  cursor: pointer;
}
@media (min-width: 768px) {
  .nav {
    display: block;
  }
  .nav li {
    float: left;
    width: auto;
    padding: 20px 30px;
  }
}
.selectedlLi {
  border-bottom: 3px solid #ffffff;
}
</style>

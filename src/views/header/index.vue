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
  props: {
    activeNav: {
      default: 'uptop'
    }
  },
  data () {
    return {
      navlis: [
        {
          prop: 'uptop',
          label: '网站首页'
        },
        {
          prop: 'Honor',
          label: '荣誉资质'
        },
        {
          prop: 'Business',
          label: '公司业务'
        },
        {
          prop: 'GoodCase',
          label: '精彩案例'
        },
        {
          prop: 'Aboutus',
          label: '关于我们'
        },
        {
          prop: 'CooperativePartner',
          label: '合作伙伴'
        }
      ],
      selectedlLi: 'uptop'
    }
  },
  watch: {
    activeNav: {
      handler (newVal) {
        this.selectedlLi = this.activeNav
      }
    }
  },
  created () {
    this.selectedlLi = this.activeNav
  },
  methods: {
    handleClickFunc (key) {
      this.selectedlLi = key
      this.$emit('tabClick', key)
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

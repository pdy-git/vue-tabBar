<template>
  <div>
    <MyHeader title="我的title"></MyHeader>
    <div style="padding-top: 45px">
      <component :is="comName"> </component>
    </div>

    <MyTaBar :list="tabList" @change="changeFn"></MyTaBar>
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader.vue";
import MyTaBar from "./components/MyTabBar.vue";
import MyGoodsList from "./views/MyGoodsList.vue";
import MyGoodsSearch from "./views/MyGoodsSearch.vue";
import MyUserInfo from "./views/MyUserInfo.vue";

export default {
  data() {
    return {
      comName: MyGoodsList,
      tabList: [
        {
          iconText: "icon-shangpinliebiao",
          text: "商品列表",
          componentName: "MyGoodsList",
        },
        {
          iconText: "icon-sousuo",
          text: "商品搜索",
          componentName: "MyGoodsSearch",
        },
        {
          iconText: "icon-user",
          text: "我的信息",
          componentName: "MyUserInfo",
        },
      ],
    };
  },
  components: {
    MyHeader,
    MyTaBar,
    MyGoodsList,
    MyGoodsSearch,
    MyUserInfo,
  },
  methods: {
    changeFn(val) {
      this.comName = val;
    },
  },
};
</script>

<style></style>

<template>
  <div id="app">
    <ul>
      <li v-for="(item, i) in num" :key="item.id">
        {{ list[index + i].content }}
      </li>
    </ul>
    <el-pagination
      @current-change="handleCurrentChange"
      :page-size="3"
      :pager-count="11"
      layout="prev, pager, next"
      :total="list.length"
    >
    </el-pagination>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      list: [
        {
          id: 1,
          content: "1",
        },
        {
          id: 2,
          content: "2",
        },
        {
          id: 3,
          content: "3",
        },
        {
          id: 4,
          content: "4",
        },
        {
          id: 5,
          content: "5",
        },
        {
          id: 6,
          content: "6",
        },
        {
          id: 7,
          content: "7",
        },
        {
          id: 8,
          content: "8",
        },
        {
          id: 9,
          content: "9",
        },
        {
          id: 10,
          content: "10",
        },
        {
          id: 11,
          content: "11",
        },
        {
          id: 12,
          content: "12",
        },
        {
          id: 13,
          content: "13",
        },
        {
          id: 14,
          content: "14",
        },
      ],
      index: 0,
      num: 3
    };
  },
  methods: {
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`);
      if(val == 1){
        this.index = 0
      }
      if(val == 2){
        this.index = 3
      }
      if(val == 3){
        this.index = 6
      }
      if(val > 3){
        this.index = val * 3 - 3
      }
      this.num = this.list.length - (val - 1) * 3
      if(this.num >= 3){
        this.num = 3
      }
      if(this.num < 3){
        this.num = this.list.length - (val - 1) * 3
      }
      if(this.num < 0){
        this.num = 0
      }
    },
  },
};
</script>

<style>
</style>

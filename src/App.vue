<template>
  <div id="app">
    <p>入力してください</p>
    <input type="text" v-model="form.str">
    <input type="text" v-model="form.tag">
    <button type="submit" @click="clickEvent">登録</button>
    <ul v-for=" (view,i) in views" :key="i">
      <li>タスク名:{{ view.str }} タグ:{{ view.tag }}<button @click="deleteEvent(i)">削除</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      form:{
        str:"",
        tag:""
      },
      dir:{
        str:"",
        tag:"",
      },
      views:[]
    }
  },
  methods: {
    clickEvent(){
      this.dir["str"] = this.form.str
      this.dir["tag"] = this.form.tag
      this.views.push(this.dir)
    },
    deleteEvent(index){
      this.views.splice(index,1)
    }
  }
}
</script>

<style>
*{
  font-size:20px;
}
</style>
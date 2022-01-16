<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
     <!-- 문구밑에 문자열 입력란과 버튼 -->
    <input type="text" :value="message" @input="changeMessage"/>
    <button v-on:click="submit">제출</button>
    <button v-on:click="notify">알림</button>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      message: '',
      count: 0,
    };
  },
  methods: {
    // 입력했을때 메소드
    changeMessage(e) {
      this.message = e.target.value;
    },
    // 제출이벤트 메소드
    submit() {
      // 버튼 누르면 input엡력된 문자열과 바로 밑에 표시되는 문자열 왼쪽으로 1칸씩 회전
      this.message = this.message.slice(1) + this.message.slice(0, 1);
      console.log(this.message);
    },
    // 알림이벤트 메소드
    notify() {
      // input에 입력된 문자열과 버튼 누른 횟수 보여주는 알림창
      this.count += 1;
      alert(`${this.message} ${this.count}`);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

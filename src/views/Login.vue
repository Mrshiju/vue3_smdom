<template>
  <div class="home">
     <label for="username">用户名</label>
     <input type="text" placeholder="输入用户名">
     <label for="pwd">密码</label>
     <input type="text" name="pwd" id="" placeholder="输入密码">
     <button @click="submit">
         {{msg}}
     </button>
     <router-view></router-view>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';
@Component
export default class Login extends Vue {
  public msg: string = '提交';
//   interface  Days:enum Sun=1, Mon, Tue, Wed, Thu, Fri, Sat};
//  @Prop() private msg!:string;
  private submit() {
      this.msg = this.msg === '提交' ? '已提交' : '提交';
      if (this.$route.fullPath === '/myself') {
          return;
      } else {
          this.$router.push('/myself');
      }
  }
}
</script>

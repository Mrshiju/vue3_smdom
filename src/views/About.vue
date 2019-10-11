<template>
  <div class="about">
    <h1>This is an about page</h1>
    <HelloWorld msg="今天天气不好"></HelloWorld>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
// @Component
@Component({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {
  public beforeRouteEnter(to:string, from:string, next: () => void): void {
    // console.log(from,to);
    next();
  }
  public beforeRouteUpdate(to:string, from:string, next: () => void): void {
    // console.log(from, to); // 暂时不生效，版本问题
    next();
  }
  public beforeRouteLeave(to:string, from:string, next: () => void): void {
    // console.log(from);
    next();
  }
}
</script>


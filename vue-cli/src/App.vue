<template>
  <!-- 최상위 노드는 1개만 있어야 한다. -->
  <div>
    <!-- {{ str }} -->
    <app-header 
      v-bind:propsdata="str"
      v-on:renew="renewStr"></app-header>
    <!-- v-bind:프롭스속성이름(appHeaderApp.vue)="상위컴포넌트(.vue)의 데이터이름" -->
  </div>
</template>


<script>
// 재사용을 많이하는데, ..data도 많이사용하고..그래서 data: 하고 리터럴로작선
// 하지 않고 함수로 표시한 후 return 뒤에 객체로 작성한다.
// 변수, 메서드, 이벤트, 에밋, 프롭스 다 가능함.

// 외부 단일컴포넌트 임포트
import AppHeader from './components/AppHeader.vue';

export default {
  data: function(){
    return {
      str: 'Header'
    }
  },
  components: {
    'app-header': AppHeader
  },
  methods: {
    renewStr: function(){
      this.str = 'HiHiHi'
    }
  }
}
</script>
  
<style>

</style>
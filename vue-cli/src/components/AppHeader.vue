<template>
  <!-- 컴포넌트는 파스칼케이스로 네이밍하고(예를들어 AppHeader)
        최소한 두글자 이상을 조합하여 지어야한다. (예를들어 AppHeader)
        이유는 : html표준태그인지, 컴포넌트의 태그인지 브라우저는 알 수 없어
        그래서 컴포넌트태그는 최소한 두 단어로, 한단어로 할 경우에는 충돌
        나지 않도록....해야하는데 걍 두단어로해라.-->
    <header>
        <h1>{{propsdata}}</h1>
        <button v-on:click="sendEvent">send</button>
    </header>

</template>

<script>
export default {
    props: ['propsdata'],
    methods: {
        sendEvent: function(){
            //AppHeader.vue에서 App.vue로 보낼 이벤트의 이름.
            this.$emit('renew');
        }
    }
}
</script>

<style>

</style>
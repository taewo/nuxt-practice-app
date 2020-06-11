<template>
  <div>

    <child>
      <template slot="header" slot-scope="slotProps">
      <h1>모달 제목</h1>
      <button @click="slotProps.close">닫기</button>
        {{ slotProps }} <!-- { hello: 'hello' } -->
      </template>


      <p slot="content">모달의 컨텐츠입니다.</p>


    </child>



  </div>
</template>
<script>
import child from '~/components/child'
export default {
  components: {child},
  data() {
    return {
      text: ''
    }
  },
}
</script>
<style lang=''>

</style>

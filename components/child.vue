<template>
  <div>
    <header>
      <slot name="header" :hello="childData" :active="active" :close="close">
        <strong>기본 타이틀</strong>
        <button>기본 버튼</button>
      </slot>
    </header>
    <div>
      <slot name="content">
        <p>기본 콘텐츠</p>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseModal",
  data() {
    return {
      childData: "hello",
      active: false
    };
  },
  methods: {
    close() {
      console.log('close')
      this.active = false
    }
  }
}
</script>

<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <button v-bind:class="{'btn': true, 'btn--outlined': outlined}" v-bind:type="type">
    <slot></slot>

  </button>
</template>

<script>
  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Button',
    props: {
      type: {
        type: String,
        default: 'button'
      },
      outlined: {
        type: Boolean,
        default: false

      }

    }
  }
</script>

<!-- <style lang="scss" scoped> -->
<style scoped>
  .btn {
    display: inline-block;
    font-size: 18px;
    background-color: #FF662D;
    color: black;
    cursor: pointer;
    min-width: 220px;
    padding: 8px 15px;
    border-radius: 3px;
    border: 1px solid transparent;
  }
  .btn:hover{
    background-color: blue;
    color: aliceblue;
  }
  .btn--outlined{
    background: none;
    border: 1px solid #FF662D;
  }
</style>
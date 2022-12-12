<!-- eslint-disable vue/no-deprecated-dollar-listeners-api -->
<template>
    <Container>
        <input type="text" class="custom-input" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"/>
    </Container>
</template>

<script>
    import Container from './Container.vue'
    export default {
        name: 'CustomInput',
        components: {
        Container
        },
        props: {
        modelValue: {
        type: String,
        default: ''
        }
    },
    emits: ['update:modelValue'],
    }
</script>

<style lang="scss" scoped>
  @import '../../assets/scss/index.scss';
.wrapper-input {
  position: relative;
  display: inline-flex;
}
.custom-input {
  height: 40px;
  width: 100%;
  border: 2px solid $main-color;
  font-size: 18px;
  outline: none;
  line-height: inherit;
  padding: 8px 15px;
  &::placeholder {
    color: inherit;
  }
  &--error {
    border-color: $error-color;
  }
  &__error {
    position: absolute;
    top: 100%;
    right: 0;
    width: 100%;
    font-size: 12px;
    color: $error-color;
    line-height: 1.3;
  }
}
</style>
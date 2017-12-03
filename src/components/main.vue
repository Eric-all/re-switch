<template>
  <span :class="classes" @click="handleClick">
    <span :class="[`${prefixCls}-inner`]">
      {{ defaultChecked ? checkedChildren : unCheckedChildren }}
    </span>
  </span>
</template>

<script>
  import '../styles/index.less'
  import classnames from 'classnames'
  export default {
    name: 'Switch',
    props: {
      prefixCls: {
        type: String,
        default: 're-switch'
      },
      checked: Boolean,
      disabled: Boolean,
      checkedChildren: null,
      unCheckedChildren: null
    },
    data () {
      return {
        defaultChecked: this.checked
      }
    },
    methods: {
      handleClick (e) {
        if (this.disabled) return
        this.defaultChecked = !this.defaultChecked
        this.$emit('toggle', this.defaultChecked)
      }
    },
    computed: {
      classes () {
        return classnames({
          [`${this.prefixCls}`]: true,
          [`${this.prefixCls}-checked`]: this.defaultChecked,
          [`${this.prefixCls}-disabled`]: this.disabled
        })
      }
    }
  }
</script>

<template>
  <div class="container">
    <h2>按钮类型</h2>
    <section class="container-content">
      <amber-button type="default">默认按钮</amber-button>
      <amber-button type="primary">主要按钮</amber-button>
      <amber-button type="success">成功按钮</amber-button>
      <amber-button type="info">信息按钮</amber-button>
      <amber-button type="warning">警告按钮</amber-button>
      <amber-button type="danger">危险按钮</amber-button>
    </section>
    <h2>禁用状态</h2>
    <section class="container-content">
      <amber-button type="default" disabled>默认按钮</amber-button>
      <amber-button type="primary" disabled>主要按钮</amber-button>
      <amber-button type="success" disabled>成功按钮</amber-button>
      <amber-button type="info" disabled>信息按钮</amber-button>
      <amber-button type="warning" disabled>警告按钮</amber-button>
      <amber-button type="danger" disabled>危险按钮</amber-button>
    </section>
    <h2>按钮形状</h2>
    <section class="container-content">
      <amber-button type="primary">主要按钮</amber-button>
      <amber-button round type="success">成功按钮</amber-button>
    </section>
    <h2>加载状态</h2>
    <section class="container-content">
      <amber-button loading type="primary"></amber-button>
      <amber-button loading type="success" loading-text="加载中..."></amber-button>
    </section>
    <h2>按钮尺寸</h2>
    <section class="container-content">
      <amber-button size="large">大号按钮</amber-button>
      <amber-button size="normal">普通按钮</amber-button>
      <amber-button size="small">小型按钮</amber-button>
      <amber-button size="mimi">迷你按钮</amber-button>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {
    const methods = {
      handleClick(e: Event) {
        console.log('点击了按钮', e)
      }
    }

    return {
      ...methods
    }
  }
})
</script>
<style lang="scss" scoped>
.container {
  position: relative;
  h2 {
    padding: 10px 0;
    font-weight: 400;
    font-size: 14px;
    color: #5e6d82;
  }
  &-content {
    overflow: hidden;
    .amber-button {
      margin-bottom: 10px;
    }
  }
}
</style>

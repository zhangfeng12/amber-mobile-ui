<template>
  <div class="index">
    <div class="index-header">
      <div class="info">
        <h1>AmberMobileUI</h1>
        <p>一块医药移动端 Vue3 组件库</p>
      </div>
    </div>
    <div class="index-components">
      <ol v-for="_nav in nav" :key="_nav">
        <li>{{ _nav.name }}</li>
        <ul>
          <template v-for="_package in _nav.packages">
            <li v-if="_package.show" :key="_package">
              <router-link :to="_package.name.toLowerCase()"
                >{{ _package.name }}&nbsp;&nbsp;{{ _package.cName }}
              </router-link>
              <amber-icon size="14px" color="#979797" name="right"></amber-icon>
            </li>
          </template>
        </ul>
      </ol>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
import { nav } from '../config.json'

export default defineComponent({
  name: 'docsPage',
  setup() {
    console.log(nav)
    const methods = {
      sendToParent() {
        window.parent.postMessage(
          {
            msg: 'AmberMobile',
            key: 'AmberMobile'
          },
          '*'
        )
      }
    }
    return reactive({
      nav,
      ...methods
    })
  }
})
</script>
<style lang="less" scoped>
.index {
  height: 100%;
  width: 100%;
  padding-top: 30px;

  &-header {
    display: flex;
    align-items: center;
    padding: 0 34px;
    height: 117px;
    > img {
      width: 67px;
      height: 67px;
      margin-right: 18px;
      flex-shrink: 0;
    }
    .info {
      display: flex;
      flex-direction: column;
      h1 {
        height: 48px;
        line-height: 48px;
        font-size: 34px;
        color: rgba(51, 51, 51, 1);
      }
      p {
        height: 18px;
        line-height: 18px;
        font-size: 12px;
        color: rgba(154, 155, 157, 1);
      }
    }
  }
  &-components {
    box-sizing: border-box;
    background: #f7f8fa;
    border-radius: 30px 30px 0 0;
    overflow: hidden;
    padding: 30px 25px;
    > ol {
      margin-bottom: 17px;
      > li {
        line-height: 20px;
        font-size: 14px;
        color: rgba(144, 156, 164, 1);
        margin-bottom: 10px;
      }
      > ul {
        li {
          display: flex;
          align-items: center;
          padding: 0 24px;
          height: 45px;
          line-height: 45px;
          background: rgba(255, 255, 255, 1);
          border-radius: 22px;
          box-shadow: 0px 1px 4px 0px rgba(102, 102, 102, 0.06);
          margin-bottom: 13px;
          a {
            width: 100%;
            height: 100%;
            font-size: 15px;
            font-weight: bold;
            display: block;
            color: rgba(51, 51, 51, 1);
          }
        }
      }
    }
  }
}
</style>

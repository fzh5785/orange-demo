<template>
  <div>
    <div style="padding-top: 16px;">
      <p><strong>使用 offset 可以将列向右侧偏。</strong></p>
      <div class="global">
        <g-row>
          <g-col :span="8">
            <div class="content bg-color-dark">8</div>
          </g-col>
          <g-col :span="8" :offset="8">
            <div class="content bg-color">8</div>
          </g-col>
        </g-row>
      </div>
      <p>
        <strong>代码</strong>
      </p>
      <pre><code>{{content}}</code></pre>
    </div>
  </div>
</template>


<script>
  import Row from '../../../src/grid/row'
  import Col from '../../../src/grid/col'

  export default {
    components: {
      'g-row': Row,
      'g-col': Col,
    },
    data() {
      return {
        content: `
          <g-row>
            <g-col :span="8" >
              <div class="content bg-color-dark">8</div>
            </g-col>
            <g-col :span="8" :offset="8">
              <div class="content bg-color">8</div>
            </g-col>
          </g-row>
      `.replace(/^ {8}/gm, '').trim(),
      }
    }
  }
</script>

<style lang="scss" scoped>
  $bgc: rgb(44, 62, 80);
  .bg-color-dark {
    background: $bgc;
  }

  .bg-color {
    background: lighten($bgc, 30%);
  }
  .content {
    min-height: 36px;
    width: 100%;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .row {
    margin: 10px 0;
    height: 36px;
  }
  .global {
    border: 1px solid #ebebeb;
    border-radius: 3px;
    align-items: center;
    padding: 20px 20px;
    margin: 0 .5em;
  }
</style>
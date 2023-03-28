<template>
  <div>
    <h2>自定義元件</h2>
    <slot name="header"></slot>
    <div>
      <slot></slot>
    </div>
    <slot name="footer"></slot>
  </div>
</template>

<script>
  // 這個元件包含三個插槽，分別是 header、default 和 footer。 
  // header 和 footer 插槽是具有命名的插槽，而 default 插槽是未命名的默認插槽。

  export default {
    name: 'CustomComponent'
  }
</script>
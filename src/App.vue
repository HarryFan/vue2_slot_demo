<template>
  <div id="app">

    <CustomComponent>
      <template slot="header">
        <h3>這是自定義的標題</h3>
      </template>
      <p>這是自定義的元件內容</p>
      <template #footer>
        <div>
          <p>版權所有 2023。</p>
        </div>
      </template>
    </CustomComponent>
  </div>
</template>

<script>

// 在上面的示例中，我們使用 SlotComponent 元件，並將三個不同的元素分別插入 header、default 和 footer 插槽中。 結果會顯示為以下內容：
// 注意，我們在使用 SlotComponent 元件時，通過 <template> 元素的 slot 屬性來定義每個插槽的內容。 然後，我們將每個 <template> 元素作為子元素傳遞給 CustomComponent 元件。

  import CustomComponent from './components/CustomComponent.vue'
  export default {
    name: 'App',
    components: {
      CustomComponent
    }
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
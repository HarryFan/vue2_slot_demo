技術文件 \- Vue 2 插槽範例
==================

本文將介紹一個 Vue 2 的插槽範例，展示如何在組件中使用插槽來實現靈活的內容和樣式自定義。

源代碼
---

以下是源代碼，包含一個自定義組件 CustomComponent 和一個使用 CustomComponent 的示例組件。

```
<!-- CustomComponent.vue --><template>
  <div>
    <h2>自定義元件</h2>
    <slot name="header"></slot>
    <div>
      <slot></slot>
    </div>
    <slot name="footer"></slot>
  </div></template><script>export default {  name: 'CustomComponent'}</script>
```

```
<!-- App.vue --><template>
  <div>
    <custom-component>
      <template slot="header">
        <h3>這是自定義元件的標題</h3>
      </template>
      <p>這是自定義元件的內容。</p>
      <template slot="footer">
        <p>版權所有 2023。</p>
      </template>
    </custom-component>
  </div></template><script>import CustomComponent from './CustomComponent.vue'export default {  components: {    CustomComponent
  }
}</script>
```

使用說明
----

### CustomComponent 組件

CustomComponent 組件包含三個插槽，分別是 `header`、`default` 和 `footer`。 `header` 和 `footer` 插槽是具有命名的插槽，而 `default` 插槽是未命名的默認插槽。

在使用 CustomComponent 組件時，您可以通過插槽將任意內容傳遞給組件，從而實現靈活的內容和樣式自定義。

#### header 插槽

header 插槽用於在 CustomComponent 組件的標題位置插入自定義內容。要使用 header 插槽，您可以在 CustomComponent 組件中使用以下代碼：

```
<slot name="header"></slot>
```

然後，在使用 CustomComponent 組件時，您可以使用以下代碼將自定義的內容傳遞給 header 插槽：

```
<custom-component>
  <template slot="header">
    <!-- 在這裡插入自定義內容 -->
  </template>
  <!-- 其他內容 --></custom-component>
```

#### default 插槽

default 插槽用於在 CustomComponent 組件的內容位置插入自定義內容。要使用 default 插槽，您可以在 CustomComponent 組件中使用以下代碼：

```
<div>
  <slot></slot></div>
```

然後，在使用 CustomComponent 組件時，您可以使用以下代
碼將自定義的內容傳遞給 default 插槽：

```
<custom-component>
  <!-- 在這裡插入自定義內容 --></custom-component>
```

#### footer 插槽

footer 插槽用於在 CustomComponent 組件的頁腳位置插入自定義內容。要使用 footer 插槽，您可以在 CustomComponent 組件中使用以下代碼：

```
<slot name="footer"></slot>
```

然後，在使用 CustomComponent 組件時，您可以使用以下代碼將自定義的內容傳遞給 footer 插槽：

```
<custom-component>
  <!-- 其他內容 -->
  <template slot="footer">
    <!-- 在這裡插入自定義內容 -->
  </template></custom-component>
```

### App 組件

App 組件使用 CustomComponent 組件來展示如何使用插槽實現靈活的內容和樣式自定義。

在 App 組件中，我們首先要將 CustomComponent 組件引入到 App 組件中，使用以下代碼：

```
<script>import CustomComponent from './CustomComponent.vue'export default {  components: {    CustomComponent
  }
}</script>
```

然後，在 App 組件的模板中，我們可以使用以下代碼來使用 CustomComponent 組件：

```
htmlCopy code<custom-component>
  <template slot="header">
    <h3>這是自定義元件的標題</h3>
  </template>
  <p>這是自定義元件的內容。</p>
  <template slot="footer">
    <p>版權所有 2023。</p>
  </template></custom-component>
```

在上面的代碼中，我們使用 header 插槽將一個標題插入到 CustomComponent 組件中，使用 default 插槽將一個段落插入到 CustomComponent 組件中，使用 footer 插槽將一個版權聲明插入到 CustomComponent 組件中。

總結
--

本文介紹了一個 Vue 2 的插槽範例，展示如何在組件中使用插槽來實現靈活的內容和樣式自定義。通過這個範例，您可以學習如何使用命名和未命名的插槽，以及如何在不同的組件中共享代碼。如果您正在開發 Vue 2 的應用程序，這個範例可以為您提供有用的參考和指導。
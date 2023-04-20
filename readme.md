
<h1 align="center">vue-canvas-compression</h1>

<p>
  <a href="https://github.com/vuejs/vue">
    <img src="https://img.shields.io/badge/vue-2.5.21-brightgreen.svg" alt="vue">
  </a>

  <a href="https://github.com/GavinZhuLei/vue-form-making/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/GavinZhulei/vue-form-making" alt="license">
  </a>

</p>


利用canvas压缩图片并支持上传到指定服务器的vue组件。
支持配置
  压缩百分比
  图片宽度
  输出图片的类型
  支持选择的图片类型
  其他扩展待完善...

![配置宽度后和压缩比例 后的效果](https://img-blog.csdnimg.cn/40cbb2f019ef49fe88c223e297e27a90.jpeg#pic_center)


## 安装使用

```bash
$ npm install --save vue-canvas-compression
```

全局注册组件

```javascript
//main.js
import Vue from 'vue'
import VueCanvasCompression from 'vue-canvas-compression'

Vue.component('VueCanvasCompression', VueCanvasCompression)
```

局部注册组件

```vue
<template>
  <div id="app">
    <vue-canvas-compression
      @getOriginal="getOriginal"
      @success="success"
      @error="error"
      :preview="true"
      :width='200'
    >
      <button>上传图片</button>
    </vue-canvas-compression>
  </div>
</template>

<script>
import VueCanvasCompression from 'vue-canvas-compression'
export default {
  name: 'app',
  components:{
    VueCanvasCompression
  },
  methods: {
    getOriginal: function (file) {
      console.log('原始图片信息', file);
    },
    success(file) {
      console.log('压缩后图片信息', file);
    },
    error(e) {
      console.log(e);
    }
  },
}
</script>

<style>
</style>

```


## Props
**accept**<br/>
类型: `String`<br/>必需: `false`<br/>默认: `image/*`

可选的图片类型。

```vue
<vue-canvas-compression accept="image/*" @success="success" />
```

**width**<br/>
类型: `Number`<br/>必需: `false`<br/>默认: `0`

当不传width时图片保留原始尺寸。


```vue
<vue-canvas-compression :width="200" />
```

**quality**<br/>
类型: `Number`<br/>必需: `false`<br/>默认: `1`

定义压缩比例。

```vue
<vue-canvas-compression :quality="0.8" />
```

**preview**<br/>
类型: `Boolean`<br/>
必需: `false`<br/>
默认: `false`

是否展示压缩前后的图片。

```vue
<vue-canvas-compression preview />
```


## Events
**getOriginal**<br/>
参数: params<br/>

返回参数是一个File,里面包含原始的图片信息。  

**success**<br/>
参数: params<br/>

返回参数是一个Object,里面包含压缩后的file文件信息。  

**error**<br/>
参数: params<br/>

返回参数是一个Object,里面包含压缩失败的错误信息。  

```vue
<template>
  <div id="app">
    <vue-canvas-compression
      @getOriginal="getOriginal"
      @success="success"
      @error="error"
      :preview="true"
      :width='200'
    />
  </div>
</template>

<script>
import VueCanvasCompression from 'vue-canvas-compression'

export default {
  name: 'app',
  components: {
    VueCanvasCompression
  },
  methods: {
    getOriginal: function (file) {
      console.log('原始图片信息', file);
    },
    success(file) {
      console.log('压缩后图片信息', file);
    },
    error(e) {
      console.log(e);
    }
  },
}
</script>

```



## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.

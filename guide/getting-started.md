---
title: 起步
editLink: true
---



# 安装/使用
确认系统中已安装node，通过npm或者yarn等包管理器来进行安装

### 安装

::: code-group
```bash [Yarn]
$ yarn add v-mapbox-gl
```
```bash [Npm]
$ npm install v-mapbox-gl
```
::: 

### 使用
入口
::: code-group
```ts [Ts]
import { createApp } from 'vue'
import './style.css'
import App from './App.vue'
import 'v-mapbox-gl/dist/style.css'
import mapboxVue from 'v-mapbox-gl'
const app = createApp(App)
/**
 * option : { accessToken?: string }
 */
app.use(mapboxVue, {
  accessToken: 'pk.xxxxxxx'
})
app.mount('#app')
```
```js [Js]
import { createApp } from 'vue'
import './style.css'
import App from './App.vue'
import 'v-mapbox-gl/dist/style.css'
import mapboxVue from 'v-mapbox-gl'
const app = createApp(App)
app.use(mapboxVue, {
  accessToken: 'pk.xxxxxxx'
})
app.mount('#app')
```
::: 
组件
::: code-group
```vue [Ts]
<template>
	<Mapbox :options="options" @register="register"></Mapbox>
</template>
<script lang="ts" setup>
import { useMapbox } from 'v-mapbox-gl';
import type { MapboxOptions } from 'mapbox-gl';

const options: Partial<MapboxOptions> = {
	style: 'mapbox://styles/mapbox/satellite-v9',
	center: [107.132759, 34.784138],
	zoom: 4,
	// accessToken: 'pk.xxxxxx',
};

const { getMapInstance, register } = useMapbox();

</script>

```
```vue [Js]
<template>
	<Mapbox :options="options" @register="register"></Mapbox>
</template>
<script lang="ts" setup>
import { useMapbox } from 'v-mapbox-gl';

const options = {
	style: 'mapbox://styles/mapbox/satellite-v9',
	center: [107.132759, 34.784138],
	zoom: 4,
	// accessToken: 'pk.xxxxxx',
};

const { getMapInstance, register } = useMapbox();

</script>
```
::: 

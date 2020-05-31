<p align="center">
    <a href="https://splidejs.com" target="_blank">
        <img width="120px" src="images/splide-logo.png">
    </a>
    <a href="https://vuejs.org/" target="_blank">
        <img width="120px" src="images/vue-logo.png">
    </a>
</p>

# Vue Splide
**[Vue](https://vuejs.org/) component for the [Splide](https://github.com/Splidejs/splide) slider library.**
* [Document](https://splidejs.com/integration-vue-splide/)
* [Splide](https://github.com/Splidejs/splide)

## Installation
Get the latest version by NPM:
```bash
$ npm install @splidejs/vue-splide
```

## Registration
### Global Registration
Import vue-splide and install into Vue:
```javascript
import Vue from 'vue';
import App from './App';
import VueSplide from '@splidejs/vue-splide';

Vue.use( VueSplide );

new Vue( {
  el    : '#app',
  render: h => h( App ),
} );
```

### Local Registration
Import Splide and SplideSlide components:
```javascript
import { Splide, SplideSlide } from '@splidejs/vue-splide';

export default {
  components: {
    Splide,
    SplideSlide,
  },
}
```

### CSS
Import [styles](https://splidejs.com/themes/) if you need.
```javascript
import '@splidejs/splide/dist/css/themes/splide-default.min.css';
// or
import '@splidejs/splide/dist/css/themes/splide-sea-green.min.css';
// or
import '@splidejs/splide/dist/css/themes/splide-skyblue.min.css';
```

## Options
The `Splide` component accepts [options](https://splidejs.com/options/) as an object:
```javascript
<splide :options="yourOptions"></splide>
```

## Listening to Events
You can listen to all [Splide events](https://splidejs.com/events/) through the `Splide` component. The callback function name is generated by original event names, adding an "splide:" prefix. For example, "arrow:mounted" will be "splide:arrow:mounted".
```javascript
<splide @splide:arrow:mounted="onArrowMounted"></splide>
```
Note that the first argument is the splide instance, meaning original arguments are shifted by one.

## Examples
Here is a small example:
```javascript
<template>
  <splide :options="options">
    <splide-slide>
      <img src="image1.jpg">
    </splide-slide>
    <splide-slide>
      <img src="image2.jpg">
    </splide-slide>
    <splide-slide>
      <img src="image3.jpg">
    </splide-slide>
  </splide>
</template>

<script>
  export default { 
    data() {
      return {
        options: {
          rewind : true,
          width  : 800,
          gap    : '1rem',
        },
      };
    },
  }
</script>
```
More examples:
* [Basic example](https://github.com/Splidejs/vue-splide/blob/master/src/js/examples/components/BasicExample.vue)
* [Autoplay](https://github.com/Splidejs/vue-splide/blob/master/src/js/examples/components/AutoplayExample.vue)
* [Thumbnails](https://github.com/Splidejs/vue-splide/blob/master/src/js/examples/components/ThumbnailsExample.vue)
* [Dynamic slides](https://github.com/Splidejs/vue-splide/blob/master/src/js/examples/components/DynamicSlidesExample.vue)

## License
Vue Splide and Splide are released under the MIT license.  
© 2020 Naotoshi Fujita
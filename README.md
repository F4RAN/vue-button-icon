easy to use vue button with animations and icons

**Demo:**  [http://byParsa.me/Plugins/vue-button-icon](http://byParsa.me/Plugins/vue-button-icon)

## vue-button-icon
### Install

    npm install vue-js-modal --save

## How to use

### Globally : 
Import plugin in your  `main.js`  file globally.

    import vueButtonIcon from  'vue-button-icon';
    Vue.use(vueButtonIcon)
    /*
    
    Example:
    
    Vue.use(vueButtonIcon, { color: "white" })
    
    ...
    
    <vue-button-icon color="white"></vue-button-icon>
    
    */
### Locally : 
Import plugin in your `component` directly.

    import { ButtonComponent } from  'vue-button-icon'
    
    export  default {
    
	    components:{
		    ButtonComponent
		}
    }

## Props:

|Name|Type|Default|Description|
|--|--|--|--|
| `color` | String | #ffffff | `color` define button text and button icon color|
|`width`|Number|200|`width` property allows you change the width optional|
|`block`|Boolean|false|`block` if true width = 100% of block => `width` property disable
`icon`|String|fa fa-instagram | `icon` property allows you to use the fontawesome icons with class name , you can use custom classes too 
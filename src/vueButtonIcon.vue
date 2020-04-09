<template>


<button
  @mouseover="mouseover = true"
  @mouseout="mouseover = false"
  @click="onClick"
  @dblclick="onDoubleClick"
  style="position:relative"
  :style="!mouseover ? {'color' : color , 'width' : width + 'px'} : {'color' : color , 'width' : width + 'px' , 'background-position' : - width / 5 + 'px'}"
  :class="[
   'btn addToCard',
   'btn addToCard--' + bgcolor,
   {
    'btn addToCard--rounded': rounded,
    'btn addToCard--block': block
   }
  ]"
 >
<i :class="icon" style="position:absolute;color:white;font-size:15pt;padding:2px" :style="{'right': 'calc('+ width / 10 + 'px ' + '- 7.5pt)' , 'color' : color}"></i>
  <slot></slot>
 </button>

</template>
<script>

export default {
data(){
    return{
        mouseover: false
    }
},
 props: {
width: {
   type: Number,
   default: 200,
  },
color: {
   type: String,
   default: "#ffffff",
  },
    icon: {
   type: String,
   default: 'fa fa-instagram'
  },

block: {
   type: Boolean,
   default: false,
  },
 },

 methods: {
  onClick(event) {
   this.$emit("click", event);
  },

  onDoubleClick(event) {
   this.$emit("dblclick", event);
  },
 }
};
</script>
<style >
@import './fa/css/font-awesome.min.css';
.btn {
    display: inline-block;
    font-weight: 600;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    border: 1px solid transparent;
    padding: .375rem .75rem;
    font-size: 1rem;
    line-height: 1.5;
    border-radius: .25rem;
    transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out,box-shadow .15s ease-in-out;
}
.addToCard--block {
    display: block;
    width: 100%!important;
} 
.addToCard{

    background: rgb(254, 76, 80); /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, rgb(254, 76, 80), #b91d73); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, rgb(254, 76, 80), #b91d73); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    transition: background 500ms ease-out;
}
.addToCard--mouseover{
 background-position:-100px;
 }

/* .nice-handsome-button {
 display: inline-block;
 outline: 0;
 border: 1px solid rgba(0, 0, 0, 0.1);
 color: #ffffff;
 font-weight: 500;
 font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
 user-select: none;
 cursor: pointer;
}



.nice-handsome-button--blue {
 background-color: #0194ef;
}

.nice-handsome-button--green {
 background-color: #1bb934;
}

.nice-handsome-button--red {
 background-color: #e1112c;
}



.nice-handsome-button--small {
 padding: 8px 10px;
 border-radius: 4px;
 font-size: 12px;
 line-height: 12px;
}

.nice-handsome-button--default {
 padding: 12px 14px;
 border-radius: 6px;
 font-size: 14px;
 line-height: 16px;
}

.nice-handsome-button--large {
 padding: 16px 18px;
 border-radius: 8px;
 font-size: 16px;
 line-height: 20px;
} 



.nice-handsome-button--rounded {
 border-radius: 60px;
} */
</style>
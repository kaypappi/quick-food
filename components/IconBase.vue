<template>
  <div
    v-html="require(`../static/svgs/${icon}.svg?raw`)"
    :class="[iconClass]"
    :style="{height, width}"
  />
</template>

<script>
export default {
  props: {
    icon: {
      type: String,
      required: true
    },
    iconClass:String,
    height:{
        type:String,
        default:'1em'
    },
    width:{
        type:String,
        default:'1em'
    },
  },
  mounted() {
      
    
    this.$el.firstElementChild.removeAttribute("height");
    this.$el.firstElementChild.removeAttribute("width");
    this.$el.firstElementChild.querySelectorAll("g , circle , line").forEach(item=>{
        item.removeAttribute("fill")
    // item.setAttribute("fill",this.fill)
    })
    // this.$el.firstElementChild.classList.add(this.$style.svg);
  },
};
</script>
<style >
.svg {
  fill: currentColor;
  margin-top: -4px;
  vertical-align: middle;
}
</style>



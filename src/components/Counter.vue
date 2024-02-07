<template>
  <div>
    <h1>Counter</h1>
    <div>
      <label :class="text_class">{{ counter }}</label> 
    </div>    
    <div> 
       <button :disabled="disabled_btn()" @click="handler_btn()">Count up</button> 
    </div>    
  </div>
</template>

<!--
  BEGIN GENERATED PART
--->

<script>
export default {
  data() {
    return {
      counter: 0,
      text_class: 'blue',
      state: 'Blue',
    };
  },
  methods: {
    disabled_btn() {
      return !((this.state === 'Blue' && this.counter < 10) 
        || (this.state === 'Red' && this.counter < 10));
    },
    handler_btn() {
      if (this.state === 'Blue' && this.counter < 10) {
        this.counter++;
        this.state = 'Red';
        this.text_class = 'red';
      }
      else if (this.state === 'Red' && this.counter < 10) {
        this.counter++;
        this.state = 'Blue';
        this.text_class = 'blue';
      }
    },
  },
};
</script>

<!--
  END GENERATED PART
--->

<style>
.blue { color: #00f; }
.red { color: #f00; }
</style>


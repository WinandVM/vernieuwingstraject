<script setup>
import ODISNL from '../components/AppTrajectNlODIS.vue'
import ODISEN from '../components/AppTrajectEnODIS.vue'
</script>


<template>
  <div class="container px-3 mx-auto" style="max-width: none">
  <div class="row">
    <div class="col-sm-8"></div>
      <div class="col-sm-2">
        <select class="form-select"  size="1" name="count" @change="change($event)">
          <option value="0" selected>Nederlands</option>
          <option value="1">English</option>
        </select>
      </div>
    </div>
  </div>
  <div class="container px-3 mx-auto" v-show="en" style="max-width:none">
    <ODISEN />
  </div>
  <div class="container px-3 mx-auto" v-show="nl" style="max-width:none">
    <ODISNL />
</div>
</template>

<script>
export default {
  data() {
    return {
      nl: true,
      en: false
    }
  },  
  methods: {
    change(e) {
//      console.log('value', e.target.value);
//      console.log('nl', this.nl);
      if ( e.target.value == 1 ){
        {
            this.nl = false,
            this.en = true
        }
      } else {
            this.nl = true,
            this.en = false
      }
    },
  },
};
</script>
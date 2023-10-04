<template>
  <q-page class="flex flex-center">
    <div class="col-6">
      <q-btn-toggle
        v-model="op" 
        spread
        toggle-color="primary" 
        color="white"
        text-color="black"
        :options="[
          { label: '+', value: '+' },
          { label: '-', value: '-' }
        ]"
      />
      <q-input 
        filled 
        v-model="sum" 
        readonly 
      />
      <q-btn-group>
        <q-btn 
          v-for="btn in btnTab" 
          color="primary" 
          :key="btn" 
          :label=btn 
          :value=btn 
          @click="calc(btn)" 
        />
      </q-btn-group>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'IndexPage',

  setup () {
    const tab = Array.from(Array(10).keys())
    const operators = {
      '+': function(a, b) { return a + b },
      '-': function(a, b) { return a - b }
    }

    var sum = ref(0);
    var op = ref('+');

    return {
      btnTab: tab,
      opTab: operators,
      op,
      sum,
      calc (val) {
        sum.value = operators[op.value](sum.value, val)
      }
    }
  }
})
</script>

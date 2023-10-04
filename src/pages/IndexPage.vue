<template>
  <q-page class="flex flex-center">
    <div class="col-6">
      <q-input filled v-model="sum" readonly />
      <q-btn-group>
        <q-btn color="primary" label="0" :value="0" @click="addSum($event)" />
        <q-btn color="primary" label="1" :value="1" @click="addSum($event)" />
        <q-btn color="primary" label="2" :value="2" @click="addSum($event)" />
        <q-btn color="primary" label="3" :value="3" @click="addSum($event)" />
        <q-btn color="primary" label="4" :value="4" @click="addSum($event)" />
        <q-btn color="primary" label="5" :value="5" @click="addSum($event)" />
        <q-btn color="primary" label="6" :value="6" @click="addSum($event)" />
        <q-btn color="primary" label="7" :value="7" @click="addSum($event)" />
        <q-btn color="primary" label="8" :value="8" @click="addSum($event)" />
        <q-btn color="primary" label="9" :value="9" @click="addSum($event)" />
      </q-btn-group>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'IndexPage',

  setup () {
    var sum = ref(0);

    return {
      sum,
      addSum (e) {
        sum.value += parseInt( e.currentTarget.getAttribute('value') );
      }
    }
  }
})
</script>

<template>
  <div id="q-app">
    <!-- <router-view /> -->
    <h5 class="text-center">Slots</h5>
    <hr>
    <base-form ref="myForm" @on:reset="reset">
      <template #main>
        <q-input
          class="col-xs-12 col-sm-3"
          :rules="[ val => val && val.length > 0 || 'Campo requerido']"
          v-model="name" square outlined reverse-fill-mask
          label="First label"
        />
      </template>
      <template #footer>
        <q-btn label="Submit" type="submit" color="primary"/>
        <!-- <q-btn label="click" @click="clicked" type="click" color="secondary"/> -->
      </template>
    </base-form>
  </div>
</template>

<script>
import BaseForm from "./components/BaseForm.vue"

export default {
  components: { BaseForm },
  data () {
    return {
      name: null,
      age: null,

      accept: false
    }
  },
  methods: {
    clicked () {
      this.$refs.myForm.slotClick();
    },
    reset () {
      this.name = null;
    }
  },
}
</script>

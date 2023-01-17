<template>
<q-card style="width: 100%" class="q-mt-md">
    <q-card-section>
      <q-form
        @submit="onSubmit"
        @reset="onReset"
        class="q-gutter-lg"
        ref="slotForm"
      >
        <div class="row q-col-gutter-sm">
          <slot name="main"></slot>
        </div>
        <q-card-actions align="right">
          <slot name="footer"></slot>
          <q-btn label="Reset" type="reset"  color="primary" flat class="q-ml-sm" />

          <!-- <slot name="footer"></slot> -->
        </q-card-actions>
      </q-form>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  data () {
    return {
      name: null,
      age: null,

      accept: false
    }
  },
  // emits: ['on:reset'],

  methods: {
    onSubmit () {
      console.log('SAVING...');
    },

    slotClick () {
      // console.log('clicked')
    },
    onReset () {
      this.$emit('on:reset');
      // this.$refs.slotForm.reset();
    },
  },
  mounted() {
    console.log(this.$slots)
  },
}
</script>

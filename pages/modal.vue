<template>
  <section>
      <b-button
          label="Launch component modal"
          type="is-primary"
          size="is-medium"
          @click="isComponentModalActive = true" />

      <b-modal
          v-model="isComponentModalActive"
          has-modal-card
          trap-focus
          :destroy-on-hide="false"
          aria-role="dialog"
          aria-label="Example Modal"
          close-button-aria-label="Close"
          aria-modal>
          <template>

            <div  style=" height: 50vh;"><h3>hello from model</h3></div>
          </template>
      </b-modal>
  </section>
</template>

<script>


  export default {

      data() {
          return {
              isComponentModalActive: false,
          }
      }
  }
</script>

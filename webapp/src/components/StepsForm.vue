<template>
  <v-stepper v-model="e1">
    <v-stepper-header>
      <v-stepper-step
        :complete="e1 > 1"
        step="1"
      >
        Name of step 1
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step
        :complete="e1 > 2"
        step="2"
      >
        Name of step 2
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step step="3">
        Name of step 3
      </v-stepper-step>
    </v-stepper-header>

    <v-stepper-items>
      <v-stepper-content step="1"
        class="form-padding"
      >
        <v-card
          class="mb-12"
          height="100%"
        >
          <v-card-text
          >
            <FormNewAppointmentBasicInformation />
          </v-card-text>
        </v-card>

        <v-btn
          color="primary"
          @click="e1 = 2"
          min-width="100%"
        >
          Continue
        </v-btn>

      </v-stepper-content>

      <v-stepper-content step="2"
        class="form-padding"
      >
        <v-card
          class="mb-12"
          height="100%"
        >
          <v-card-text>
            <FormNewAppointmentBasicInformation />
          </v-card-text>
        </v-card>

        <v-btn
          color="primary"
          @click="e1 = 3"
        >
          Continue
        </v-btn>

      </v-stepper-content>

      <v-stepper-content step="3"
        class="form-padding"
      >
        <v-card
          class="mb-12 box-shadow-none"
          height="100%"
        >
          <v-card-text>
            <FormNewAppointmentBasicInformation />
          </v-card-text>
        </v-card>

        <v-btn
          color="primary"
          @click="e1 = 1"
          class="btn-margin"
        >
          Continue
        </v-btn>

        <v-btn text>
          Cancel
        </v-btn>
      </v-stepper-content>
    </v-stepper-items>
  </v-stepper>
</template>

<script>
import FormNewAppointmentBasicInformation from './FormNewAppointmentBasicInformation.vue'

  export default {
components: {
  FormNewAppointmentBasicInformation

},

    data () {
      return {
        e1: 1,
      }
    },
  }
</script>

<style scoped>

    .form-padding {
      padding: 1px 0px 0px 0px;
    }

    .btn-margin {
      margin-left: 5px !important;
    }

    .v-sheet.v-card{
      box-shadow: none !important;
    }

</style>
<template>

  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
    class="pr-1"
  >
  <v-container class="pr-1">
    <v-row>
      <v-col>
        <h1><strong class="roboto py-1">New Appointment</strong></h1>
        <p class="roboto py-1">Total: $250.00</p>
      </v-col>
    </v-row>
  </v-container>

  <v-container>
    <v-row>
      <v-col
        cols="12"
          md="6"
      >
        <v-text-field
        v-model="customer"
        :counter="10"
        :rules="nameRules"
        label="Select Customer"
        required
        outlined
      ></v-text-field>
      </v-col>
      <v-col
        cols="12"
          md="6"
      >
        <v-text-field
        v-model="ServiceName"
        :counter="10"
        :rules="nameRules"
        label="Select Service Name"
        required
        outlined
      ></v-text-field>
      </v-col>
    </v-row>

  <v-row>
    <v-col
      cols="12"
      md="6"

    >
        <v-text-field
        v-model="time"
        :counter="10"
        :rules="nameRules"
        label="Time"
        required
        outlined
      ></v-text-field>
    </v-col>

        <v-col
      cols="12"
      md="6"

    >
      <v-text-field
        v-model="ampm"
        :counter="10"
        :rules="nameRules"
        label="AM/PM"
        required
        outlined
      ></v-text-field>
    </v-col>

  </v-row>

  <v-row>
    <v-col
      cols="12"
      md="12"
    >
      <v-text-field
        v-model="inHouseNotes"
        :counter="10"
        :rules="nameRules"
        label="In house notes"
        required
        outlined
      ></v-text-field>
    </v-col>

  </v-row>

    <v-row>
    <v-col
      cols="12"
      md="12"
    >
      <v-text-field
        v-model="notesForTheCustomer"
        :counter="10"
        :rules="nameRules"
        label="Notes for the customer"
        required
        outlined
      ></v-text-field>
    </v-col>

  </v-row>

  </v-container>

  </v-form>
</template>


<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],
      checkbox: false,
    }),

    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },
    },
  }
</script>


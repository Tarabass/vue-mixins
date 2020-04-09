<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-form ref="form">
          <v-text-field
            v-model="model"
            :counter="max"
            :rules="rules"
            label="First name"
          ></v-text-field>
          <TextField
            v-model="model"
            label="First name 2"
          ></TextField>
        </v-form>
      </v-col>
      <v-col
        cols="12"
        md="6"
      >
        <v-slider
          v-model="max"
          label="Max characters"
        >
        </v-slider>

        <v-checkbox
          v-model="allowSpaces"
          label="Allow spaces"
        ></v-checkbox>

        <v-text-field
          v-model="match"
          label="Value must match"
        ></v-text-field>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  import TextField from '@/components/TextField.vue';
  import formRulesMixin from '@/mixins/formrules';

  export default {
    name: 'Form',
    mixins: [formRulesMixin],
    components: {
      TextField
    },

    data: () => ({
      allowSpaces: false,
      match: 'Foobar',
      max: 0,
      model: 'Foobar',
    }),

    created: function() {
      console.log(this.rules);
      console.log(this.message); 
    }
  }
</script>

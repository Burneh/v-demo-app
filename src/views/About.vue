<template>
  <v-container grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12 md8 offset-md2>
        <v-slide-y-transition mode="out-in">
          <v-layout row wrap>
            <v-flex sm6>
              <v-text-field
                v-model="model.firstName"
                label="First Name"
                prepend-icon="fas fa-user"
              />
            </v-flex>
            <v-flex sm6>
              <v-text-field
                v-model="model.lastName"
                label="Last Name"
                prepend-icon="fas fa-user"
              />
            </v-flex>
            <v-flex sm6>
              <v-text-field
                v-model="model.phone"
                label="Phone Number"
                prepend-icon="fas fa-phone"
              />
            </v-flex>
            <v-flex sm6>
              <v-select
                :items="['', 'Contract', 'Contract to Hire', 'Freelancer']"
                label="Payment Model"
                dense
                prepend-icon="fas fa-money-bill-alt"
                v-model="payModel"
              />
            </v-flex>
            <v-flex sm12>
              <v-text-field
                v-model="model.headline"
                label="Headline"
                prepend-icon="fas fa-file-signature"
                multi
              />
            </v-flex>
            <v-flex xs12><v-divider/></v-flex>
            <v-flex sm6>
              <v-radio-group v-model="country" label="Country" prepend-icon="fas fa-globe">
                <v-radio
                  v-for="n in ['United States', 'United Kingdom', 'Other']"
                  :key="n"
                  :label="`${n}`"
                  :value="n"
                ></v-radio>
              </v-radio-group>
            </v-flex>
            <v-flex sm6>
              <v-text-field
                v-model="model.jobTitle"
                label="Job Title"
                prepend-icon="fas fa-tag"
                multi
              />
            </v-flex>
            <v-btn color="primary">Create Profile</v-btn>
          </v-layout>
        </v-slide-y-transition>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      model: {
        firstName: '',
        lastName: '',
        phone: '',
        payModel: '',
        headline: '',
        jobTitle: '',
        country: ''
      }
    }
  }
}
</script>

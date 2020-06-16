<template>
    <div>
        <h1>{{ titleSpecies }} for Adoption</h1>
        <b-table striped hover :items="pets">
            <template v-slot:cell(name)="data">
                <router-link :to="`/pets/${species}/${data.index}`">
                    {{ data.value }}
                </router-link>
            </template>
        </b-table>
    </div>
</template>

<script>
export default {
  props: {
    species: String,
    pets: Array
  },
  methods: {
    capitalizeSpecies () {
      return this.species.charAt(0).toUpperCase() + this.species.slice(1)
    }
  },
  data () {
    return {
      titleSpecies: this.capitalizeSpecies()
    }
  }
}
</script>

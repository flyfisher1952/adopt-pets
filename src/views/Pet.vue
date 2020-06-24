<template>
  <div>
    <h1>Pets for Adoption</h1>
    <b-table striped hover :items="pets" />
  </div>
</template>

<script>
import _ from 'lodash'
import cats from '@/data/cats'
import dogs from '@/data/dogs'

export default {
  data () {
    return {
      cats: cats,
      dogs: dogs,
      pets: _.sortBy(_.concat(dogs, cats), p => {
        return p.name
      })
    }
  }
}
</script>

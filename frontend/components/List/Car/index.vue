<template>
  <v-card
    class="mx-auto"
    max-width="500"
  >
    <v-list two-line>
      <v-list-item-group
        v-model="selected"
        active-class="pink--text"
        multiple
      >
        <template v-for="(car, index) in cars">
          <v-list-item :key="car.id">
            <template>
              <v-list-item-content>
                <v-list-item-title v-text="car.name"></v-list-item-title>

                <v-list-item-subtitle
                  class="text--primary"
                  v-text="car.brand"
                ></v-list-item-subtitle>

                <v-list-item-subtitle v-text="car.mileage"></v-list-item-subtitle>
              </v-list-item-content>

            </template>
          </v-list-item>

          <v-divider
            v-if="index < cars.length - 1"
            :key="index"
          ></v-divider>
        </template>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>


<script>
  export default {
    props: [ 'cars' ]
  }
</script>
<template>
<div>
<table>
  <tr>
    <th>Vrsta</th>
    <th>Ime</th>
    <th>dateofBirth</th>
  </tr>
  <tr v-for="(animal, index) in listOfAnimals" :key="index">
    <td>{{ animal.vrsta }}</td>
    <td>{{ animal.ime }}</td>
    <td v-if="animal.dateofBirth">{{ animal.dateofBirth.toLocaleString() }}</td>
    <td v-else> Unkown </td>
    <td><button v-on:click="removeAnimal(index)">DeleteAnimal</button></td>
  </tr>
</table>
</div>
</template>

<script>
export default {
  name: 'AnimalList',
  data() {
    return {
      listOfAnimals: [
        { vrsta: "Majumn", ime: "Slavko", dateofBirth: new Date(2031, 1, 22) },
        { vrsta: "Konj", ime: "Djordje", dateofBirth: new Date(2020, 1, 32) },
        { vrsta: "Pauk", ime: "Mica", dateofBirth: new Date(2500, 16, 24)},
        { vrsta: "Jelen", ime: "Djoka", dateofBirth: new Date(2200, 1, 52) },
        { vrsta: "Medved", ime: "Radovan" },
        { vrsta: "Golub", ime: "Zika", dateofBirth: new Date(1999, 1, 10) },
      ],
    };
},
    methods: {
    removeAnimal(index) {
        this.listOfAnimals.splice(index, 1);

      }
    }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

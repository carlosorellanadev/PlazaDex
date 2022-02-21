<template>
  <div>
    <div class="col-md-8">
      <div class="marco-dex bg-secondary d-flex justify-content-center">
        <div
          class="pokemon-info d-flex justify-content-evenly align-items-center"
        >
          <div class="info-nro">{{nro}}</div>
          <div class="info-name">{{name}}</div>
          <div class="info-species">Rock Pokemon</div>
          <div class="info-type-a">Rock</div>
          <div class="info-type-b">Ground</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
    data(){
        return{
            pokeData: [],
            nro: null,
            name: null
        }
    },
  methods: {
    async getPokemonData() {
      await fetch("https://pokeapi.co/api/v2/pokemon/149")
        .then((response) => response.json())
        .then((data) => this.pokeData = data);

        this.name = this.pokeData.name
        this.nro = this.pokeData.order
    },
  },
  mounted(){
      this.getPokemonData()
  }
};
</script>
<style scoped lang="scss">
.marco-dex {
  border-radius: 0px 10px 10px 0px;
  border-top: 10px solid #28394a;
  border-bottom: 10px solid #28394a;
  border-right: 10px solid #28394a;
  height: 80vh;
  width: 100%;
  padding: 10px;
}

.pokemon-info {
  background-color: #28394a;
  height: 50px;
  width: 80%;
  color: #ffffff;
  padding: 5px;
  font-size: 1.5rem;
}
</style>

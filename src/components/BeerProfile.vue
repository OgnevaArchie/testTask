<template>
  <section class="section-beer">
    <div class="beer-container-desctiption">
      <div class="beer-container-item">
        <p>Brand</p>
      </div>
      <div class="beer-container-item">
        <p>Name</p>
      </div>
      <div class="beer-container-item">
        <p>Style</p>
      </div>
      <div class="beer-container-item">
        <p>Hop</p>
      </div>
      <div class="beer-container-item">
        <p>Yeast</p>
      </div>
      <div class="beer-container-item">
        <p>Malts</p>
      </div>
      <div class="beer-container-item">
        <p>Ibu</p>
      </div>
      <div class="beer-container-item">
        <p>Alcohol</p>
      </div>
      <div class="beer-container-item">
        <p>Blg</p>
      </div>
    </div>

      <div class="beer-container-information">
        <div class="beer-information-item">
          <p>{{beer?.brand}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.name}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.style}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.hop}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.yeast}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.malts}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.ibu}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.alcohol}}</p>
        </div>
        <div class="beer-information-item">
          <p>{{beer?.blg}}</p>
        </div>
      </div>
  </section>
</template>

<script>

  export default {
    name: "beer-component",
    data() {
      return {
        beer: null,
      };
    },
    async created() {
      const response = await fetch("https://random-data-api.com/api/beer/random_beer");
      const data = await response.json();
      this.beer = data;
    }
  }
</script>


<style>
  .beer-container-desctiption {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: start;
    background-color: #1b1b1b;
    height: 620px;
    min-width: 100px;
    max-width: 150px;
    margin-left: 5%;
    padding-top: 20px;
    padding-left: 40px;
  }


  .beer-container-item {
    max-width: 300px;
    min-width: 100px;
    height: 50px;
    text-align: center;
    background-color: rgb(245, 245, 245);
    margin-top: 15px;
  }

  .beer-container-information {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    background-color: #d6d4d4;
    justify-content: start;
    height: 620px;
    width: 360px;
    padding-top: 20px;
    color: white;
  }

  .beer-information-item {
    width: 300px;
    height: 50px;
    text-align: center;
    background-color: #1b1b1b;
    margin-top: 15px;
  }

  .section-beer {
    display: flex;
    flex-direction: row;
    margin-top: 60px;
    margin-right: auto;
    margin-bottom: 60px;
  }
</style>
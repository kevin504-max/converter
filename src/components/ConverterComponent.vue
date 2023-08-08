
<template>
  <div class="converter">
    <h2>{{ currencyA }} To {{ currencyB }}</h2>
    <input type="text" v-model="currencyA_value" v-bind:placeholder="currencyA"> 
    <input type="button" value="Converter" v-on:click="converter">
    <h2>{{ currencyB_value }}</h2>
  </div>
</template>

<script>
export default {
  name: 'ConverterComponent',
  props: ['currencyA', 'currencyB'],
  data() {
    return {
      currencyA_value: "",
      currencyB_value: 0,
    }
  },
  methods: {
    converter() {
      let url = `
        https://api.freecurrencyapi.com/v1/latest?apikey=fca_live_is7EbHjXrfykEJLfZxIaDvPTKaAsHH2HmhQ951gO&base_currency=${this.currencyA}&convert_currency=${this.currencyB}
      `;

      fetch(url).then((response) => {
        if (!response.ok) throw new Error(`Request failed with status: ${response.status}`);

        return response.json();
      }).then((json) => {
        let cotation = json.data[this.currencyB];

        this.currencyB_value = (parseFloat(this.currencyA_value) * cotation).toFixed(2);
      });
    }
  }
}
</script>

<style scoped>
.converter {
  padding: 20px;
  max-width: 300px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  background-color: #f1f1f1;
  border-radius: 7px;

}

.converter input {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.converter input[type=button] {
  background-color: #4CAF50;
  color: white;
  cursor: pointer;
}

.converter input[type=button]:hover {
  background-color: #45a049;
}

.converter h2 {
  text-align: center;
}

.converter h2:first-child {
  margin-top: 0;
}

.converter h2:last-child {
  margin-bottom: 0;
}

.converter input[type=text]:focus {
  outline: none;
}

.converter input[type=text]:focus::placeholder {
  color: transparent;
}

.converter input[type=text]:focus + input[type=button] {
  background-color: #45a049;
}
</style>
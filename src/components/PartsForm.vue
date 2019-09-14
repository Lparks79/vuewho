<template>
  <div class="hello">
    <div class="form">
      <label class="partOrderTitle">
        <h1> Order Form </h1>
      </label>
      <div class="formLine">
        <label class="label">Year</label>
        <select class="dropdown" name="years" v-model="partOrder.selectedYear">
          <option>1979</option>
          <option>1980</option>
        </select>
      </div>
      <div class="formLine" v-if="partOrder.selectedYear">
        <label class="label">Make</label>
        <select class="dropdown" name="make" v-model="partOrder.selectedMake">
          <option>Ford</option>
          <option>Chevy</option>
        </select>
      </div>
      <div class="formLine" v-if="partOrder.selectedMake === 'Ford'">
        <label class="label">Model</label>
        <input class="input" id="model" v-model="partOrder.fordModel"/>
      </div>
      <div class="formLine" v-if="partOrder.selectedMake === 'Chevy'">
        <label class="label">Model</label>
        <input class="input" id="model" v-model="partOrder.chevyModel"/>
      </div>
      <div class="formLine">
        <label class="label partDescLabel">Part Description</label>
        <textarea class="partDescTextarea" id="partDesc" v-model="partOrder.partDesc" />
      </div>
      <div class="formSubmit" @click="submitForm">Submit</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PartsForm',
  props: {
    msg: String
  },
  data() {
    return {
      partOrder: {
        years: [ '1979', '1980', '1981'],
        selectedYear: '',
        makes: [ 'Ford', 'Chevy' ],
        selectedMake: '',
        fordModels: [ 'Mustang', 'F150' ],
        chevyModels: [ 'Camaro', 'Corvette' ],
        selectedModel: '',
        partDesc: '',

      }
    }
  },
  methods: {
    submitForm() {
      console.log("Data: " + JSON.stringify(this.partOrder));
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.partOrderTitle {
  display: block;
}

.formLine {
  display: block;
  width: 300px;
  text-align: right;
  padding: 5px;
  margin-left: auto;
  margin-right: auto;
}

.formSubmit {
  border-radius: 5px;
  color:white;
  background-color: blue;
  width: 120px;
  padding: 10px;
  margin: 10px auto 10px auto;
  box-shadow: 5px 3px 5px lightblue;
}

.label {
  padding: 5px;
  width: 100px;
}

.partDescLabel {
  vertical-align: top;
  top: 10px;
  position: relative;
}

.input {
  padding: 5px;
  width: 150px;
}

.partDescTextarea {
  min-width: 158px;
  max-width: 158px;
  min-height: 25px;
  max-height: 200px;
}

.dropdown {
  width: 164px;
  padding: 5px;
}
</style>

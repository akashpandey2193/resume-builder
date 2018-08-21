<template>
  <div class="input-container">
    <label id="text" for="text-field">Akas</label>
    <input type="text" @click="setLabel" name="text-field" :value="value">
  </div>
</template>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      default: () => 'Enter Here'
    },
    label: {
      type: String,
      default: () => ''
    }
  },
  data() {
    return {
      value: ''
    }
  },
  methods: {
    setLabel(val) {
      console.log(val);
      document.getElementById('text').classList.add('labels');
    },
  },
  watch: {
    value(val) {
      handler: setLabel(val)
    }
  }
}
</script>

<style lang="scss" scoped>
.input-container {
  position: relative;
  border: 1px solid #000000;
  width: 500px;
  cursor: pointer;
  input {
    width: 100%;
    height: 30px;
    padding: 0;
    border-radius: 4px;
    outline: none;
    font-size: 14px;
    padding: 4px;
    border: none;
    box-sizing: border-box;
  }
}
.input-container:hover, .input-container:active {
  border-color: #d32213;
}
.labels {
  top: 5px;
  font-size: 10px;
}
label {
  top: 50%;
  position: absolute;
  transform: translateY(-50%);
}

input:focus {
  border-color: blue;
}

</style>

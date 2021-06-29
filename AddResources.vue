<template>
  <div>
    id: <input type="text" ref="input0" /> <br /><br />
    name: <input type="text" ref="input1" /><br /><br />
    description: <input type="textarea" ref="value2" /><br /><br />
    link: <input type="url" ref="value3" />
    <button @click="storeValueFunction">Add</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value0: '',
      value1: '',
      value2: '',
      value3: '',
    };
  },
  methods: {
    storeValueFunction() {
      this.value0 = this.$refs.value0.value;
      this.value1 = this.$$refs.value1.value;
      this.value2 = this.$refs.value2.value;
      this.value3 = this.$refs.value3.value;
      this.$emit(
        'inputs-values',
        this.value0,
        this.value1,
        this.value2,
        this.value3
      );
    },
  },
};
</script>
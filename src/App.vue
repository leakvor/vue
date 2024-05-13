<template>
<h1>Form Test</h1>
  <Form />
  <h1>Table</h1>
  <TableVue />
  <h1>Card Vue</h1>
  <CardVue />
</template>

<script>
import CardVue from './components/Card.vue';
import Form from './components/Form.vue';
import TableVue from './components/Table.vue';



export default {
  name: "App",
  components: {
    Form,
    TableVue,
    CardVue
  },
  data() {
    return {
      
    };
  },
  
};
</script>

<style></style>

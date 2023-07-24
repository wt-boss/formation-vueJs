<template>
  <app-form>
  
      <template class="help" v-slot:help></template>

      <template class="fields" v-slot:fields>
        <label> name <input type="text" /></label>
        <label> surname <input type="text" /></label>
      </template>

      <template class="button" button>
        <button type="button">Envoyer</button>
    </template>
   
  </app-form>
  <app-form></app-form>
</template>

<script>
import AppForm from "./components/Form.vue";
export default {
  name: "App",
  components: {
    AppForm,
  },
};
</script>

<style lang="scss" scoped></style>

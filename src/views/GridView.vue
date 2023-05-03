<template>
    <ag-grid-vue
      style="width: 500px; height: 200px"
      class="ag-theme-alpine"
      :columnDefs="columnDefs"
      :rowData="rowData"
    >
    </ag-grid-vue>
</template>
  
<script>
import "ag-grid-community/styles/ag-grid.css";
import "ag-grid-community/styles/ag-theme-alpine.css";
import { AgGridVue } from "ag-grid-vue3";
import csv from '../data/scope3tools.csv'

export default {
  name: "App",
  components: {
    AgGridVue,
  },
  setup() {
    console.log(csv);
    return {
      columnDefs: [
      //  { headerName: "Make", field: "make" },
      //  { headerName: "Model", field: "model" },
      //  { headerName: "Price", field: "price" },
        { headerName: "Haus", field: "Name"},
        { headerName: "Kategorie", field: "Beschreibung"},
        { headerName: "Komplexität", field: "Komplexität"}
      ],
      rowData: csv,
      //rowData: [
      //  { make: "Toyota", model: "Celica", price: 35000 },
      //  { make: "Ford", model: "Mondeo", price: 32000 },
      //  { make: "Porsche", model: "Boxster", price: 72000 },
      //],
    };
  },
};
</script>
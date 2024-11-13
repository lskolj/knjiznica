<template>
  <q-page padding>
    <q-card>
      <q-card-section>
        <div class="text-h4">Popis svih knjiga</div>
        <div class="text-subtitle2">Ovdje možete vidjeti popis svih knjiga u bazi podataka.</div>
      </q-card-section>

      <q-card-section>
        <q-table
        :rows="books"
        :columns="columns"
        row-key="id"/>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      books: [
        { id: 1, title: 'Dead Souls', autor: 'Nikolai Gogol', year: 1842 },
        { id: 2, title: 'Anna Karenina', autor: 'Leo Tolstoy', year: 1877 },
        { id: 3, title: 'The Castle', autor: 'Franz Kafka', year: 1926 }
      ],
      columns: [
        { name: 'title', label: ' Naslov ', align: 'left', field: row => row.title },
        { name: 'autor', label: ' Autor ', align: 'left', field: row => row.autor },
        { name: 'year', label: ' Godina ', align: 'center', field: row => row.year }
      ]
    }
  }
}
</script>

<style scoped>
.q-table {
  max-height: 400px;
  overflow: auto;
}
</style>

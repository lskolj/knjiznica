<template>
  <q-page padding>
    <q-card>
      <q-card-section>
        <div class="text-h4">Pretraživanje knjiga</div>
        <div class="text-subtitle2">Pretražite knjige prema autoru ili naslovu.</div>
      </q-card-section>

      <q-card-section>
        <q-input v-model="searchQuery" label="Pretraži" />
        <q-checkbox v-model="searchbyAuthor" label="Pretraži po autoru" />
        <q-checkbox v-model="searchbyTitle" label="Pretraži po naslovu" />
        <q-btn @click="searchBooks" label="Traži" color="primary" />
      </q-card-section>

      <q-card-section>
        <q-table
        :rows="filteredBooks"
        :columns="columns"
        row-key="id"
        />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      searchQuery: '',
      searchbyAuthor: false,
      searchbyTitle: false,
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
  },
  computed: {
    filteredBooks () {
      return this.books.filter(book => {
        const query = this.searchQuery.toLowerCase();
        return (
        (this.searchByAuthor && book.author.toLowerCase().includes(query)) ||
          (this.searchByTitle && book.title.toLowerCase().includes(query))
        );
      });
    },
  },
  methods: {
    searchBooks() {
      console.log('Pretraga za:', this.searchQuery);
    },
  },
};

</script>

<style scoped>
.q-table {
  max-height: 400px;
  overflow: auto;
}
</style>

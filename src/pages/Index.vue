<template>
  <q-page class="flex justify-center q-pa-md">
    <q-table
      :grid="grid"
      class="main-table"
      title="Treats"
      :rows="rows"
      :columns="columns"
      row-key="name"
    />
  </q-page>
</template>

<script>
const columns = [
  {
    name: 'name',
    required: true,
    label: 'شماره سند',
    align: 'left',
    field: row => row.name,
    sortable: true
  },
  { name: 'calories', align: 'center', label: 'عنوان', field: 'calories', sortable: true },
  { name: 'iron', label: '', field: 'iron' }
]

const rows = [
  {
    name: 'Frozen Yogurt',
    calories: 159,
    iron: '1%'
  }
]

export default {
  setup () {
    return {
      columns,
      rows
    }
  },
  computed: {
    grid() {
      return /iPhone|iPad|iPod|Android/i.test(navigator.userAgent)
    }
  }
}
</script>

<style>
.main-table {
  width: 70%;
  height: 100%;
}
@media(max-width: 1300px) {
  .main-table {
    width: 85%;
  }
}
@media(max-width: 800px) {
  .main-table {
    width: 100%;
  }
}
</style>

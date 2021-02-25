<template>
  <div id="app">
    <div class="container-fluid">
      <div class="row">
        <Sidebar />
        <div class="col-6 offset-3">
          <TransactionsTable />
        </div>
        <div class="col-2">
          <TransactionsPanel />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue'
import TransactionsTable from './components/TransactionsTable.vue'
import TransactionsPanel from './components/TransactionsPanel.vue'

export default {
  name: 'App',
  components: {
    Sidebar,
    TransactionsTable,
    TransactionsPanel
  }
}
</script>

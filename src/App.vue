<template>
  <div id="app">
    <div class="container-fluid">
      <Navbar />
      <div class="row">
        <div class="col-2 bg-dark">
          <Sidebar />
        </div>
        <div class="col-8 p-5">
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
import Navbar from './components/Navbar.vue'
import TransactionsTable from './components/TransactionsTable.vue'
import TransactionsPanel from './components/TransactionsPanel.vue'

export default {
  name: 'App',
  components: {
    Sidebar,
    Navbar,
    TransactionsTable,
    TransactionsPanel
  }
}
</script>

<template>
  <div class="col-2 bg-dark position-fixed">
    <div class="nav flex-column flex-nowrap vh-100 overflow-auto text-white p-2">
      <b-link class="navbar-brand" href="">Finpal</b-link>
      <b-link href="#" class="nav-link">Transactions</b-link>
      <b-link href="#" class="nav-link">Transfers</b-link>
      <b-link href="#" class="nav-link">Invoices</b-link>
      <b-link href="#" class="nav-link">Manage cards</b-link>
      <b-link href="#" class="nav-link">Manage accounts</b-link>
      <b-link href="#" class="nav-link">Team</b-link>
      <b-link href="#" class="nav-link">Integration</b-link>
      <b-link href="#" class="nav-link">Settings</b-link>
      <b-button variant="outline-primary">Upgrade account</b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sidebar'
}
</script>

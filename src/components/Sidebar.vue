<template>
  <div class="nav flex-column flex-nowrap vh-100 overflow-auto text-white p-5">
    <b-link href="#" class="nav-link">Transactions (3)</b-link>
    <b-link href="#" class="nav-link">Transfers (2)</b-link>
    <hr/>
    <b-link href="#" class="nav-link">Invoices (1)  </b-link>
    <b-link href="#" class="nav-link">Manage cards</b-link>
    <hr/>
    <b-link href="#" class="nav-link">Manage accounts</b-link>
    <b-link href="#" class="nav-link">Team</b-link>
    <hr/>
    <b-link href="#" class="nav-link">Integration</b-link>
    <b-link href="#" class="nav-link">Settings</b-link>

    <b-button id="upgrade-account-btn" variant="outline-primary">
      Upgrade account
    </b-button>
  </div>
</template>

<script>
export default {
  name: 'Sidebar'
}
</script>

<style lang="scss">
  .nav-link {
    color: #8A919F;
  }

  #upgrade-account-btn {
    margin-top: 40px;
    color: #8CC3CF;
    border-color: #8CC3CF;
    text-transform: uppercase;
    font-weight: bold;
    font-size: 15px;

    &:hover {
      background-color: #8CC3CF;
      color: #363d45;
    }
  }

  hr {
    border-top: 1px solid red;
  }
</style>
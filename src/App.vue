<template>
  <div id="app">
    <div class="container-fluid">
      <div class="row">
        <Sidebar />
        <div class="col-9 offset-3">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue'

export default {
  name: 'App',
  components: {
    Sidebar
  }
}
</script>

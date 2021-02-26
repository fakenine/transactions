<template>
  <div id="top-nav" class="row">
    <div class="col-2 align-items-center">
      <div id="brand-container" class="pl-5 d-flex align-items-center">
        <b-link class="navbar-brand" href="">Finpal</b-link>
      </div>
    </div>
    <div class="col-8 p-0">
      <div id="orange-nav">
      </div>
    </div>
    <div class="col-2 p-0">
      <div id="gray-nav">
      </div>
    </div>
  </div>
</template>

<style lang="scss">
  #top-nav, #orange-nav, #gray-nav {
    min-height: 80px;
  }

  #top-nav {
    background-color: #363d45;

    #brand-container {
      height: 100%;

      .navbar-brand {
        text-transform: uppercase;
        color: #ffffff;
        font-weight: bold;
        font-size: 25px;
      }
    }

    #orange-nav { background-color: orange; }
    #gray-nav { background-color: #f6f6f6; }
  }
</style>

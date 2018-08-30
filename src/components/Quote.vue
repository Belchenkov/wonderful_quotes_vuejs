<template>
  <div class="col-sm-6 col-md-4 col-lg-3 pt-5">
    <div class="card">
      <div class="card-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Marck+Script&subset=cyrillic');
  .card-body {
    font-family: 'Marck Script', cursive;
    font-size: 27px;
    color: #6e6e6e;
  }

  .quote {
    cursor: pointer;
  }

  .quote:hover {
    background: #ffe2e2;
  }
</style>

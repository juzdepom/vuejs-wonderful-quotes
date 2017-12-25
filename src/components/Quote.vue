<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-body">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style scoped>
.panel-body {
  font-family: 'Arizonia', cursive;
  font-size: 24px;
  color: #6e6e6e;
}
.panel-body:hover {
  background-color: #ffe2e2
}
.quote {
  cursor: pointer
}

</style>

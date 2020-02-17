<template>
  <div class="panel panel-default card div_hover">
    <div class="panel-body">{{ quote }}</div>
  </div>
</template>
<script>
export default {
  props: ["quote"]
};
</script>
<style scoped>
.card {
  width: 350px;
  display: inline-block;
  margin: 5px;
  font-family: Arizonia;
  font-size: 30px;
  font-weight: 500;
  overflow-wrap: break-word;
}
.div_hover {
  background-color: #ffffff;
}

.div_hover:hover {
  background-color: #f2dede;
}
</style>
<template>
    <div>
        <button class="btn"><slot></slot></button>
    </div>
</template>

<script>
    export default {
        name:'my-button',
    }
</script>

<style scoped>
.btn {
  margin-top: 15px;
  padding: 10px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
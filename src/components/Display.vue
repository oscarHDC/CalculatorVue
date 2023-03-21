<template>
    <div class="calculator--display">
      <span class="calculator--display__text">  {{input}}</span>
    </div>
</template>

<script>
export default {
    name: "DisplayItem",
    props: ['input'],
}
</script>

<style >

.calculator--display{
    grid-column: 1 / -1;
    width: 100%;
    height: 20px;
    padding: 15px;
    border: 1px solid black;
    text-align: center;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .calculator--display__text{
    vertical-align: middle;
  }

</style>
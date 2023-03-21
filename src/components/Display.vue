<template>
    <div class="calculator--display">
       {{input}}
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
    padding: 15px;
    border: 1px solid black;
    text-align: center;
    margin: 0 auto;
  }

</style>
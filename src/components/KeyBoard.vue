<template>
    <div class="calculator--keyboard">
      <input type="button" value="9" @click="handleClick" >
      <input type="button" value="8" @click="handleClick" >
      <input type="button" value="7"  @click="handleClick" >
      <input type="button" value="x"  @click="handleClick"> 
      <input type="button" value="6"  @click="handleClick"> 
      <input type="button" value="5"  @click="handleClick">
      <input type="button" value="4"  @click="handleClick">
      <input type="button" value="-"  @click="handleClick">
      <input type="button" value="3"  @click="handleClick">
      <input type="button" value="2"  @click="handleClick">
      <input type="button" value="1"  @click="handleClick">
      <input type="button" value="+"  @click="handleClick">
      <input type="button" value="/"  @click="handleClick"> 
      <input type="button" value="CE" @click="handleClick"> 
      <input class="equal" type="button" value="=" @click="handleClick"> 
   </div>
</template>

<script >
    export default{
        name: "KeyboardItem",

        data(){
            return {
                digit: ""
            }
        },
        methods: {
            handleClick(){
                this.$emit("keyClicked", event.target.value)
            }
        },


    }

</script>

<style>

    .calculator--keyboard{
        display: grid;
        grid-template-columns: repeat(4,1fr);
    }

  .calculator--keyboard input{
    background-color: #04AA6D;
    border: none;
    color: white;
    padding: 16px;
    text-decoration: none;
    cursor: pointer;
  }

  .calculator--keyboard input:hover{
    background-color: #017d50;
  }

  .equal{
    grid-column: span 2;
  }

</style>
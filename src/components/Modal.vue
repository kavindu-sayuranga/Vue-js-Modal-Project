<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{sale: theme==='sale'}">
      <h1>{{header}}</h1>
      <p>{{text}}</p>
    </div>
  </div>
</template>

<script>
  export default{
    props: ['header','text','theme'],
    methods: {
      closeModal(){
        this.$emit('close')
      }
    }
  }
</script>

<style scoped>
.modal{
  width: 400px;
  padding: 20px;
  margin: 200px auto;
  background-color: white;
  border-radius: 10px;
}

.backdrop{
  top: 0;
  position: fixed;
  background: rgb(133, 131, 131);
  width: 100%;
  height: 100%;
}
h1{
  color: aqua;
  border: none;
  padding: 0;
}
.modal.sale{
  background: red;
  color: white;
}

.modal.sale h1{
  color: white;
}
</style>
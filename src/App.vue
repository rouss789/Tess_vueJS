<template>
  <h1>votaciones de productos</h1>
  <div id="app">
    <div class="contenedor">
      <div v-for="(producto, index)" :key="index" class="tarjeta_producto" :style="{backgroundColor: producto.color}">
        <h2>{{ producto.nombre }}</h2>
        <p>Puntos:{{ producto.votos }}</p>
          <button @click="votar(idex)">Votar</button>
        <p></p>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name: 'App',
  data(){
    return{ 
      productos:[
        {nombre:'Producto Azul', color:'blue', votos:0},
        {nombre:'Producto Rojo', color:'red', votos:0},
        {nombre:'Producto Morado',color:'purple', votos:0}
      ]
    };
  },
  methods:{
    votar(idex){
      this.productos[index].votos +=1;
    }
  }
};
</script>

<style>

</style>
<template>
  <h1>votaciones de productos</h1>
  <div id="app">
    <div class="contenedor">
      <div v-for="(producto, index) in productos" :key="index" class="tarjeta_producto">
        <p class="puntos" :style="{backgroundColor: producto.color}">{{ producto.votos }} </p>
        <div>
        <h2 class="titulo_votar">{{ producto.nombre }}</h2>
        <p class="texto_votar">Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt reiciendis dolor quis repellat! A blanditiis minus iusto voluptas officiis.
        </p>
        </div>
        <button class="boton_votar" @click="votar(index)">Votar</button>
      
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
        {nombre:'Producto 1',color:'#985CD8', votos:0},
        {nombre:'Producto 2', color:'#4BA6F7', votos:0},
        {nombre:'Producto 3', color:'#E05775', votos:0},
      ]
    };
  },
  methods:{
    votar(index){
      this.productos[index].votos +=1;
    }
  }
};
</script>

<style scoped>
#app {
  text-align: center;
  margin-top: 20px
}
.contenedor{
  display: flex;
  flex-wrap: wrap;
  gap:10px;
  padding: 10px;
}
.tarjeta_producto{
  display: flex;
  align-items: center;
  justify-content:space-between;
  padding: 10px;
  color:white;
  border-radius: 5px;
  text-align: center;
}
.puntos{
 display: flex;
 justify-content:center;
 align-items:center;
 color:white;
 padding: 10px;
 border-radius: 5px;
 width:80px;
 height:80px;
}
.titulo_votar{
  color: black;
  font-size: 14px;
}
.texto_votar{
  color:black;
  font-size:8px;
  width:150px;
}

@media (max-width:768px){
  .contenedor{
    flex-direction: column;
  }
  .tarjeta-producto{
    width: 100%;
  }
  .tarjeta-producto:nth_of_fype(1){
    width: 50%;
  }
}
</style>
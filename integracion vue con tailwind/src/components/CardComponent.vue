
<script setup>
const borrarTarjeta = (index) => {
    console.log("borrar Tarjeta" , index)
    emit('borrarTarjeta', index)
}

const emit = defineEmits(["borrar Tarjeta"])

const props = defineProps(
  {
    name:{
      type: String,
      default: "no name"
    },
    mail:{
      type: String,
      default: "no mail"
    },
    index: {
        type: Number
    }
  }
)

const modificarTarjeta = (index) => {
    console.log("Modificar Tarjeta" , index) 
    emit ('modificarTarjeta' , index)
       
}

</script>

<template>
   <div class="w-48 rounded shadow overflow-hidden">
   <div class="inline-block align-top">
<img src="https://picsum.photos/200" alt="">
   </div>

   <div class="inline-block pl-2">
        <h2 class="text-sm font-semibold">{{ props.name }}</h2>
        <p class="text-xs">{{ props.mail }}</p>
   </div>
   <div class="flex justify-center">
   <span class="inline-block ml-4 bg-red-400 text-white rounded leading-0 py-0 px-2 hover:cursor-pointer hover:bg-red-600" @click="borrarTarjeta(props.index)">
       x
   </span>

   <span class="inline-block ml-4 bg-yellow-400 text-white rounded leading-0 py-0 px-2 hover:cursor-pointer hover:bg-red-600" @click="modificarTarjeta(props.index)">
    📝
  </span>
  </div>
   </div> 
</template>
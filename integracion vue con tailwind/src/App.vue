<script setup>
import CardComponent from '@/components/CardComponent.vue'
import { ref } from 'vue';

const borrarTarjeta = (index) => {
  console.log('kill to', index)
  users.value.splice(index, 1)
  console.log(users)
}

let name, mail

const addUser = () => {
const newUser = {
  name: name,
  mail: mail,
}

users.value.unshift(newUser)
}

const users = ref([
  {
    name: "Juana de arco",
    mail: "juana@mail.com"
  },

  {
    name: "Fulano de tal xd",
    mail: "fulano@mail.com"
  }
])

</script>

  <template>
  <h1 class="text-2xl">
    HOLA MUNDO
    <br>
    <input type="text" v-model="name" placeholder="escriba su Nombre" class="border rounded">
    <br>
    <input type="text" v-model="mail" placeholder="escriba su correo" class="border rounded">
    <br>
    <button class="bg-green-200 px-2 py-1 rounded mt-2 mb-2" @click="addUser">
Añadir
    </button>
    <br>
      <div class="space-y-2">
        <CardComponent v-for="(user, index) in users" :key="index" :name="user.name" :mail="user.mail" :index="index" @borrarTarjeta="borrarTarjeta"/>
      </div>
    
  </h1>

</template>

<style scoped>

</style>

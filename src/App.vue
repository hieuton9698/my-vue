<script setup>
import { computed, ref } from 'vue';
const firstName = ref('nguyen')
const lastName = ref('hieu')
const fullName = computed({
  get(){
    return firstName.value +' '+ lastName.value
  },
  set(newvalue){
    [firstName.value, lastName.value] = newvalue.split(',')
  }
})
const changeFullname = () => {
  fullName.value = "nguyen,B"
}
</script>
<template>
 <div>
  <p id= "count">fullname: {{ fullName }}</p>
  <p id= "count">first name: {{ firstName }}</p>
  <p id= "count">last name: {{ lastName }}</p>
  <button @click="changeFullname">change fullname</button>
 </div>
</template>


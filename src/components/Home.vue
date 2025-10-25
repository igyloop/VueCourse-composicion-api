<template>
  <div>
    Nombre completo: {{ fullname }}
  </div>
  <div>
    {{ username }}
  </div>
  <button ref="btn">
    Click!
  </button>
</template>

<script setup>
import { defineProps, defineExpose, ref, toRefs, computed, inject, watch } from "vue";

const props = defineProps({
  firstName: String,
  lastName: String,
});

const { firstName, lastName } = toRefs(props);

const fullname = computed(() => {
  return `${firstName.value} ${lastName.value}`;
});

const username = inject("username");

defineExpose({
  fullname,
})

const btn = ref(null);

console.log(btn.value);

watch(btn, (valor) => {
  console.log(valor);
});
</script>

<template>
  <div>
    Nombre completo: {{ fullname }}
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const firstname = ref("Eduardo");
    const lastname = ref("Gallegos");

    const fullname = computed(() => {
      return `${firstname.value} ${lastname.value}`;
    });

    return {
      fullname,
    };
  },
}
</script>

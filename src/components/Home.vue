<template>
  <div>
    Nombre completo: {{ fullname }}
  </div>
</template>

<script>
import { toRefs, computed } from "vue";

export default {
  props: {
    firstName: String,
    lastName: String,
  },

  setup(props) {
    const { firstName, lastName } = toRefs(props);

    const fullname = computed(() => {
      return `${firstName.value} ${lastName.value}`;
    });

    return {
      fullname,
    };
  },
}
</script>

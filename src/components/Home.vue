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

<script>
import { ref, toRefs, computed, inject, watch } from "vue";

export default {
  props: {
    firstName: String,
    lastName: String,
  },

  setup(props, { expose }) {
    const { firstName, lastName } = toRefs(props);

    const fullname = computed(() => {
      return `${firstName.value} ${lastName.value}`;
    });

    const username = inject("username");

    expose({
      fullname,
    })

    const btn = ref(null);

    console.log(btn.value);

    watch(btn, (valor) => {
      console.log(valor);
    });

    return {
      fullname,
      username,
      btn,
    };
  },
}
</script>

<template>
  <AppLayout title="Contacto Editar">
    <template #header>
      
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Editar Contacto
    </h2>
    </template>
    <pre>
      {{contact}}
    </pre>
  </AppLayout>
</template>

<script>
  import AppLayout from '@/Layouts/AppLayout.vue';

  export default {
    components:{
      AppLayout
    },
    props:{
      contact: {
        type: Object,
        required: true
      },
    }
  }
</script>

<style>

</style>
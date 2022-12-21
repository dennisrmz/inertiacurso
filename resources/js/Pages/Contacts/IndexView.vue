<template>
  <AppLayout title="Contactos">
    <template #header>

      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Contactos
      </h2>
    </template>

    <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col">
        <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
          <div class="py-4 inline-block min-w-full sm:px-6 lg:px-8">
            <div class="overflow-hidden">
              <table class="min-w-full text-center">
                <thead class="border-b bg-gray-50">
                  <tr>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4">
                      Name
                    </th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4">
                      Organization
                    </th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4">
                      City
                    </th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4">
                      Phone
                    </th>
                    <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4">
                      Actions
                    </th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(contact, index) in contacts"  :key="index" class="bg-white border-b">
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ contact.first_name + ' ' + contact.last_name }}</td>
                    <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-wrap">
                     {{ contact.organization.name }}
                    </td>
                    <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-wrap">
                      {{ contact.city }}
                    </td>
                    <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-wrap">
                      {{ contact.phone }}
                    </td>
                    <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-wrap">
                      <i class="fas fa-chevron-right"></i>
                    </td>
                  </tr>
                 
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>

  </AppLayout>

</template>

<script>
import AppLayout from '@/Layouts/AppLayout.vue';

export default {
  components: {
    AppLayout
  },
  props: {
    contacts: {
      type: Array,
      required: true
    },
  }
}
</script>

<style>

</style>
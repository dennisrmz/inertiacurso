<template>
    <div class="flex items-center justify-between border-t border-gray-200 bg-white px-4 py-3 sm:px-6">
        <div class="flex flex-1 justify-between sm:hidden">
            <a href="#"
                class="relative inline-flex items-center rounded-md border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700 hover:bg-gray-50">Previous</a>
            <a href="#"
                class="relative ml-3 inline-flex items-center rounded-md border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700 hover:bg-gray-50">Next</a>
        </div>
        <div class="hidden sm:flex sm:flex-1 sm:items-center sm:justify-between">
            <div>
                <p class="text-sm text-gray-700">
                    Mostrando
                    <span class="font-medium">{{ pagination.from }}</span>
                    hasta
                    <span class="font-medium">{{ pagination.to }}</span>
                    de
                    <span class="font-medium">{{ pagination.total }}</span>
                    resultados
                </p>
            </div>
            <div>
                <nav class="isolate inline-flex -space-x-px rounded-md shadow-sm" aria-label="Pagination">
                    <template v-for="(link, index) in pagination.links" :key="index">

                        <div v-html="link.label" v-if="link.url === null" class="relative inline-flex items-center px-4 py-2 
                                                text-sm font-semibold text-gray-900 ring-1 ring-inset 
                                              ring-gray-300 hover:bg-gray-50 focus:z-20 focus:outline-offset-0">
                        </div>
                        <Link v-else v-html="link.label" :href="link.url"
                            :class="link.active ? 'z-10 bg-indigo-600 text-white focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600' : 'text-gray-900 ring-1 ring-inset ring-gray-300 hover:bg-gray-50 focus:outline-offset-0'"
                            class="relative inline-flex items-center px-4 py-2 text-sm 
                                                    font-semibold  ring-1 ring-inset ">
                        </Link>
                    </template>

                </nav>
            </div>
        </div>
    </div>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";

export default {
    components: {
        Link
    },
    props: {
        pagination: Object,
    }
}

</script>
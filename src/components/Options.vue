<template>
    <div>
        <div class="relative z-10" aria-labelledby="modal-title" role="dialog" aria-modal="true" v-bind:class="{hidden: isHidden}">
            <div class="fixed inset-0 bg-gray-400 bg-opacity-10 transition-opacity"></div>
            <div class="fixed inset-0 z-10 overflow-y-auto">
                <div class="flex min-h-full justify-center p-4 items-center">
                    <div class="relative transform overflow-hidden rounded-lg bg-img shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-lg">
                        <div class="px-4 py-3 pt-16 pl-10 pr-10 grid grid-cols-4 gap-4">
                            <div class="text-3xl" v-if="idiom == 'English'" >
                                Options
                            </div>
                            <div class="text-3xl" v-else >
                                Opciones
                            </div>
                            <div></div>
                            <div></div>
                            <div class="relative inline-flex">
                                <select id="small" v-model="idiom" @change="options.idiom = idiom"  class="block p-2 mb-6 w-full text-sm rounded-full text-gray-900 bg-gray-50 border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                    <option>Español</option>
                                    <option>English</option>
                                </select>
                            </div>
                        </div>
                        <div class="px-4 pt-5 pb-4 sm:p-6 sm:pb-4"> <!-- Contenido -->
                            <div class="sm:flex sm:items-start">
                                <div class="mx-auto flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full bg-red-100 sm:mx-0 sm:h-10 sm:w-10">
                                <!-- Heroicon name: outline/exclamation-triangle -->
                                <svg class="h-6 w-6 text-red-600" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M12 10.5v3.75m-9.303 3.376C1.83 19.126 2.914 21 4.645 21h14.71c1.73 0 2.813-1.874 1.948-3.374L13.949 4.88c-.866-1.501-3.032-1.501-3.898 0L2.697 17.626zM12 17.25h.007v.008H12v-.008z" />
                                </svg>
                                </div>
                                <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                                <h3 class="text-lg font-medium leading-6 text-gray-900" id="modal-title">Deactivate account</h3>
                                <div class="mt-2">
                                    <p class="text-sm text-gray-500">Are you sure you want to deactivate your account? All of your data will be permanently removed. This action cannot be undone.</p>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="px-4 py-3 pb-10 sm:flex sm:flex-row-reverse sm:px-6"> <!-- Botones -->
                            <!-- <button type="button" class="inline-flex w-full justify-center rounded-md border border-transparent bg-red-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2 sm:ml-3 sm:w-auto sm:text-sm">Deactivate</button> -->
                            <button v-if="idiom == 'English'" type="button" class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-300 bg-blue-400 px-4 py-2 text-base font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm" v-on:click="accept" >Accept</button>
                            <button v-else type="button" class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-300 bg-blue-400 px-4 py-2 text-base font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm" v-on:click="accept" >Aceptar</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isHidden: false,
            idiom: 'Español',
            options: {
                idiom: 'Español'
            }
        }
    },
    methods: {
        accept() {
            this.isHidden = !this.isHidden

            console.log({opciones: this.options});
        },
        test() {
            console.log(this.idiom);
        }

    }
}
</script>

<style lang="css">
    .hidden {
        visibility: hidden;
        opacity: 0;
        transition: visibility 0s, opacity 0.5s linear;
    }
    .bg-img {
        background-image: url(../assets/option_bg.png);
        background-size: 100% 100%;
    }
</style>
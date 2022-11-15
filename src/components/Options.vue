<template>
    <div>
        <div class="relative z-10" aria-labelledby="modal-title" role="dialog" aria-modal="true" v-bind:class="{hidden: isHidden}">
            <div class="fixed inset-0 bg-gray-400 bg-opacity-10 transition-opacity"></div>
            <div class="fixed inset-0 z-10 overflow-y-auto">
                <div class="flex min-h-full justify-center p-4 items-center">
                    <div class="relative transform overflow-hidden rounded-lg bg-img shadow-xl transition-all pr-20 pb-5 pt-5 pl-10">
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
                        <div class="px-4 py-3 pt-1 pl-10 pr-10"> <!-- Contenido -->
                            <h3 v-if="idiom == 'Español'" class="text-2xl pb-4">Generaciones</h3>
                            <h3 v-else class="text-2xl pb-4">Generations</h3>
                            <ul class="items-center w-full text-sm font-medium text-gray-900 bg-white rounded-lg border border-gray-200 sm:flex dark:bg-gray-700 dark:border-gray-600 dark:text-white">
                                <li class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[0]" id="vue-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="vue-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 1</label>
                                    </div>
                                </li>
                                <li class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[1]" id="react-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="react-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 2</label>
                                    </div>
                                </li>
                                <li class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[2]" id="angular-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="angular-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 3</label>
                                    </div>
                                </li>
                                <li class="w-full dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[3]" id="laravel-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="laravel-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 4</label>
                                    </div>
                                </li>
                            </ul>
                            <ul class="mt-2 items-center w-full text-sm font-medium text-gray-900 bg-white rounded-lg border border-gray-200 sm:flex dark:bg-gray-700 dark:border-gray-600 dark:text-white">
                                <li class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[4]" id="vue-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="vue-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 5</label>
                                    </div>
                                </li>
                                <li class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[5]" id="react-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="react-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 6</label>
                                    </div>
                                </li>
                                <li class="w-full border-b border-gray-200 sm:border-b-0 sm:border-r dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[6]" id="angular-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="angular-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 7</label>
                                    </div>
                                </li>
                                <li class="w-full dark:border-gray-600">
                                    <div class="flex items-center pl-3">
                                        <input v-model="gens[7]" id="laravel-checkbox-list" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                                        <label for="laravel-checkbox-list" class="py-3 ml-2 w-full text-sm font-medium text-gray-900 dark:text-gray-300">Gen 8</label>
                                    </div>
                                </li>
                            </ul>
                        </div>
                        <div class="px-4 py-3 pt-1 pl-10 pr-10">
                            <h3 class="text-2xl pb-4">Extra</h3>
                            <div class="flex">
                                <div class="flex items-center mr-4">
                                    <input v-model="hisui" id="inline-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600">
                                    <label for="inline-checkbox" class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">Hisui</label>
                                </div>
                                <div class="flex items-center mr-4">
                                    <input v-model="mega" id="inline-2-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 rounded border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600">
                                    <label for="inline-2-checkbox" class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">Mega Evo</label>
                                </div>
                            </div>
                        </div>
                        <div class="px-4 py-3 pt-1 pl-10 pr-10">
                            <h3 v-if="idiom =='Español'" class="text-2xl pb-4">Configuración</h3>
                            <h3 v-else class="text-2xl pb-4">Config</h3>
                            <div class="flex space-x-10">
                                <div>
                                    <label v-if="idiom =='Español'" for="pokemon" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Numero de pokemons</label>
                                    <label v-else for="pokemon" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Number of pokemon</label>
                                    <input v-model="numPok" type="number" id="pokemon" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                </div>
                                <div>
                                    <label v-if="idiom =='Español'" for="item" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Numero de items</label>
                                    <label v-else for="item" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Number of items</label>
                                    <input v-model="numObj" type="number" id="item" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" required>
                                </div>
                            </div>
                        </div>  
                        <div class="px-4 py-3 pb-10 sm:flex sm:flex-row-reverse sm:px-6"> <!-- Botones -->
                            <!-- <button type="button" class="inline-flex w-full justify-center rounded-md border border-transparent bg-red-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2 sm:ml-3 sm:w-auto sm:text-sm">Deactivate</button> -->
                            <button v-if="idiom == 'English'" type="button" class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-300 bg-blue-400 px-4 py-2 text-base font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm" v-on:click="accept" >Accept</button>
                            <button v-else type="button" class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-300 bg-blue-400 px-4 py-2 text-base font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm" v-on:click="test" >Aceptar</button>
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
            gens: [],
            hisui: false,
            mega: false,
            numObj: 10,
            numPok: 30,
            options: {
                idiom: 'Español',
                generate: []
            }
        }
    },
    methods: {
        accept() {
            this.isHidden = !this.isHidden

            console.log({opciones: this.options});
        },
        test() {
            console.log(this.gens, this.mega, this.hisui, this.numObj, this.numPok);
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
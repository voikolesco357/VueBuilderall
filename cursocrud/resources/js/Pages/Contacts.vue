<template>
<app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                CONTACTS
            </h2>
        </template>

        <button class="bg-blue-500 text-white p-2 rounded" @click="openModal()">Open</button>
        <div v-if="isOpen" class="fixed inset-0 text-center">

            <div class="fixed inset-0 transition-opacity bg-blue-500 opacity-40"></div>

            <div class="inline-block bg-white rounded-lg text-left overflow-hidden shadow-x1 transform m-8 sm:max-w-md sm:w-full">
                <form>
                    <div class="bg-white p-4">
                        <h2>Contact Form</h2>
                        <div class="mb-4">
                            <label for="name">Name: </label>
                            <input id="name" type="text" v-model="form.name" placeholder="Enter Name" class="rounded w-full"/>
                        </div>
                        <div class="mb-4">
                            <label for="phone">Phone: </label>
                            <input id="phone" type="text" v-model="form.phone" placeholder="Enter Phone" class="rounded w-full"/>
                        </div>
                        <div class="mb-4">
                            <label for="email">Email: </label>
                            <input id="email" type="email" v-model="form.email" placeholder="Enter email" class="rounded w-full"/>
                        </div>
                        <div class="mb-4">
                            <label for="birthday">Birthday: </label>
                            <input id="birthday" type="date" v-model="form.name" placeholder="Enter birthday" class="rounded w-full"/>
                        </div>
                        <div class="mb-4">
                            <label for="type">Type:</label>
                            <select id="type" v-model="form.type" class="rounded w-full">
                                <option v-for="option in types" v-bind:key="option.value">
                                    {{ option.text }}
                                </option>
                            </select>
                        </div>
                        <div>
                            <button class="bg-green-500 text-white p-2 rounded" @click="closeModal()">Save</button>
                            <button class="bg-red-500 text-white p-2 rounded" @click="closeModal()">Cancel</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </app-layout>
</template>

<script>
import AppLayout from '@/Layouts/AppLayout'
import Welcome from '@/Jetstream/Welcome'

export default {
    data() {
        return{
            isOpen: false,
            form: {
                name: null,
                phone: null,
                email: null,
                birthday: null,
                type: 1,
            },
            types: [
                { text: 'Pessoal'   , value: '1' },
                { text: 'Celular'   , value: '2' },
                { text: 'Casa'      , value: '3' },
                { text: 'Comercial' , value: '4' },
                { text: 'Principal' , value: '5' },
                { text: 'Secundário', value: '6' },
                { text: 'Fax'       , value: '7' },
                { text: 'Outro'     , value: '8' },
            ]
        }
    },
    components: {
        AppLayout,
        Welcome,
    },
    methods: {
        closeModal() {
            this.reset();
            this.isOpen = false;
        },
        openModal() {
            this.reset();
            this.isOpen = true;
        },
        reset(){
            this.form.name = null;
            this.form.phone = null;
            this.form.email = null;
            this.form.birthday = null;
            this.form.type = 1;
        }
    }
}
</script>

<style>

</style>
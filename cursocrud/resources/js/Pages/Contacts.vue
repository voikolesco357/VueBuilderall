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
                        <div>
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
            }
        }
    },
    components: {
        AppLayout,
        Welcome,
    },
    methods: {
        closeModal() {
            this.isOpen = false;
        },
        openModal() {
            this.isOpen = true;
        }
    }
}
</script>

<style>

</style>
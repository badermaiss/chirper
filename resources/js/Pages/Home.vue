<script setup>
import UnauthenticatedLayout from '@/Layouts/UnauthenticatedLayout.vue';
import InputError from '@/Components/InputError.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import { useForm, Head } from '@inertiajs/inertia-vue3';
import GuestChirp from '@/Components/GuestChirp.vue';
 
const form = useForm({
    message: '',
});

defineProps(['chirps']);

</script>
 
<template>
    <Head title="Chirps" />
 
    <UnauthenticatedLayout>
        <div class="max-w-2xl mx-auto p-4 sm:p-6 lg:p-8">            
            <div class="mt-6 bg-white shadow-sm rounded-lg divide-y">
                <GuestChirp
                    v-for="chirp in chirps"
                    :key="chirp.id"
                    :chirp="chirp"
                />
            </div>
        </div>
    </UnauthenticatedLayout>
</template>
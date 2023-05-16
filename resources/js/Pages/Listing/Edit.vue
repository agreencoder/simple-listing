<template>
    <form @submit.prevent="update">

        <div>
            <label>Name</label>
            <input v-model="form.name" type="text">
            <div v-if="form.errors.name" >{{ form.errors.name }}</div>
        </div>

        <div>
            <label>Age</label>
            <input v-model.number="form.age" type="text">
            <div v-if="form.errors.age" >{{ form.errors.age }}</div>
        </div>

        <div>
            <label>Address</label>
            <input v-model="form.address" type="text">
            <div v-if="form.errors.address" >{{ form.errors.address }}</div>
        </div>

        <div>
            <input type="submit" value="Update">
        </div>

    </form>
</template>

<script setup>

import {useForm} from '@inertiajs/inertia-vue3'

    const props = defineProps({
        'listing' : Object
    })
    const form = useForm({
        name: props.listing.name,
        age: props.listing.age,
        address: props.listing.address,
    })

    const update = () => form.put(route('listing.update', {listing: props.listing.id}))
    
</script>
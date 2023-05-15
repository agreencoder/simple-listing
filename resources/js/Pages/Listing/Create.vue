<template>

    <form @submit.prevent="create">
        <div>
            <div>
                <label>Name</label>
            </div>
            <div><input v-model="form.name" type="text"></div>
            <div>{{ form.errors.name }}</div>
        </div>

        <div>
            <div>
                <label>Age</label>
            </div>
            <div><input v-model.number="form.age" type="text"></div>
            <div>{{ form.errors.age }}</div>
        </div>

        <div>
            <div>
                <label>Address</label>
            </div>
            <div><input v-model="form.address" type="text"></div>
            <div>{{ form.errors.address }}</div>
        </div>

        <div>
            <button type="submit">Create</button>
        </div>
        

    </form>


</template>

<script setup>
    import {useForm} from '@inertiajs/inertia-vue3'
    const form = useForm({
        name: null,
        age: 0,
        address: null,
    })
    const create = () => form.post(route('listing.store'))
</script>
<template>
    <div>
        <Link :href="route('listing.index')">Home</Link>
        <Link :href="route('listing.create')">Create</Link>
        <div v-if="flashSuccess" class="success">
            {{ flashSuccess }}
        </div>

    </div>
    <slot>Default</slot>
</template>

<script setup>
import {Link} from '@inertiajs/inertia-vue3'
import {computed} from 'vue'
import {usePage} from '@inertiajs/inertia-vue3'
const page = usePage()
const flashSuccess = computed(
    () => page.props.value.flash.success,
)
</script>

<style scoped>
    .success{
        background-color: green;
        color: #fff;
    }
</style>
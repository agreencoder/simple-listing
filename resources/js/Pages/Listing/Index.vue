<template>
    <div>
        <div v-for="listing in listings" :key="listing.id">
            <Link :href="route('listing.show', {listing: listing.id})">
                <ListingDetail :listing="listing" />
            </Link>
            <div>
                <Link :href="route('listing.edit', {listing: listing.id})">Edit</Link>
                <Link :href="route('listing.destroy', {listing: listing.id})" method="DELETE">Delete</Link>
            </div>
        </div>
        
    </div>
</template>

<script setup>
import {Link} from '@inertiajs/inertia-vue3'
import ListingDetail from '@/Components/ListingDetail.vue';
defineProps({
        listings: Array,
    })
</script>

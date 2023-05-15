<template>
    <div>
        <div v-for="listing in listings" :key="listing.id">
            <Link :href="route('listing.show', {listing: listing.id})">
                <ListingDetail :listing="listing" />
            </Link>
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

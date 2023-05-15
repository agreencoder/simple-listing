<template>
    <ListingDetail :listing="listing" />
</template>

<script setup>
import ListingDetail from '@/Components/ListingDetail.vue';
    defineProps({
        listing: Object,
    })
</script>
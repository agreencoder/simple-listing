<template>
    <span> {{ listing.id }} - {{ listing.name }} - {{ listing.age }} - {{ listing.address }} </span>
</template>

<script setup>
    defineProps({
        listing: Object,
    })
</script>
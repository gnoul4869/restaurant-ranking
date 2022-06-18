<script setup lang="ts">
defineProps<{
    index: number;
    rank: number;
    name: string;
    isHeader: boolean;
}>();
</script>

<template>
    <div class="row" v-if="isHeader">
        <h4 class="header">Rank</h4>
        <h4 class="header">Chain</h4>
    </div>
    <div class="row" :style="index % 2 === 0 && { background: 'LavenderBlush' }">
        <h4 class="header rank">{{ rank }}</h4>
        <a :href="`/${name}`" class="header link">{{ name }}</a>
    </div>
</template>

<style lang="scss" scoped>
.row {
    border-top: 1px solid #80808056;
    display: flex;
    align-items: center;
}
.header {
    font-size: 1.25rem;
    color: #0a1f94;
    margin: 0;
    margin-right: 2rem;
    padding: 0.5rem 1rem;
    font-weight: 700;
    width: 4rem;
}
.rank {
    color: black;
}
.link {
    text-decoration: none;
    color: #e49d1b;
    width: auto;
    font-weight: 500;
}
</style>

<script setup lang="ts">
import restaurants from '@/data.json';

const splittedRestaurants = {
    left: [...restaurants].splice(0, Math.ceil(restaurants.length / 2)),
    right: [...restaurants].splice(Math.ceil(restaurants.length / 2)),
};
</script>

<template>
    <div class="table">
        <h1>Top 50 Restaurants</h1>
        <div class="table-container">
            <div class="table-col">
                <RestaurantRow
                    v-for="(restaurant, index) in splittedRestaurants.left"
                    :key="restaurant.id"
                    :name="restaurant.name"
                    :rank="restaurant.rank"
                    :index="index"
                    :isHeader="index === 0"
                />
            </div>
            <div class="table-col">
                <RestaurantRow
                    v-for="(restaurant, index) in splittedRestaurants.right"
                    :key="restaurant.id"
                    :name="restaurant.name"
                    :rank="restaurant.rank"
                    :index="index"
                    :isHeader="index === 0"
                />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.table {
    margin: 3rem 0;

    h1 {
        margin-bottom: 2rem;
    }

    .table-container {
        display: flex;
        justify-content: space-between;
        .table-col {
            width: 48%;
        }
    }
}
</style>

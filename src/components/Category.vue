<template>
    <div class="category">
        <h2>{{ title }}</h2>
        <ul>
            <li v-for="item in items" :key="item.id">{{ item.name }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Category',

    props: {
        title: {
            type: String,
            required: true
        },
        items: {
            type: Array,
            required: true
        }
    }
}
</script>

<style>
.category {
    padding: 1rem;
    border: 1px solid #ccc;
    border-radius: 5px;
}
.category h2 {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
}
.category ul {
    list-style-type: none;
    padding: 0;
}
.category li {
    margin: 0.25rem 0;
}
</style>

<template>
    <header>
        <input v-model="userSearchText" type="text">
        <button @click="$emit('userSearch', userSearchText)">Cerca</button>
    </header>
</template>
<script>
export default {
    name: "Header",
    data: function() {
        return {
            userSearchText: '',
        }
    }
}
</script>
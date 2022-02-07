<template>
    <div class="header">
        <div class="logo">
            Logo
        </div>
        <div class="buttons">
            <input  class="search-input" type="text" name="" id="" v-model="inputModel">
            <button class="search-button" @click="$emit('search', inputModel)"> Cerca</button>
        </div>
    </div>
</template>


<script>
export default {
    data() {
        return {
            inputModel : ''
        }
    },
}
</script>


<style lang="scss" scoped>

.header {
    width: 100%;
    height: 80px;
    display: flex;
    justify-content: space-between;
    padding: 20px 100px;
    background: teal;
    color: white;
    align-items: center;
}


</style>
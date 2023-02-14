<template>
    <div>
        <p>"Everything you need for your candy list"</p>
        <button @click="get_list">Candy List</button>
        <button @click="add_candy">Add Candy</button>
        <button @click="change_candy">Change Candy</button>
        <button @click="delete_candy">Delete Candy</button>
    </div>
</template>

<script>
import axios from "axios";
    export default {
        name : "candyStore",
        methods: {
        get_list() {
            axios.request({
                url: 'http://127.0.0.1:5000/api/candy',
                method : "GET",
            }).then((response)=> {
                let src = response;
                this.$root.$emit(src)
                print(response)
            }).catch((error) => {
                print(error);
            })
        },
        add_Candy() {
            axios.request({
                url: 'http://127.0.0.1:5000/api/candy',
                method : "POST",
            }).then((response)=> {
                let src = response;
                this.$root.$emit(src)
                print(response)
            }).catch((error) => {
                print(error);
            })
        },
    },
}
</script>

<style scoped>

</style>
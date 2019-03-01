<template>
    <div >
        <div v-for="item in ask">
            {{item.title}}
        </div>
    </div>
</template>

<script>
import { fetchAskList } from '../api/api.js';
export default {
    data() {
        return {
            ask: []
        }
    },
    created() {
        let vm = this;
        fetchAskList()
            .then(response => {
            console.log(response);
            vm.ask = response.data;
             })
            .catch(err => {
            console.log(err);
            });
    }
}
</script>

<style>

</style>

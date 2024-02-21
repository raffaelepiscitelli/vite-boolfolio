<template lang="">
    <main class= "container">
        <section class="row">
            <div class="12">
                <h1>My Projects</h1>
                <ul>
                    <li v-for='portfolio in portfolios' :key='portfolio.id'>
                        {{portfolio.project}}
                    </li>
                </ul>
            </div>

        </section>
    </main>
</template>
<script>
import axios from 'axios';
export default {
    name: 'AppMain',
    data() {
        return {
            portfolios: [],
        }
    },
    methods: {
        getPortfolios() {
            axios.get('http://127.0.0.1:8000/api/portfolios', {
                params: {
                }
            })
                .then((response) => {
                    console.log(response.data.results.data);
                    this.portfolios = response.data.results.data;
                })
                .catch(function (error) {
                    console.warn(error);
                    this.$router.push({ name: 'not-found' })
                })
        }
    },
    created() {
        this.getPortfolios();
    }
}
</script>
<style lang="">
    
</style>
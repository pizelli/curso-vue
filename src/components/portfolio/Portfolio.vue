<template>
    <v-layout row wrap>
        <Stock v-for="stock in stocks" :key="stock.id" :stock="stock" />
        <v-layout v-if="stocks.length < 1" row justify-center="">
            <v-card>
                <v-card-text>
                    Nenhuma ação até o momento!
                </v-card-text>
            </v-card>
        </v-layout>
    </v-layout>
</template>

<script>
import {mapGetters} from 'vuex'
import Stock from './Stock'

export default {
    components: { Stock },
    computed: {
        ...mapGetters({stocks: 'stockPortfolio'})
    }

}
</script>

<style>

</style>

<template lang="pug">
    div.section
        div.container
<<<<<<< HEAD
            h2.title Portfolio Modificado por TEG
=======

            h2.title Portfolio -s titulo de Sandy

>>>>>>> 64de6284c7c374ed2328e394f4595003d970c5e8
            div(v-if="items.length === 0")
                div.content
                    p 
                        | Error de prueba número dos probando una rama de tipo bugfix
                        |Hello, You have no shares right now. Buy some on the, saludos para todos
                        router-link(to="/stocks") market.
            div(v-else)
                div.columns.is-multiline
                    div.column.is-half(v-for="asset in items")
                        asset(
                            :name="asset.name", 
                            :quantity="asset.quantity", 
                            :price="asset.price", 
                            action="SELL"
                            :onAction="sell"
                        )
</template> 

<script>
import { mapGetters, mapActions } from 'vuex';

import Asset from '../../../components/Asset';

export default {
    computed: mapGetters('portfolio', ['items']),
    methods: mapActions('stock', ['sell']),
    components: {
        Asset
    }
};
</script>

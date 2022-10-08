<template>
    <div>
        <v-row class="second-row" justify="space-between">
            <v-col cols="auto" class="all-link">
                <a :href="2" class="episodes">{{ rowInfo.name }}</a>
            </v-col>
            <v-col cols="auto" class="see-all all-link" align-self="center"><a :href="3">See all</a></v-col>
        </v-row>
        <v-row justify="space-around">
            <v-col cols="auto" v-for="card in rowInfo.cards" :key="card.image">
                <AlbumCard :rowInfo="card" />
            </v-col>
        </v-row>
    </div>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";

export default {
    name: "AlbumsCard",
    components: { AlbumCard },
    props: ["rowInfo"],
    computed: {
        cardCount() {
            return Math.floor(window.innerWidth / 250);
        },
    },
};
</script>

<style lang="scss">
.second-row {
    padding: 0 4px;
}

.episodes {
    font-size: 24px;
    font-weight: bold;
}
.see-all {
    font-size: 12px;
    text-transform: uppercase;
    font-weight: bold;
    letter-spacing: 1px;

    a {
        color: #b3b3b3 !important;
    }
}
.all-link:hover {
    text-decoration: underline;
}
</style>
>

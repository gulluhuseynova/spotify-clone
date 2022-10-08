<template>
    <v-card class="hit-boxes show-anim" width="180" >
        <v-img class="white--text align-end card-img" height="150px" :src="rowInfo.image">
            <v-btn class="card-btn show-child scale-anim" elevation="2" fab x-small color="green">
                <v-icon>mdi-play</v-icon>
            </v-btn>
        </v-img>
        <v-card-text class="text--primary">
            <div style="font-weight: bold; font-size: 15px">NAME</div>
            <div style="font-size: 13px; color: #a7a7a7; font-weight: 500; font-family: sans-serif">
                Listen to all the tracks you've been missing.
            </div>
        </v-card-text>
    </v-card>
</template>

<script>
export default {
    name: "AlbumCard",
    props: ["rowInfo"],
    data: () => ({
        
    }),
};
</script>

<style lang="scss">
.hit-boxes {
    padding: 10px;
    background-color: black;

    &:hover {
        background-color: rgba(44, 44, 44, 0.699) !important;
    }

    .card-img {
        position: relative;

        .card-btn {
            width: 30px;
            height: 30px;
            position: absolute;
            right: 7px;
            bottom: 7px;
        }
    }
}
</style>

<template>
    <v-card elevation="3" class="card-box show-anim" outlined color="transparent">
        <v-row no-gutters>
            <img src="@/assets/ariana.jpeg" alt="ariana" width="70px" height="70px" style="border-radius: 3px" />
            <v-col cols="auto" align-self="center" class="ml-3">Ariana Grande</v-col>
            <v-col cols="auto" align-self="center" class="mr-3">
                <v-btn class="play-icon show-child scale-anim" elevation="3" fab x-small color="green">
                    <v-icon>mdi-play</v-icon>
                </v-btn>
            </v-col>
        </v-row>
    </v-card>
</template>

<script>
export default {
    name: "RecentAlbums",
};
</script>

<style lang="scss" scoped>
.card-box {
    min-width: 250px;
    border-radius: 3px;

    .play-icon {
        position: absolute;
        right: 10px;
        top: calc(50% - 16px);
    }
}
</style>

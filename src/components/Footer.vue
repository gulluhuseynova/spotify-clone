<template>
    <v-footer app>
        <v-row no-gutters>
            <v-col cols="auto" align-self="center">
                <v-row dense>
                    <v-img id="active-img" src="@/assets/Grande.jpg" alt="ariana" width="60px" height="60px" style="margin: 10px">
                        <v-btn class="scale-anim" id="arrow-btn" fab x-small text color="black">
                            <v-icon color="white" size="25px">mdi-chevron-up</v-icon>
                        </v-btn>
                    </v-img>
                    <v-col cols="auto" align-self="center">
                        <v-row dense no-gutters>
                            <v-col id="song-style" @click="true">7 rings</v-col>
                        </v-row>
                        <v-row dense no-gutters>
                            <v-col id="singer-style" @click="true">Ariana Grande</v-col>
                        </v-row>
                        <v-row dense no-gutters>
                            <v-col id="singer-style" @click="true">Ariana Grande</v-col>
                        </v-row>
                    </v-col>
                    <v-col cols="auto" align-self="center" id="heart-icon">
                        <v-icon small color="rgba(245, 245, 245, 0.658)" @click="heartToggle" :style="{ color: heartToggle, red: 'white' }"
                            >mdi-cards-heart-outline</v-icon
                        >
                    </v-col>
                </v-row>
            </v-col>
            <v-spacer />
            <v-col style="width: 400px; position: absolute; left: 50%; transform: translateX(-50%)">
                <v-row dense>
                    <v-spacer />
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-shuffle-variant</v-icon></v-btn>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-skip-previous</v-icon></v-btn>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon large>mdi-pause-circle</v-icon></v-btn>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-skip-next</v-icon></v-btn>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-repeat-variant</v-icon></v-btn>
                    </v-col>
                    <v-spacer />
                </v-row>
                <v-row dense align="center">
                    <v-col cols="auto" class="music-progress-duration">00:05</v-col>
                    <v-col>
                        <v-progress-linear color="white" height="4" value="10" striped />
                    </v-col>
                    <v-col cols="auto" class="music-full-duration">03:20</v-col>
                </v-row>
            </v-col>
            <v-spacer />
            <v-col cols="auto">
                <v-row no-gutters>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-microphone-variant</v-icon></v-btn>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-playlist-music</v-icon></v-btn>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-cellphone-link</v-icon></v-btn>
                    </v-col>
                    <v-col>
                        <v-slider style="width: 120px" color="white" v-model="media">
                            <template v-slot:prepend>
                                <v-btn fab x-small elevation="0" style="margin-top: -4px"><v-icon small>mdi-volume-high</v-icon></v-btn>
                            </template>
                        </v-slider>
                    </v-col>
                    <v-col cols="auto">
                        <v-btn fab x-small elevation="0"><v-icon small>mdi-fullscreen-exit</v-icon></v-btn>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-footer>
</template>

<script>
export default {
    name: "Footer",
    data: () => ({
        media: 0,
        heart: false,
    }),
    methods: {
        heartToggle() {
            this.heart = !this.heart;
            console.log(this.heart);
        },
        zoomOut() {
            this.zoom = this.zoom - 10 || 0;
        },
        zoomIn() {
            this.zoom = this.zoom + 10 || 100;
        },
    },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kaushan+Script&family=Licorice&family=Nanum+Gothic:wght@800&display=swap");

#song-style {
    font-size: 13px;
    line-height: 15px;
    font-family: "Nanum Gothic", sans-serif;
}
#song-style:hover {
    text-decoration: underline;
}
#singer-style {
    font-size: 10px;
    font-family: sans-serif;
    font-weight: lighter;
    color: rgba(245, 245, 245, 0.658);
}
#singer-style:hover {
    text-decoration: underline;
    color: white;
}
#heart-icon {
    margin-left: 10px;
}

.music-progress-duration,
.music-full-duration {
    font-size: 10px;
}

#active-img {
    position: relative;
}
#active-img:hover #arrow-btn {
    opacity: 1;
}

#arrow-btn {
    position: absolute;
    right: 2px;
    top: 2px;
    opacity: 0;
}
</style>

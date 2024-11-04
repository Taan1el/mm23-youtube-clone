<script setup>
import { ref } from "vue";

const items = ["How to code with vue", "Help me code", "I am lost"];
const drawer = ref(true);
const rail = ref(false);

const videoCards = [
  {
    thumbnail: "https://picsum.photos/id/24/600/420",
    title: "Cool beats for beach day",
    channel: "CheZee",
    vaatamist: "905K vaatamist",
    timeAgo: "2 päeva eest",
    duration: "8:20",
  },
  {
    thumbnail: "https://picsum.photos/id/255/600/420",
    title: "Rahulikud laulud",
    channel: "Uku leele",
    vaatamist: "707tuh vaatamist",
    timeAgo: "2 kuu eest",
    duration: "12:19",
  },
  {
    thumbnail: "https://picsum.photos/id/42/600/420",
    title: "The story of the spooky ghost",
    channel: "WeeWoo",
    vaatamist: "1.8M vaatamist",
    timeAgo: "3 kuu eest",
    duration: "1:11",
  },
  {
    thumbnail: "https://picsum.photos/id/452/600/420",
    title: "10 cars vs 1 big car",
    channel: "On drugs",
    vaatamist: "3.5 mln vaatamist",
    timeAgo: "1 aasta eest",
    duration: "9:10",
  },
  {
    thumbnail: "https://picsum.photos/id/62/600/420",
    title: "Spooky season",
    channel: "Scary BoB",
    vaatamist: "322 tuh vaatamist",
    timeAgo: "11 tunni eest",
    duration: "8:51",
  },
  {
    thumbnail: "https://picsum.photos/id/92/600/420",
    title: "New York - Official music video",
    channel: "Jaagup z",
    vaatamist: "905 tuh vaatamist",
    timeAgo: "2 päeva eest",
    duration: "13:20",
  },
  {
    thumbnail: "https://picsum.photos/id/48/600/420",
    title: "Tule minuga Tallinna",
    channel: "Aksel Kihula",
    vaatamist: "707 tuh vaatamist",
    timeAgo: "6 nädala eest",
    duration: "18:19",
  },
  {
    thumbnail: "https://picsum.photos/id/44/600/420",
    title: "New halloween news",
    channel: "ScareCrow",
    vaatamist: "1.8 mln vaatamist",
    timeAgo: "3 nädala eest",
    duration: "11:11",
  },
  {
    thumbnail: "https://picsum.photos/id/44/600/420",
    title: "Relaxing nature sounds",
    channel: "Rahu ja Heli",
    vaatamist: "3.5 mln vaatamist",
    timeAgo: "8 nädala eest",
    duration: "39:10",
  },
  {
    thumbnail: "https://picsum.photos/id/46/600/420",
    title: "The New Tesla",
    channel: "Elon Musk",
    vaatamist: "322 tuh vaatamist",
    timeAgo: "11 tundi tagasi",
    duration: "58:51",
  },
  {
    thumbnail: "https://picsum.photos/id/49/600/420",
    title: "Cool beats for beach day",
    channel: "CheZee",
    vaatamist: "905 tuh vaatamist",
    timeAgo: "2 päeva eest",
    duration: "18:20",
  },
  {
    thumbnail: "https://picsum.photos/id/12/600/420",
    title: "WhyDee - Jack In The Box",
    channel: "WhyDee",
    vaatamist: "707 tuh vaatamist",
    timeAgo: "3 nädala eest",
    duration: "2:23",
  },
];
</script>;

<template>
  <v-app theme="dark">
    <v-navigation-drawer
      v-model="drawer"
      :rail="rail"
      permanent
      style="border-right: none">
      
      <v-btn icon @click.stop="rail = !rail" style="box-shadow: none;">
        <v-icon>mdi-menu</v-icon>
      </v-btn>

      <v-list density="compact" nav>
        <v-list-item prepend-icon="mdi-home" title="Avaleht" value="myfiles" />
        <v-list-item prepend-icon="mdi-youtube" title="Shorts" value="shared" />
        <v-list-item prepend-icon="mdi-youtube-subscription" title="Tellimused" value="starred" />
      </v-list>
    </v-navigation-drawer>

    <v-app-bar>
      <v-img max-width="30" max-height="40" cover src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg" />
      <v-app-bar-title style="font-weight: 600; max-width: 100px">YouTube</v-app-bar-title>

      <v-autocomplete
            :items="items"
            class="mx-auto"
            density="comfortable"
            menu-icon="mdi-magnify"
            placeholder="Search"
            style="max-width: 600px; margin-top: 20px"
            theme="dark"
            variant="solo"
            auto-select-first
            item-props
            rounded>
          </v-autocomplete>

      <v-avatar class="d-flex align-center mr-5" size="45">
        <v-img src="https://thispersondoesnotexist.com/"/>
      </v-avatar>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-chip-group>
          <v-chip>Kõik</v-chip>
          <v-chip>Mängud</v-chip>
          <v-chip>Muusika</v-chip>
          <v-chip>Otse</v-chip>
          <v-chip>Tisleritöö</v-chip>
          <v-chip>Animatsioon</v-chip>
          <v-chip>Käsitöö</v-chip>
          <v-chip>Söök</v-chip>
          <v-chip>Märuliseiklusmängud</v-chip>
          <v-chip>Platvormimängud</v-chip>
          <v-chip>Räpp</v-chip>
          <v-chip>Miksid</v-chip>
          <v-chip>Hiljuti üles laetud</v-chip>
          <v-chip>Vaadatud</v-chip>
          <v-chip>Midagi teist</v-chip>
        </v-chip-group>

        <v-row dense>
          <v-col v-for="(video, index) in videoCards" :key="index" cols="4" sm="6" md="4" lg="3">
            <v-card class="elevation-2" outlined>
              
              <v-img :src="video.thumbnail" height="250px">
                <template #append>
                  <div class="videopikkus">{{ video.videopikkus }}</div>
                </template>
              </v-img>

              <v-card-subtitle class="d-flex align-center" style="gap: 20px;">
                  <v-avatar size="45">
                    <v-img src="https://thispersondoesnotexist.com/"/>
                  </v-avatar>
                  <span class="video-title">{{ video.title }}</span>
              </v-card-subtitle>

              <v-card-subtitle class="align-center mt-4 text-muted">
                <span class="channel">{{ video.channel }}</span><br />
                <span class="vaatamist">{{ video.vaatamist }} • {{ video.timeAgo }}</span>
              </v-card-subtitle>

            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<style>

.videopikkus {
  position: absolute;
  bottom: 8px;
  right: 8px;
  background-color: #212121;
  color: white;
  padding: 2px 6px;
  border-radius: 3px;
  font-size: 14px;
}

.video-title {
  font-weight: bold;
  font-size: 14px;
}

.channel,
.vaatamist {
  font-size: 12px;
  color: rgb(255, 255, 255);
}
</style>
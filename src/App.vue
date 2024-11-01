<script setup>
import { ref } from "vue";

const items = ["Search Item 1", "Search Item 2", "Search Item 3"];
const drawer = ref(true);
const rail = ref(false);

const videoCards = [
  {
    thumbnail: "https://via.placeholder.com/400x220",
    title: "Live from the Anjunakitchen",
    channel: "Anjunadeep",
    views: "95K views",
    timeAgo: "1 month ago",
    duration: "1:00:22",
  },
  {
    thumbnail: "https://via.placeholder.com/400x220",
    title: "Morning Chill House Music",
    channel: "Alex Flare",
    views: "707K views",
    timeAgo: "4 months ago",
    duration: "1:12:19",
  },
  {
    thumbnail: "https://via.placeholder.com/400x220",
    title: "Every Skoda vRS Drag Race",
    channel: "Carwow",
    views: "1.8M views",
    timeAgo: "1 year ago",
    duration: "11:11",
  },
  {
    thumbnail: "https://via.placeholder.com/400x220",
    title: "Chillout Deep House Music Mix",
    channel: "Flavour Trip",
    views: "3.5M views",
    timeAgo: "1 year ago",
    duration: "1:39:10",
  },
  {
    thumbnail: "https://via.placeholder.com/400x220",
    title: "Tesla Cybertruck Reveal",
    channel: "BulkDrive",
    views: "322K views",
    timeAgo: "11 hours ago",
    duration: "58:51",
  },
];
</script>

<template>
  <v-app theme="dark">
    <v-navigation-drawer
      v-model="drawer"
      :rail="rail"
      permanent
      style="border-right: none"
    >
      <v-btn icon @click.stop="rail = !rail" style="box-shadow: none;">
        <v-icon>mdi-menu</v-icon>
      </v-btn>

      <v-list density="compact" nav>
        <v-list-item prepend-icon="mdi-home" title="Home" value="myfiles" />
        <v-list-item prepend-icon="mdi-youtube" title="Shorts" value="shared" />
        <v-list-item prepend-icon="mdi-youtube-subscription" title="Subscriptions" value="starred" />
        <v-list-item prepend-icon="mdi-account-circle-outline" title="Account" value="starred" />
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
            style="max-width: 650px; margin-top: -10px"
            theme="dark"
            variant="solo"
            auto-select-first
            item-props
            rounded
          >
          </v-autocomplete>

      <v-btn icon>
        <v-icon>mdi-microphone</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-video-plus-outline</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-bell-outline</v-icon>
      </v-btn>

      <v-avatar>
        <v-img src="https://randomuser.me/api/portraits/women/85.jpg" />
      </v-avatar>
    </v-app-bar>

    <v-main>
      <v-container>
        <!-- Chip Group -->
        <v-chip-group>
          <v-chip>All</v-chip>
          <v-chip>Gaming</v-chip>
          <v-chip>Music</v-chip>
          <v-chip>Playlists</v-chip>
          <v-chip>Live</v-chip>
          <v-chip>Watched</v-chip>
          <v-chip>New to you</v-chip>
          <v-chip>Racing video</v-chip>
        </v-chip-group>

        <!-- Video Card Grid -->
        <v-row dense>
          <v-col v-for="(video, index) in videoCards" :key="index" cols="12" sm="6" md="4" lg="3">
            <v-card class="elevation-2" outlined>
              <v-img :src="video.thumbnail" height="180px">
                <template #append>
                  <div class="duration-overlay">{{ video.duration }}</div>
                </template>
              </v-img>
              <v-card-subtitle class="mt-2">
                <span class="video-title">{{ video.title }}</span>
              </v-card-subtitle>
              <v-card-subtitle class="text-muted">
                <span class="channel-name">{{ video.channel }}</span><br />
                <span class="views-info">{{ video.views }} • {{ video.timeAgo }}</span>
              </v-card-subtitle>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<style scoped>
.duration-overlay {
  position: absolute;
  bottom: 8px;
  right: 8px;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  padding: 2px 6px;
  border-radius: 3px;
  font-size: 12px;
}

.video-title {
  font-weight: bold;
  font-size: 14px;
}

.channel-name,
.views-info {
  font-size: 13px;
  color: gray;
}
</style>

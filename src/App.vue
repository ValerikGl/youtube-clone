<script setup>
import { ref, computed } from "vue";

const allVideos = ref([
  {
    thumbnail: "https://picsum.photos/400/220?random=1",
    title: "Live from the Anjunakitchen",
    channel: "Anjunadeep",
    views: "95K views",
    timeAgo: "1 month ago",
    duration: "1:00:22",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=2",
    title: "Morning Chill House Music",
    channel: "Alex Flare",
    views: "707K views",
    timeAgo: "4 months ago",
    duration: "1:12:19",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=3",
    title: "Every Skoda vRS Drag Race",
    channel: "Carwow",
    views: "1.8M views",
    timeAgo: "1 year ago",
    duration: "11:11",
    category: "Racing video",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=4",
    title: "Chillout Deep House Music Mix",
    channel: "Flavour Trip",
    views: "3.5M views",
    timeAgo: "1 year ago",
    duration: "1:39:10",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=5",
    title: "Tesla Cybertruck Reveal",
    channel: "BulkDrive",
    views: "322K views",
    timeAgo: "11 hours ago",
    duration: "58:51",
    category: "Tech",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=1",
    title: "Live from the Anjunakitchen",
    channel: "Anjunadeep",
    views: "95K views",
    timeAgo: "1 month ago",
    duration: "1:00:22",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=2",
    title: "Morning Chill House Music",
    channel: "Alex Flare",
    views: "707K views",
    timeAgo: "4 months ago",
    duration: "1:12:19",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=3",
    title: "Every Skoda vRS Drag Race",
    channel: "Carwow",
    views: "1.8M views",
    timeAgo: "1 year ago",
    duration: "11:11",
    category: "Racing video",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=4",
    title: "Chillout Deep House Music Mix",
    channel: "Flavour Trip",
    views: "3.5M views",
    timeAgo: "1 year ago",
    duration: "1:39:10",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=5",
    title: "Tesla Cybertruck Reveal",
    channel: "BulkDrive",
    views: "322K views",
    timeAgo: "11 hours ago",
    duration: "58:51",
    category: "Tech",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=1",
    title: "Live from the Anjunakitchen",
    channel: "Anjunadeep",
    views: "95K views",
    timeAgo: "1 month ago",
    duration: "1:00:22",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=2",
    title: "Morning Chill House Music",
    channel: "Alex Flare",
    views: "707K views",
    timeAgo: "4 months ago",
    duration: "1:12:19",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=3",
    title: "Every Skoda vRS Drag Race",
    channel: "Carwow",
    views: "1.8M views",
    timeAgo: "1 year ago",
    duration: "11:11",
    category: "Racing video",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=4",
    title: "Chillout Deep House Music Mix",
    channel: "Flavour Trip",
    views: "3.5M views",
    timeAgo: "1 year ago",
    duration: "1:39:10",
    category: "Music",
  },
  {
    thumbnail: "https://picsum.photos/400/220?random=5",
    title: "Tesla Cybertruck Reveal",
    channel: "BulkDrive",
    views: "322K views",
    timeAgo: "11 hours ago",
    duration: "58:51",
    category: "Tech",
  },
]);

const categories = ["All", "Music", "Racing video", "Tech"];
const selectedCategory = ref("All");
const videosPerPage = ref(4);
const currentPage = ref(1);

const filteredVideos = computed(() => {
  const filtered = selectedCategory.value === "All"
    ? allVideos.value
    : allVideos.value.filter((video) => video.category === selectedCategory.value);
  return filtered.slice(0, currentPage.value * videosPerPage.value);
});

const loadMoreVideos = () => {
  currentPage.value++;
};

const drawer = ref(true);
const rail = ref(false);
const items = ["Search Item 1", "Search Item 2", "Search Item 3"];
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
        <v-list-item prepend-icon="mdi-home" title="Home" />
        <v-list-item prepend-icon="mdi-youtube" title="Shorts" />
        <v-list-item prepend-icon="mdi-youtube-subscription" title="Subscriptions" />
        <v-list-item prepend-icon="mdi-account-circle-outline" title="Account" />
      </v-list>
    </v-navigation-drawer>

    <v-app-bar>
      <v-img
        max-width="30"
        max-height="40"
        cover
        src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg"
      />
      <v-app-bar-title style="font-weight: 600; max-width: 100px">
        YouTube
      </v-app-bar-title>

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
        <v-chip-group
          v-model="selectedCategory"
          class="mb-4"
          density="compact"
          show-arrows
        >
          <v-chip v-for="category in categories" :key="category" filter>
            {{ category }}
          </v-chip>
        </v-chip-group>

        <v-row dense>
          <v-col
            v-for="(video, index) in filteredVideos"
            :key="index"
            cols="12"
            sm="6"
            md="4"
            lg="3"
          >
            <v-card class="elevation-2 video-card" outlined>
              <v-img :src="video.thumbnail" aspect-ratio="16/9">
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

        <div v-if="filteredVideos.length < allVideos.length" class="text-center mt-4">
          <v-btn @click="loadMoreVideos" color="primary" block>
            Load More
          </v-btn>
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<style scoped>
.duration-overlay {
  position: absolute;
  bottom: 8px;
  right: 8px;
  background: rgba(0, 0, 0, 0.8);
  color: white;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 12px;
}

.video-title {
  font-weight: bold;
  font-size: 15px;
  color: #fff;
}

.channel-name {
  font-size: 14px;
  color: #bbb;
}

.views-info {
  font-size: 13px;
  color: #999;
}

.video-card {
  border-radius: 12px;
  overflow: hidden;
  background: #1e1e1e;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  padding-bottom: 20px;
}

.video-card:hover {
  transform: scale(1.05);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.3);
}

.v-img {
  width: 100%;
  object-fit: cover;
}
</style>

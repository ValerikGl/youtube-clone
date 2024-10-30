<script setup></script>

<template>
  <v-app theme="dark">
    <v-responsive class="border rounded" height="100vh">
      <v-app>
        <v-navigation-drawer style="border-right: none;">
          <v-card>
            <v-layout>
              <v-navigation-drawer
                v-model="drawer"
                :rail="rail"
                permanent
                @click="rail = false"
                style="border-right: none;"
              >
                <v-btn
                  icon="mdi-menu"
                  variant="text"
                  @click.stop="rail = !rail"
                ></v-btn>

                <template v-slot:append> </template>

                <v-list density="compact" nav>
                  <v-list-item
                    prepend-icon="mdi-home"
                    title="Home"
                    value="myfiles"
                  ></v-list-item>

                  <v-list-item
                    prepend-icon="mdi-youtube"
                    title="Shorts"
                    value="shared"
                  ></v-list-item>

                  <v-list-item
                    prepend-icon="mdi-youtube-subscription"
                    title="Subscriptions"
                    value="starred"
                  ></v-list-item>

                  <v-list-item
                    prepend-icon="mdi-account-circle-outline"
                    title="Account"
                    value="starred"
                  ></v-list-item>
                </v-list>
              </v-navigation-drawer>
              <v-main style="height: 100vh"></v-main>
            </v-layout>
          </v-card>
        </v-navigation-drawer>

        <v-app-bar title=""
        style="">
          <v-img
            max-width="30"
            max-height="40"
            cover
            src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg"
          ></v-img>
          <v-app-bar-title style="font-weight: 600; max-width: 100px"
            >YouTube</v-app-bar-title
          >

          <v-autocomplete
            :items="items"
            class="mx-auto"
            density="comfortable"
            menu-icon="mdi-magnify"
            placeholder="Search"
            style="max-width: 650px; margin-top: 10px"
            theme="dark"
            variant="solo"
            auto-select-first
            item-props
            rounded
          >
          </v-autocomplete>

          <v-btn
            icon="mdi-microphone"
            style="
              border-radius: 20px;
              height: 40px;
              width: 40px;
              background: #3d3d3d;
            "
          ></v-btn>
          <v-btn icon="mdi-video-plus-outline"></v-btn>
          <v-btn icon="mdi-bell-outline"></v-btn>
          <v-list>
            <v-list-item
              prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
            ></v-list-item>
          </v-list>
        </v-app-bar>

        <v-main>
          <v-container>
            <v-chip-group>
              <v-chip>All</v-chip>

              <v-chip>Gaming</v-chip>

              <v-chip>Music</v-chip>

              <v-chip>laylists</v-chip>

              <v-chip>Live</v-chip>

              <v-chip>Watched</v-chip>

              <v-chip>New to you</v-chip>

              <v-chip>Racing video</v-chip>

              <v-chip>Chip 3</v-chip>

              <v-chip>Chip 3</v-chip>
              
            </v-chip-group>
          </v-container>
        </v-main>
      </v-app>
    </v-responsive>

    <!-- <v-app-bar :elevation="2" style="height: 75px">
      <template v-slot:prepend>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
      </template>
      <v-img
        max-width="30"
        max-height="40"
        cover
        src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg"
      ></v-img>
      <v-app-bar-title
        style="font-weight: 600; max-width: 100px;"
        >YouTube</v-app-bar-title>

        
      <v-autocomplete
        :items="items"
        class="mx-auto"
        density="comfortable"
        menu-icon="mdi-magnify"
        placeholder="Search"
        style="max-width: 650px; margin-top: 10px"
        theme="dark"
        variant="solo"
        auto-select-first
        item-props
        rounded
        
      >
    </v-autocomplete>
      
      <v-icon icon="mdi-microphone" style="border-radius: 20px; height: 40px; width: 40px; background: #3D3D3D;"></v-icon>
      <v-icon icon="mdi-video-plus-outline"></v-icon>
      <v-icon icon="mdi-bell-outline"></v-icon>
      <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
          ></v-list-item>
        </v-list>

    </v-app-bar>

    <v-card>
      <v-layout>
        <v-navigation-drawer expand-on-hover rail style="margin-top: 75px">
          <v-list density="compact" nav>
            <v-list-item
              prepend-icon="mdi-home"
              title="Home"
              value="myfiles"
            ></v-list-item>

            <v-list-item
              prepend-icon="mdi-youtube"
              title="Shorts"
              value="shared"
            ></v-list-item>

            <v-list-item
              prepend-icon="mdi-youtube-subscription"
              title="Subscriptions"
              value="starred"
            ></v-list-item>

            <v-list-item
              prepend-icon="mdi-account-circle-outline"
              title="Account"
              value="starred"
            ></v-list-item>
          </v-list>
        </v-navigation-drawer>

        <v-main style="height: 100vh"></v-main>
      </v-layout>
    </v-card> -->
  </v-app>
</template>

<style scoped></style>

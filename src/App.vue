<script setup></script>

<template>
  <v-app theme="dark">
    <v-app-bar :elevation="2">
      <template v-slot:prepend>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
      </template>
            <v-img
              max-width="40"
              min-height="20"
              cover
              src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fd/YouTube_full-color_icon_%282024%29.svg/1486px-YouTube_full-color_icon_%282024%29.svg.png"
            ></v-img>
      <v-app-bar-title style="font-weight: 600">YouTube</v-app-bar-title>
    </v-app-bar>

    <v-card>
      <v-layout>
        <v-navigation-drawer expand-on-hover rail>
          <v-list>
            <v-list-item prepend-icon="mdi-menu" title="YouTube"></v-list-item>
          </v-list>

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

        <v-main style="height: 550px"></v-main>
      </v-layout>
    </v-card>
  </v-app>
</template>

<style scoped></style>

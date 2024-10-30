<script setup></script>

<template>
  
  <v-app theme="dark">



  <v-responsive class="border rounded" height="100vh">
    <v-app>
      <v-navigation-drawer>
        <v-card>
    <v-layout>
      <v-navigation-drawer
        v-model="drawer"
        :rail="rail"
        permanent
        @click="rail = false"
      >
       
        <v-btn
              icon="mdi-menu"
              variant="text"
              @click.stop="rail = !rail"
            ></v-btn>
        
          <template v-slot:append>
           
          </template>
      

        <v-divider></v-divider>

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
      <v-main style="height: 250px"></v-main>
    </v-layout>
  </v-card>
      </v-navigation-drawer>

      <v-app-bar title="">

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
      
      <v-btn icon="mdi-microphone" style="border-radius: 20px; height: 40px; width: 40px; background: #3D3D3D;"></v-btn>
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
          <h1>Main Content</h1>
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

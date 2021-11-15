<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      class="grey darken-4"
    >
      <v-divider />
      <div v-if="miniVariant">
        <v-list>
          <v-list-item v-for="[icon] in links_mini" :key="icon" link exact>
            <div class="d-flex flex-column align-left">
              <v-list-item-icon>
                <v-icon color="grey">{{ icon }}</v-icon>
              </v-list-item-icon>
            </div>
          </v-list-item>
        </v-list>
      </div>
      <div v-else>
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-list>
        <v-list-item
          v-for="(item, i) in categoryItems"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-subheader class="font-weight-bold py-4 subtitle-1"
        >TELLIMUSED</v-subheader
      >
      <v-list>
        <v-list-item
          v-for="(item, i) in subscriptions"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-avatar>
            <v-img
              src="https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
            ></v-img>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-subheader class="font-weight-bold py-4 subtitle-1"
        >ROHKEM YOUTUBE'IST</v-subheader
      >
      <v-list>
        <v-list-item
          v-for="(item, i) in moreItems"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-list>
        <v-list-item
          v-for="(item, i) in moreItems2"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <div class="ml-6 mr-8 mt-2" style="letter">
        <a
          href="http://localhost:3000/"
          class="link mr-1 text--secondary caption"
          >Teave</a
        >
        <a
          href="http://localhost:3000/"
          class="link mr-1 text--secondary caption"
          >Press</a
        >
        <a href="http://localhost:3000/" class="link text--secondary caption"
          >Autoriõigused</a
        >
        <a href="http://localhost:3000/" class="link text--secondary caption"
          >Võtke meiega ühendust</a
        >
        <a
          href="http://localhost:3000/"
          class="link text--secondary mr-1 caption"
          >Sisuloojad</a
        >
        <a
          href="http://localhost:3000/"
          class="link text--secondary mr-1 caption"
          >Reklaam</a
        >
        <a href="http://localhost:3000/" class="link text--secondary caption"
          >Arendajad</a
        >
      </div>
      <div class="ml-6 mr-8 mt-2">
        <a
          href="http://localhost:3000/"
          class="link text--secondary mr-1 caption"
          >Tingimused</a
        >
        <a href="http://localhost:3000/" class="link text--secondary caption"
          >Privaatsus</a
        >
        <a
          href="http://localhost:3000/"
          class="link text--secondary mr-9 caption"
          >Eeskirjad ja ohutus</a
        >
        <a href="http://localhost:3000/" class="link text--secondary caption"
          >Kuidas YouTube toimib?</a
        >
        <a href="http://localhost:3000/" class="link text--secondary caption"
          >Proovige uusi funktsioone</a
        >
      </div>
      <p class="ml-6 mt-4 body-2 darken" style="color: #757575">
        © 2021 Google LLC
      </p>
      </div>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app flat class="grey darken-4">
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <a class="text-decoration-none white--text" href="/">
        <v-img
          class="white--text"
          width="25"
          src="https://upload.wikimedia.org/wikipedia/commons/e/e1/YouTube_play_buttom_icon_%282013-2017%29.svg"
          max-height="100px"
          max-width="300px"
        >
        </v-img>
      </a>
      <a>
        <v-toolbar-title class="link text--primary ml-1" v-text="title" />
      </a>
      <sup class="grey--text lighten-1">EE</sup>  
      <v-spacer />
      <v-text-field
        flat
        hide-details
        append-icon="mdi-magnify"
        placeholder="Search"
        outlined
        dense
        v-model="searchText"
        @click:append="() => {}"
        class="hidden-sm-and-down"
      ></v-text-field>
      <v-icon>mdi-microphone</v-icon>
      <v-spacer />
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-icon class="mr-8" v-bind="attrs" v-on="on">
            mdi-video-plus
          </v-icon>
        </template>
        <span>Märguanded</span>
      </v-tooltip>
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-icon class="mr-8" v-bind="attrs" v-on="on"> mdi-apps </v-icon>
        </template>
        <span>YouTube-i rakendused</span>
      </v-tooltip>
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-icon class="mr-8" v-bind="attrs" v-on="on"> mdi-bell </v-icon>
        </template>
        <span>Loomine</span>
      </v-tooltip>
      <v-avatar size="40">
        <v-img
          src="https://yt3.ggpht.com/yti/ANoDKi5EBlI_n-5sDTVTuIvwjTIMY74WiDiV9wbSeA=s88-c-k-c0x00ffffff-no-rj-mo"
        ></v-img>
      </v-avatar>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-home",
          title: "Avaleht",
          to: "/1",
        },
        {
          icon: "mdi-youtube-subscription",
          title: "Tellimused",
          to: "/2",
        },
      ],
      links_mini: [
        ["mdi-home", "Avaleht"],
        ["mdi-fire", "Populaarsed"],
        ["mdi-youtube-subscription", "Tellimused"],
        ["mdi-play-box-multiple", "Kogu"]
      ],
      categoryItems: [
        {
          icon: "mdi-play-box-multiple",
          title: "Kogu",
          to: "/3",
        },
        {
          icon: "mdi-history",
          title: "Ajalugu",
          to: "/4",
        },
        {
          icon: "mdi-play-box-outline",
          title: "Teie videod",
          to: "/6",
        },
        {
          icon: "mdi-clock",
          title: "Hiljem vaatamiseks",
          to: "/7",
        },
        {
          icon: "mdi-playlist-play",
          title: "Lemmikud",
          to: "/8",
        },
        {
          icon: "mdi-thumb-up",
          title: "Meeldinud videod",
          to: "/9",
        },
      ],
      subscriptions: [
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj",
          to: "/10",
          title: "Eesti Youtuberid",
        },
      ],
      moreItems: [
        {
          icon: "mdi-youtube",
          title: "Youtube Premium",
          to: "/12",
        },
        {
          icon: "mdi-youtube-gaming",
          title: "Mängud",
          to: "/13",
        },
        {
          icon: "mdi-access-point",
          title: "Otseülekanded",
          to: "/14",
        },
        {
          icon: "mdi-trophy",
          title: "Sport",
          to: "/15",
        },
      ],
      moreItems2: [
        {
          icon: "mdi-cog",
          title: "Seaded",
          to: "/16",
        },
        {
          icon: "mdi-flag",
          title: "Teadvituste ajalugu",
          to: "/17",
        },
        {
          icon: "mdi-help-circle",
          title: "Abi",
          to: "/18",
        },
        {
          icon: "mdi-message-alert",
          title: "Saada tagasisidet",
          to: "/19",
        },
      ],
      moreItems3: [
        {
          icon: "mdi-video-plus",
          to: "/20",
        },
        {
          icon: "mdi-apps",
          to: "/21",
        },
        {
          icon: "mdi-bell",
          to: "/22",
        },
      ],
      headerItems: [
        {
          icon: "mdi-video-plus",
          to: "/23",
        },
        {
          icon: "mdi-apps",
          to: "/23",
        },
        {
          icon: "mdi-bell",
          to: "/23",
        },
      ],
      miniVariant: false,
      right: true,
      title: "Youtube",
    };
  },
};
</script>
<style>
.v-navigation-drawer__content::-webkit-scrollbar {
  width: 8px;
  background-color: #212121;
}

.v-navigation-drawer__content::-webkit-scrollbar-thumb {
  background: #616161;
}
</style>

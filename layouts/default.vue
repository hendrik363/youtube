<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
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
      <v-divider/>
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
      <v-divider/>
      <v-subheader class="font-weight-bold py-4 subtitle-1">TELLIMUSED</v-subheader>
      <v-list>
        <v-list-item
          v-for="(item, i) in subscriptions"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-avatar>
            <v-img src="https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"></v-img>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
        
      </v-list>
      <v-divider/>
      <v-subheader class="font-weight-bold py-4 subtitle-1">ROHKEM YOUTUBE'IST</v-subheader>
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
      <v-divider/>
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
      <v-divider/>
      <div class="ml-6 mr-8 mt-2" style="letter">
          <a href="http://localhost:3000/" class="link mr-1 text--secondary caption">Teave</a>
          <a href="http://localhost:3000/" class="link mr-1 text--secondary caption">Press</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Autoriõigused</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Võtke meiega ühendust</a>
          <a href="http://localhost:3000/" class="link text--secondary mr-1 caption">Sisuloojad</a>
          <a href="http://localhost:3000/" class="link text--secondary mr-1 caption">Reklaam</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Arendajad</a>
        </div>
        <div class="ml-6 mr-8 mt-2">
          <a href="http://localhost:3000/" class="link text--secondary mr-1 caption">Tingimused</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Privaatsus</a>
          <a href="http://localhost:3000/" class="link text--secondary mr-9 caption">Eeskirjad ja ohutus</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Kuidas YouTube toimib?</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Proovige uusi funktsioone</a
          >
        </div>
        <p class="ml-6 mt-4 body-2 darken" style="color: #757575">© 2021 Google LLC</p>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <!-- <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn> -->
      <!-- <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn> -->
      <v-toolbar-title v-text="title" />
      <v-spacer />
       <!-- <v-text-field
        flat
        hide-details
        append-icon="mdi-magnify"
        placeholder="Search"
        outlined
        dense
        v-model="searchText"
        @click:append="search"
        class="hidden-sm-and-down"
      ></v-text-field>  -->
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <!-- <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
    </v-navigation-drawer> -->
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Avaleht',
          to: '/1'
        },
        {
          icon: 'mdi-youtube-subscription',
          title: 'Tellimused',
          to: '/2',
        }
        
        
      ],
      categoryItems: [
        {
          icon: 'mdi-play-box-multiple',
          title: 'Kogu',
          to: '/3',
        },
        {
          icon: 'mdi-history',
          title: 'Ajalugu',
          to: '/4',
        },
        {
          icon: 'mdi-play-box-outline',
          title: 'Teie videod',
          to: '/6',
        },
        {
          icon: 'mdi-clock',
          title: 'Hiljem vaatamiseks',
          to: '/7',
        },
        {
          icon: 'mdi-playlist-play',
          title: 'Lemmikud',
          to: '/8',
        },
        {
          icon: 'mdi-thumb-up',
          title: 'Meeldinud videod',
          to: '/9',
        }    
      ],
      subscriptions: [
        {
          icon: 'https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj',
          to: '/10',
          title: 'Eesti Youtuberid',

        },
      ],
      moreItems: [

        {
          icon: 'mdi-youtube',
          title: 'Youtube Premium',
          to: '/12'
        },
        {
          icon: 'mdi-youtube-gaming',
          title: 'Mängud',
          to: '/13',
        },
        {
          icon: 'mdi-access-point',
          title: 'Otseülekanded',
          to: '/14',
        },
        {
          icon: 'mdi-trophy',
          title: 'Sport',
          to: '/15',
        }
        
      ],
      moreItems2: [

        {
          icon: 'mdi-cog',
          title: 'Seaded',
          to: '/16'
        },
        {
          icon: 'mdi-flag',
          title: 'Teadvituste ajalugu',
          to: '/17',
        },
        {
          icon: 'mdi-help-circle',
          title: 'Abi',
          to: '/18',
        },
        {
          icon: 'mdi-message-alert',
          title: 'Saada tagasisidet',
          to: '/19',
        }
        
      ],
      miniVariant: false,
      right: true,
      title: 'Youtube'
    }
    
  }
}
</script>

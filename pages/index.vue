<template>
  <v-row>
      <v-col v-for="(video, n) in videos" :key="n" cols="3" class="mb-5 pl-8">
        <v-hover v-slot="{ hover }" open-delay="500">
          <div>
            <v-row dense
              ><v-img v-if="hover" :src="video.thumbnailwebp" contain></v-img>
              <v-img v-else :src="video.thumbnailjpg" contain></v-img>
            </v-row>
            <v-row class="mt-5" dense>
              <v-col :cols="2" class="pl-0 pr-0">
                <v-avatar size="40">
                  <v-img :src="video.avatar"></v-img> </v-avatar
              ></v-col>
              <v-col :cols="10" class="pl-0">
                <v-list-item-title style="white-space: pre-wrap; margin-bottom: -20px;" class="font-weight-bold"
                  >{{ video.title }}
                </v-list-item-title>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.channelName }}
                  <v-icon color="grey" size="14" class="ml-1">{{
                    "mdi-check-circle"
                  }}</v-icon>
                </v-list-item-subtitle>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.views }}
                  <v-icon color="grey" size="20" class="ml-0 mr-0">{{
                    "mdi-circle-small"
                  }}</v-icon>
                  {{ video.date }}
                </v-list-item-subtitle></v-col
              >
            </v-row>
          </div>
        </v-hover>
      </v-col>
    </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  data()
  {
    return {
          videos: [
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
                {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "PUID ALLA | Mis värk on selle iPhonega!?",
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: 'PUID ALLA | Mis värk on selle iPhonega!?',
          channelName: "Eesti Youtuberid",
          views: "33 tuh vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gdjTHi1_S-c/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLChRCrqix7WCnJ-IIBUk_dmhRBYTw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gdjTHi1_S-c/mqdefault_6s.webp?du=3000&sqp=CLmq9oIG&rs=AOn4CLBS5pzNf1a9uUfT6YcXxcfUbUKA-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngABIvlVpBRkH3JX46SLM6yHfzpDhwkwmo2sg4O=s88-c-k-c0x00ffffff-no-rj"
        }
      ]
      }
  },
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>

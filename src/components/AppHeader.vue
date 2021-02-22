<template lang="pug">
div

  v-navigation-drawer.hidden-sm-and-up(app v-model="drawer" absolute temporary)
    v-list(nav dense)
      v-list-item-group(v-model="group")
        v-list-item(v-for="item in appPages" :key="item.title + '-side-nav'")
          v-list-item-title {{item.title}}
  v-app-bar(app elevate-on-scroll scroll-target="" )
    v-app-bar-nav-icon.hidden-sm-and-up(@click="drawer = !drawer")
    v-toolbar-title {{appTitle}}
    v-spacer
    v-toolbar-items.hidden-xs-only
      v-btn(v-for="item in appPages" :key="item.title" text)
        v-icon(left dark) {{ item.icon }}
        p.mb-0 {{ item.title }}



</template>

<script>
export default {
  props: {
    appTitle: String
  },
  data(){
    return {
      drawer: false,
      group:false,
      appPages: [
        {
          title: 'Home',
          path: '/home',
          icon: 'mdi-home'
        },
        {
          title: 'About',
          path: '/about',
          icon: 'mdi-face-woman'
        },
        {
          title: 'Contact',
          path: '/contact',
          icon: 'mdi-account-box'
        }
      ]
    }
  }
}
</script>

<style lang="scss">

</style>
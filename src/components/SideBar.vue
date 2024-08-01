<template>
    <div id="sidebar">
      <v-app>
        <!-- vuetify side bar -->
        <v-navigation-drawer v-model="drawer" app permanent>
          <v-list>
            <!-- list-container: Title image and name -->
            <v-list-item class="title-container">
              <img src="../assets/Images/logo-light.png" alt="logo" class="sidebar-logo"/>
              <span><img src="../assets/Images/appname-light.png" alt="title" class="sidebar-title"/></span>
            </v-list-item>
          </v-list>

            <!-- list group ci=ontaining elements -->
          <v-list>
            <!-- using for loop fetch element array : title -->
            <v-list-group v-for="item in items" :key="item.title" value="true">
              <template v-slot:activator>
                <v-list-item link :class="{ 'active-item': activeItem === item.title }" @click="setActiveItem(item.title)">
                  <v-list-item-content>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </template>
            <!-- using for loop fetch element array : Sublinks with logo -->
              <v-list-item v-for="(subtitle, index) in item.subtitles" :key="index" link :class="{ 'active-item': activeItem === subtitle.text }" @click="setActiveItem(subtitle.text)">
                <v-list-item-icon class="sub-elements-dashboard">
                  <v-icon>{{ subtitle.icon }}</v-icon>
                  <v-list-item-subtitle>{{ subtitle.text }}</v-list-item-subtitle>
                </v-list-item-icon>
              </v-list-item>
            </v-list-group>
          </v-list>
        </v-navigation-drawer>
      </v-app>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        // initialize datas
        drawer: false,
        activeItem: null,
        // nested element array
        items: [
          {
            title: 'Dashboards',
            subtitles: [
              { text: 'E-Commerce', icon: 'mdi-home' },
            ],
          },
          {
            title: 'Apps',
            subtitles: [
              { text: 'Blog', icon: 'mdi-chat' },
              { text: 'Calendar', icon: 'mdi-calendar-blank-outline' },
              { text: 'Chat', icon: 'mdi-wechat' },
              { text: 'Files', icon: 'mdi-folder-outline' },
              { text: 'Mail', icon: 'mdi-email-outline' },
              { text: 'Task List', icon: 'mdi-checkbox-marked-outline' },
            ],
          },
          {
            title: 'UI kit',
            subtitles: [
              { text: 'Form Layout', icon: 'mdi-card-account-details-outline' },
              { text: 'Input', icon: 'mdi-checkbox-marked-outline' },
              { text: 'Float Label', icon: 'mdi-bookmark-outline' },
              { text: 'Invalid State', icon: 'mdi-alert-circle-outline' },
              { text: 'Button', icon: 'mdi-cube-outline' },
              { text: 'Table', icon: 'mdi-table' },
              { text: 'List', icon: 'mdi-format-list-bulleted' },
              { text: 'Tree', icon: 'mdi-share-variant-outline' },
              { text: 'Panel', icon: 'mdi-cellphone' },
              { text: 'Overlay', icon: 'mdi-content-copy' },
              { text: 'Media', icon: 'mdi-image-area' },
              { text: 'Menu', icon: 'mdi-menu' },
              { text: 'Message', icon: 'mdi-chat' },
              { text: 'File', icon: 'mdi-file-document-outline' },
              { text: 'Chart', icon: 'mdi-chart-bar' },
              { text: 'Misc', icon: 'mdi-circle-outline' },
            ],
          },
          {
            title: 'Prime Blocks',
            subtitles: [
              { text: 'Free Blocks', icon: 'mdi-eye-outline' },
              { text: 'All Blocks', icon: 'mdi-web' },
            ],
          },
          {
            title: 'Utilities',
            subtitles: [
              { text: 'Prime Icons', icon: 'mdi-emoticon-angry' },
              { text: 'Colors', icon: 'mdi-palette-outline' },
              { text: 'PrimeFlex', icon: 'mdi-television' },
              { text: 'Figma', icon: 'mdi-pencil-outline' },
            ],
          },
          {
            title: 'Pages',
            subtitles: [
              { text: 'Landing', icon: 'mdi-web' },
              { text: 'Auth', icon: 'mdi-account-outline' },
              { text: 'Crud', icon: 'mdi-pencil-outline' },
              { text: 'Timeline', icon: 'mdi-calendar-blank-outline' },
              { text: 'Invoice', icon: 'mdi-currency-usd' },
              { text: 'About Us', icon: 'mdi-account-outline' },
              { text: 'Help', icon: 'mdi-help-circle-outline' },
              { text: 'Not Found', icon: 'mdi-alert-circle-outline' },
              { text: 'Empty', icon: 'mdi-circle-outline' },
              { text: 'FAQ', icon: 'mdi-help' },
              { text: 'Contact Us', icon: 'mdi-phone' },
            ],
          },
          {
            title: 'E-Commerce',
            subtitles: [
              { text: 'Product Overview', icon: 'mdi-image-area' },
              { text: 'Product List', icon: 'mdi-menu' },
              { text: 'New Product', icon: 'mdi-plus' },
              { text: 'Shopping Cart', icon: 'mdi-cart-outline' },
              { text: 'Check Form', icon: 'mdi-checkbox-marked-outline' },
              { text: 'Order History', icon: 'mdi-history' },
              { text: 'Order Summary', icon: 'mdi-file' },
            ],
          },
          {
            title: 'User Management',
            subtitles: [
              { text: 'List', icon: 'mdi-menu' },
              { text: 'Create', icon: 'mdi-plus' },
            ],
          },
          {
            title: 'Hierarchy',
            subtitles: [
              { text: 'Submenu 1', icon: 'mdi-menu' },
              { text: 'Submenu 2', icon: 'mdi-menu' },
            ],
          },
          {
            title: 'Start',
            subtitles: [
              { text: 'Buy Now', icon: 'mdi-cart-outline' },
              { text: 'Documentation', icon: 'mdi-alert-circle-outline' },
            ],
          },
        ],
      };
    },
    // methods to maintain active class      
    methods: {
      setActiveItem(title) {
        this.activeItem = title;
      },
    },
  };
  </script>
  
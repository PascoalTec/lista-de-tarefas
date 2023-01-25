<template>
  <v-app id="inspire">

    <v-navigation-drawer
    v-model="drawer"
    app
    >
    <v-img
    src="./assets/bg.jpg"
    gradient="to top right, rgba(19,84,122,.5), rgba(28,108,199,.8)"
    dark
    class="pt-5 text-center"
    >
    <v-avatar
    size="100"
    >
      <img
        src="https://mail.google.com/mail/u/0?ui=2&ik=ba9bd541b8&attid=0.1&permmsgid=msg-a:r4528135427147176668&th=1846c8d71fe0df7c&view=fimg&realattid=1846c8ce818d198d6662&disp=thd&attbid=ANGjdJ945ZTHr99wmuzfBoRlO1KFXnsFXLzY5EgN8USHnk7CVvZ_sqYPQPyfmh8Qv2IMwn-paXn4uEhJRf6FirG2xqUhrR4_yhIaSVJ9o7cfYS4foLUiEN4p-SctSlU&ats=2524608000000&sz=w1920-h913"
        alt="John"
      >
    </v-avatar>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Vue.js
          </v-list-item-title>
          <v-list-item-subtitle>
            Lista de Tarefas
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-img>
      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      app
      prominent
      height="180"
      color="#fcb69f"
      dark
      src="./assets/bg.jpg"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(28,108,199,.8)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <center>
        <v-app-bar-title
        class="mt-2"
      >
        Title
        <inputTarefa />
        </v-app-bar-title>
      </center>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import inputTarefa from './components/inputTarefa.vue'

  export default {
  components: { inputTarefa },
    data: () => ({
            drawer: null,
            items: [
          { title: 'Tarefas', icon: 'mdi-view-dashboard', to:'/' },
          { title: 'Sobre', icon: 'mdi-help-box', to:'/sobre' },
        ]
     }),
  }
</script>

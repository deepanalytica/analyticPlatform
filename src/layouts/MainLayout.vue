<template>
 <q-layout view="lHh Lpr lff">
      <q-header elevated class="bg-cyan-8">
        <q-toolbar>
          <q-toolbar-title>Plataforma de Analítica de Datos Sociales, Económicos y Medioambientales</q-toolbar-title>
          <q-btn flat @click="drawer = !drawer" round dense icon="menu" />
        </q-toolbar>
      </q-header>

      <q-drawer
        v-model="drawer"
        show-if-above
        :width="200"
        :breakpoint="400"
      >
        <q-scroll-area style="height: calc(100% - 150px); margin-top: 150px; border-right: 1px solid #ddd">
          <q-list padding>
            <q-item clickable v-ripple to="/social" active-class="my-menu-link">
              <q-item-section avatar>
                <q-icon name="people" />
              </q-item-section>

              <q-item-section>
                Social
              </q-item-section>
            </q-item>

            <q-item active clickable v-ripple to="/economic" active-class="my-menu-link">
              <q-item-section avatar>
                <q-icon name="star" />
              </q-item-section>

              <q-item-section>
                Económico
              </q-item-section>
            </q-item>

            <q-item clickable v-ripple to="/medioambiental" active-class="my-menu-link">
              <q-item-section avatar>
                <q-icon name="water" />
              </q-item-section>

              <q-item-section>
                Medioambiental
              </q-item-section>
            </q-item>

            <q-item clickable v-ripple to="/surveys" active-class="my-menu-link">
              <q-item-section avatar>
                <q-icon name="mail" />
              </q-item-section>

              <q-item-section>
                Encuestas
              </q-item-section>
            </q-item>


          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="https://cdn.quasar.dev/img/material.png" style="height: 150px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png">
            </q-avatar>
            <div class="text-weight-bold">San Javier de Loncomilla</div>
            <div>@SanJavier</div>
          </div>
        </q-img>
      </q-drawer>

      <q-page-container>
        <router-view></router-view>>
      </q-page-container>
    </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const drawer = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      drawer
      }
  }
}
</script>

<style lang="scss">
.my-menu-link {
  color: white;
  background: #F2C037;
}

</style>

<template>
    <div>
        <v-layout row>
      <v-flex xs12 sm6 offset-sm3>
        <v-card height="200px">
          <v-card-title class="blue white--text">
            <span><v-icon>face</v-icon>จัดการข้อมูลยานพาหนะ</span>
            <v-spacer></v-spacer>
            <v-menu bottom left>
              <v-btn slot="activator" icon dark>
                <v-icon>more_vert</v-icon>
              </v-btn>
              <v-list>
                <v-list-tile v-for="(item, i) in items" :key="i">
                  <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile>
              </v-list>
            </v-menu>
          </v-card-title>
          
        </v-card>
      </v-flex>
    </v-layout>
        <nuxt/>
    </div>
</template>



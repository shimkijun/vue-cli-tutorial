<template>
  <div class="blue lighten-3 pa-8 ma-5">
    <h1>User 컴포넌트</h1>
    <p>이름: {{ name }} </p>
    <v-btn
        depressed
        small
        color="primary"
        @click="changeName"
    >
        이름 변경
    </v-btn>
    <v-container>
        <v-layout row wrap>
        <v-flex xs12 sm6>
            <UserDetail :nameOfChild="name"></UserDetail>
        </v-flex>
        <v-flex xs12 sm6>
            <UserEdit></UserEdit>
        </v-flex>
        </v-layout>
    </v-container>
  </div>
</template>

<script>
import UserDetail from './UserDetail.vue'
import UserEdit from './UserEdit.vue'

export default {
  components: {
    UserDetail,
    UserEdit
  },
  data () {
    return {
      name: 'Vue.js'
    }
  },
  methods: {
    changeName () {
      this.name = 'skj'
    }
  }
}
</script>

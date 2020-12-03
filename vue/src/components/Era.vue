<template>
  <div class="era">
    <div>
      <h1 class="title">EPL 20/21</h1>
    </div>
    <hr>

    <p>HongTen</p>

    <div>
      <ul v-for="(club, i) in clubs" :key="i" class="list-unstyled">
        <li>
          {{ i+1 }}. {{ club.name }} {{ club.stadium }}
        </li>
      </ul>
    </div>

  </div>
</template>


<script>
import axios from 'axios'
export default {
  name: 'Era',

  data() {
    return {
      title: 'club',
      clubs: []
    }
  },
  methods: {
    getTodos () {
        axios.get('http://localhost:28080/club')
        .then((res) => {
          this.clubs = res.data
        })
      },
    },
    mounted(){
      this.getTodos()
    }
  }
</script>

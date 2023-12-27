<template>
  <v-app>

    <v-app-bar :elevation="2" color="pink" app>
      <v-btn>
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-col>
          <h3>menu1</h3>
        </v-col>
        <v-col>
          <h3>menu2</h3>
        </v-col>
        <v-col>
          <h3>menu3</h3>
        </v-col>

    </v-app-bar>
    <v-main>
      <v-row>
        <v-col>
          <v-row >
            <v-col>
              <v-card color="pink">
                <h1>{{ todos.data_1 }}</h1>
              </v-card>
            </v-col>
            <v-col>
              <v-card color="pink">
                <h1>{{ todos.data_2 }}</h1>
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card color="pink">
                <h1>{{ todos.data_3 }}</h1>
              </v-card>
            </v-col>
            <v-col>
              <v-card color="pink">
                <h1>{{ todos.data_4 }}</h1>
              </v-card>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card color="pink">
                <h1>{{ todos.data_6 }}</h1>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
        <v-col>
          <v-card color="pink">
            <h1>{{ todos.data_5 }}</h1>
          </v-card>
        </v-col>

      </v-row>


    </v-main>





  </v-app>
</template>

<script>
import axios from "axios"

export default {
  name: 'Home',
  data: () => ({
    todos: {}
  }),
  mounted() {
    this.callapi()
  },
  methods: {
    callapi: function () {
      let config = {
        method: 'get',
        maxBodyLength: Infinity,
        url: 'https://demotrade.efintradeplus.com/ExamAPI/examdata',
        headers: {}
      };

      axios.request(config)
        .then((response) => {
          this.todos = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    }
  }
}
</script>

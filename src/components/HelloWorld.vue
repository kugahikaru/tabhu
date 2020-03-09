<template>
  <v-container fluid>
    <v-row class="text-center">
      <v-col class="mb-4">
        <v-row justify="center">
          <h1 class="display-2 font-weight-bold mb-3">
            TABHU
          </h1>
        </v-row>
        <v-row justify="center">
          <p>
            major: add 2     ex)CM7 ... cm72<br />
            aug  : add aug   ex)Caug ... caug<br />
            minorM7: add mm7 ex)CmM7 ... cmm7<br />
            flat: add b      ex)Cm7♭5 ... cm7b5<br />
            add: add add     ex)Cadd9 ... cadd9<br />
            sharp: add 3     ex)C#7 ...c37<br />
          </p>
        </v-row>
        <v-textarea
          outlined
          name="chords"
          label="Outlined textarea"
          v-model="chords"
          @keyup="createTabImg"
        >
        </v-textarea>
      </v-col>
    </v-row>
    <v-row>
      <v-col v-for="(chord, index) in chordsArray" v-bind:key="index">
        <v-card flat tile>
          <v-img
            v-if="chord"
            :src="'https://muuu.jp/images/' + chord + '-s.png'"
            max-width="240"
            max-height="180"
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return{
        chords: "",
        chordsArray: []
      }
    },
    methods: {
      createTabImg: function(){
        console.log(this.chords);
        this.chordsArray = this.chords.split(",");
      }
    }
  }
</script>

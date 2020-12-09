<template>
<v-container>
  <v-row>
    <no-ssr>
      <draggable class="row">
        <v-col md="3" cols="12">
          <v-card>
            <v-card-title>card 1</v-card-title>
            <v-card-text>I am 1</v-card-text>
          </v-card>
        </v-col>
        <v-col md="3" cols="12">
          <v-card>
            <v-card-title>card 2</v-card-title>
            <v-card-text>I am 2</v-card-text>
          </v-card>
        </v-col>
      </draggable>
    </no-ssr>
  </v-row>
</v-container>
</template>

<script>


export default {
  display: "Two Lists",
  order: 1,
  data:()=>({
    list1: [
      { name: "John", id: 1 },
      { name: "Joao", id: 2 },
      { name: "Jean", id: 3 },
      { name: "Gerard", id: 4 }
    ],
    list2: [
      { name: "Juan", id: 5 },
      { name: "Edgard", id: 6 },
      { name: "Johnson", id: 7 }
    ]
  }),
  methods:{
    add: function() {
      this.list.push({ name: "Juan" });
    },
    replace: function() {
      this.list = [{ name: "Edgard" }];
    },
    clone: function(el) {
      return {
        name: el.name + " cloned"
      };
    },
    log: function(evt) {
      window.console.log(evt);
    }
  }
}
</script>

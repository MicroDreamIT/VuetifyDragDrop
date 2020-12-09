<template>
<v-container>
  <v-row>
    <v-col md="3" cols="12">
      <no-ssr>
        <draggable @change="log" :list="list1" group="people">
          <v-card v-for="(item, index) in list1" :key="index" class="mb-4">
            <v-card-title>{{ item.title }}</v-card-title>
            <v-card-text>{{ item.content }}</v-card-text>
          </v-card>
        </draggable>
      </no-ssr>
    </v-col>
    <v-col md="3" cols="12">
      <no-ssr>
        <draggable @change="log" :list="list2" group="people">
          <v-card v-for="(item, index) in list2" :key="index" class="mb-4">
            <v-card-title>{{ item.title }}</v-card-title>
            <v-card-text>{{ item.content }}</v-card-text>
          </v-card>
        </draggable>
      </no-ssr>
    </v-col>
  </v-row>
</v-container>
</template>

<script>


export default {
  display: "Two Lists",
  order: 1,
  data:()=>({
    list1: [
      { title: "John", content:'hello John', id: 1 },
      { title: "Joao", content:'hello Joao', id: 2 },
      { title: "Jean", content:'hello Jean', id: 3 },
      { title: "Gerard", content:'hello Gerard', id: 4 }
    ],
    list2: [
      { title: "John2", content:'hello John', id: 5 },
      { title: "Joao2", content:'hello Joao', id: 6 },
      { title: "Jean2", content:'hello Jean', id: 7 },
      { title: "Gerard2", content:'hello Gerard', id: 8 }
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

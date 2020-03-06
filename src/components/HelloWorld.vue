<template>
  <div>
    <v-flex>
      <v-data-iterator
        content-tag="v-layout"
        content-props="row wrap"
        :items="productsList"
        :page.sync="page"
        :items-per-page="itemsPerPage"
        hide-default-footer
        :footer-props="{
        itemsPerPageOptions: rowsPerPageItems
      }"
        @page-count="pageCount = $event"
      >
        <v-flex slot="item" slot-scope="props">
          <v-card>
            <v-card-title>
              <h4>{{ props.item.first }}</h4>
            </v-card-title>
            <v-divider></v-divider>
            <v-list dense>
              <v-list-tile>
                <v-list-tile-content>Detalhe Produto:</v-list-tile-content>
                <v-list-tile-content class="align-end">{{ props.item.first }}</v-list-tile-content>
              </v-list-tile>
              <br />
              <v-list-tile>
                <v-list-tile-content>Valor Produto:</v-list-tile-content>
                <v-list-tile-content class="align-end">{{ props.item.second }}</v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-card>
        </v-flex>
      </v-data-iterator>
      <v-pagination v-model="page" :length="pageCount"></v-pagination>
    </v-flex>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    ecosystem: [
      {
        text: "vuetify-loader",
        href: "https://github.com/vuetifyjs/vuetify-loader"
      },
      {
        text: "github",
        href: "https://github.com/vuetifyjs/vuetify"
      },
      {
        text: "awesome-vuetify",
        href: "https://github.com/vuetifyjs/awesome-vuetify"
      }
    ],
    importantLinks: [
      {
        text: "Documentation",
        href: "https://vuetifyjs.com"
      },
      {
        text: "Chat",
        href: "https://community.vuetifyjs.com"
      },
      {
        text: "Made with Vuetify",
        href: "https://madewithvuejs.com/vuetify"
      },
      {
        text: "Twitter",
        href: "https://twitter.com/vuetifyjs"
      },
      {
        text: "Articles",
        href: "https://medium.com/vuetify"
      }
    ],
    whatsNext: [
      {
        text: "Explore components",
        href: "https://vuetifyjs.com/components/api-explorer"
      },
      {
        text: "Select a layout",
        href: "https://vuetifyjs.com/layout/pre-defined"
      },
      {
        text: "Frequently Asked Questions",
        href: "https://vuetifyjs.com/getting-started/frequently-asked-questions"
      }
    ],
    page: 1,
    pageCount: 0,
    itemsPerPage: 2,
    rowsPerPageItems: [1, 2, 3],
    pagination: {
      rowsPerPage: 1,
      totalItems: 6
    },
    headers: [
      {
        text: "First collumn",
        align: "start",
        sortable: false,
        value: "first"
      },
      {
        text: "Second collumn",
        align: "start",
        sortable: false,
        value: "second"
      }
    ],
    productsList: [
      {
        first: "Produto 1",
        second: 1
      },
      {
        first: "Produto 2",
        second: 2
      },
      {
        first: "Produto 3",
        second: 3
      },
      {
        first: "Produto 4",
        second: 4
      },
      {
        first: "Produto 5",
        second: 5
      },
      {
        first: "Produto 6",
        second: 6
      }
    ]
  })
};
</script>

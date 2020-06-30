<template>
  <div style="max-width: 800px;">
    <v-text-field
      label="コメント"
      placeholder="ここにコメントを書きましょう"
      outlined
      class="mx-auto"
      append-icon="mdi-check-bold"
      style="max-width: 100%; box-sizing: border-box;"
    ></v-text-field>

    <v-card v-for="(item, index) in items" :key="index" tile>
      <v-list-item two-line>
        <v-list-item-content>
          <v-list-item-title>{{ item.comment }}</v-list-item-title>
          <v-list-item-subtitle>by: {{ item.owner }}</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-card>
  </div>
</template>
<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

interface Item {
  comment: string,
  owner: string
}
interface Form {
  comment: string
}


@Component
export default class MyComponent extends Vue {
  name:string = 'ChatComponent'
  items: Item[] = []
  form: Form = {
    comment: ''
  }

  getChatList(): void {
    // コメント取得
    this.items = [
      {
        comment: 'ここにコメントが入ります',
        owner: 'ここに投稿者名が入ります',
      },
      {
        comment: 'ここにコメントが入ります',
        owner: 'ここに投稿者名が入ります',
      },
      {
        comment: 'ここにコメントが入ります',
        owner: 'ここに投稿者名が入ります',
      },
    ]
  }
  
  created() {
    this.getChatList()
  }
}
</script>

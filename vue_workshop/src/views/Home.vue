<template>
  <div class="home">
    <!--    <h1>Hello, <span :class="{'hello': clickCount % 5 === 0}">{{ name }}</span>!</h1>-->
    <!--    <input v-model="name">-->
    <!--    <button @click="clickCount++"> {{ getButtonLabel() }}</button>-->
    <!---->
    <!--    <div v-for="(item, index) in itemList" :key="item.label">-->
    <!--      <p>{{index + 1}}. Sina ostsid poest {{ item.label.toLowerCase() }}, mis maksis {{item.cost}} euri.</p>-->
    <!--    </div>-->
    <input v-model="itemLabel">
    <button @click="addItemToList">Lisa item!</button>

    <table>
      <thead>
      <tr>
        <th>#</th>
        <th>Mis?</th>
      </tr>
      </thead>

      <tbody>
        <tr v-for="(name, index) in todoItems" :key="index">
          <td>{{index + 1}}</td>
          <td>{{name}}</td>
          <button @click="removeItemFromList(index)">X</button>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  // name: 'Home',
  // data () {
  //   return {
  //     name: 'Ann',
  //     clickCount: 0,
  //     itemList: [
  //       {
  //         label: 'toit',
  //         cost: 5
  //       },
  //       {
  //         label: 'jook',
  //         cost: 10
  //       },
  //       {
  //         label: 'tip',
  //         cost: 200
  //       }
  //     ]
  //   }
  // },
  // methods: {
  //   getButtonLabel () {
  //     if (this.clickCount === 1) return `I have been clicked ${this.clickCount} time`
  //     else return `I have been clicked ${this.clickCount} times`
  //   }
  // }
  name: 'Home',
  data () {
    return {
      todoItems: [],
      itemLabel: ''
    }
  },
  methods: {
    addItemToList () {
      this.todoItems.push(this.itemLabel)
      this.itemLabel = ''
    },
    removeItemFromList (index) {
      this.todoItems.splice(index, 1)
    }
  }
}
</script>

<style scoped>
 .hello {
   color: red;
 }
</style>

<template>
  <div>
    <div class="scroll-btns-container">
      <div class="scroll-btns-wrapper">
        <b-btn variant="primary" @click="scrollLeft">
          Left
        </b-btn>
        <b-btn variant="primary" class="float-right" @click="scrollRight">
          Right
        </b-btn>
      </div>
    </div>
    <b-table
        borderless
        dark
        class="styled-table"
        :fields="dataTable.fields"
        :items="dataTable.items"
        :responsive="true"
        :sticky-header="stickyHeader">
      <template v-slot:head(row)="row">
        <div class="row-head-container">
          {{ row.label }}
        </div>
      </template>

      <template v-slot:cell(row)="row">
        <div :class="['row-cell-container', row.item.fake_row ? 'fake-row' : '']">
          {{ row.item.row }}
        </div>
      </template>

      <template v-slot:head()="row">
        <div class="head-container">
          {{ row.label }}
        </div>
      </template>

      <template v-slot:cell(column_1)="row">
        <div class="cell-container">
          {{ row.item.column_1 }}
        </div>
      </template>

      <template v-slot:cell(column_2)="row">
        <div class="cell-container">
          {{ row.item.column_2 }}
        </div>
      </template>

      <template v-slot:cell(column_3)="row">
        <div class="cell-container">
          {{ row.item.column_3 }}
        </div>
      </template>

      <template v-slot:cell(column_4)="row">
        <div class="cell-container">
          {{ row.item.column_4 }}
        </div>
      </template>

      <template v-slot:cell(column_5)="row">
        <div class="cell-container">
          {{ row.item.column_5 }}
        </div>
      </template>

      <template v-slot:cell(column_6)="row">
        <div class="cell-container">
          {{ row.item.column_6 }}
        </div>
      </template>

      <template v-slot:cell(column_7)="row">
        <div class="cell-container">
          {{ row.item.column_7 }}
        </div>
      </template>

      <template v-slot:cell(column_8)="row">
        <div class="cell-container">
          {{ row.item.column_8 }}
        </div>
      </template>

      <template v-slot:cell(column_9)="row">
        <div class="cell-container">
          {{ row.item.column_9 }}
        </div>
      </template>

      <template v-slot:cell(column_10)="row">
        <div class="cell-container">
          {{ row.item.column_10 }}
        </div>
      </template>
    </b-table>
  </div>
</template>

<script>
export default {
  name: 'Table',
  props: {
    stickyHeader: {
      type: Boolean,
      default: false
    },
    observer: {
      type: IntersectionObserver,
      default: null
    }
  },
  data() {
    return {
      dataTable: {
        fields: [
          {
            key: 'row',
            label: 'row name',
            stickyColumn: true
          },
          {
            key: 'column_1',
            label: 'column 1'
          },
          {
            key: 'column_2',
            label: 'column 2'
          },
          {
            key: 'column_3',
            label: 'column 3'
          },
          {
            key: 'column_4',
            label: 'column 4'
          },
          {
            key: 'column_5',
            label: 'column 5'
          },
          {
            key: 'column_6',
            label: 'column 6'
          },
          {
            key: 'column_7',
            label: 'column 7'
          },
          {
            key: 'column_8',
            label: 'column 8'
          },
          {
            key: 'column_9',
            label: 'column 9'
          },
          {
            key: 'column_10',
            label: 'column 10'
          }
        ],
        items: [
          {
            'row': '',
            'column_1': '',
            'column_2': '',
            'column_3': '',
            'column_4': '',
            'column_5': '',
            'column_6': '',
            'column_7': '',
            'column_8': '',
            'column_9': '',
            'column_10': '',
            'fake_row': true
          },
          {
            'row': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Excepteur sint occaecat cupidatat non proident.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Excepteur sint occaecat cupidatat non proident.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Excepteur sint occaecat cupidatat non proident.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Excepteur sint occaecat cupidatat non proident.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Excepteur sint occaecat cupidatat non proident.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Excepteur sint occaecat cupidatat non proident.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          },
          {
            'row': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem.',
            'column_1': 'value 1',
            'column_2': 'value 2',
            'column_3': 'value 3',
            'column_4': 'value 4',
            'column_5': 'value 5',
            'column_6': 'value 6',
            'column_7': 'value 7',
            'column_8': 'value 8',
            'column_9': 'value 9',
            'column_10': 'value 10'
          }
        ]
      }
    }
  },
  mounted() {
    this.observer.observe(document.querySelector('.fake-row'));
  },
  methods: {
    scrollLeft() {
      let content = document.querySelector(".table-responsive");
      content.scrollLeft -= 224;
    },
    scrollRight() {
      let content = document.querySelector(".table-responsive");
      content.scrollLeft += 224;
    }
  }
}
</script>

<style lang="scss">
.b-table-sticky-header, .table-responsive, [class*=table-responsive-]
{
  margin-bottom: 0;
  scroll-behavior: smooth;
}
.row-head-container
{
  display: block;
  background-color: #E5E5EB;
  width: 300px;
  height: 50px;
  position: relative;
  margin: 0;
  padding: 0;
  border: 1px solid #C4C9CC;
  border-radius: 4px;
  box-sizing: border-box;

  color: #000000;
}
.row-cell-container
{
  display: block;
  background-color: transparent;
  width: 300px;
  height: auto;
  position: relative;
  margin: 0;
  padding: 0;
}
.head-container
{
  display: block;
  background-color: #E5E5EB;
  width: 200px;
  height: 50px;
  position: relative;
  margin: 0;
  padding: 0;
  border: 1px solid #C4C9CC;
  border-radius: 4px;
  box-sizing: border-box;

  color: #000000;
}
.cell-container
{
  display: block;
  background-color: transparent;
  width: 200px;
  height: 50px;
  position: relative;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.scroll-btns-container
{
  display: block;
  width: 100%;
  height: 0;
  position: relative;
  margin: 0;
  padding: 0 15px 0 315px;
  box-sizing: border-box;
  z-index: 100;
}
.scroll-btns-wrapper
{
  display: inline-block;
  background-color: transparent;
  width: 100%;
  height: 0;
  position: relative;
  margin: 0;
  padding: 10px 0 0 0;
}
</style>
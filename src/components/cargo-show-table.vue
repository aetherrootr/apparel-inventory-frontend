<template>
  <perfect-scrollbar style="max-height: calc(30vh);">
    <n-data-table 
      ref="table"
      :columns="columns" 
      :data="data" 
      :pagination="pagination"
      :row-key="row => row.id"
      @update:checked-row-keys="handleCheck" 
    />
  </perfect-scrollbar>
</template>

<script>
  import { defineComponent } from 'vue'
  import {
    NDataTable,
  } from 'naive-ui'
  import {PerfectScrollbar} from 'vue3-perfect-scrollbar'

  const createColumns = () => {
    return [
      {
        title: '货物编号',
        key: 'id'
      },
      {
        title: '货物名称',
        key: 'name'
      },
      {
        title: '颜色',
        key: 'color'
      },
      {
        title: '材质',
        key: 'material'
      },
      {
        title: '尺寸',
        key: 'size'
      },
      {
        title: '出厂价格',
        key: 'exfactoryprice'
      },
      {
        title: '零售价格',
        key: 'retailprice'
      },
      {
        title: '生产厂家',
        key: 'manufacturer'
      },
      {
        title: '货物数量',
        key: 'count'
      },
    ]
  }

  export default defineComponent({
    components: {
      NDataTable,
      PerfectScrollbar
    },
    props: {
      data: Array,
    },
    data () {
      return {
        pagination: {
          pageSize: 15
        },
        columns: createColumns(),
        checkedRowKeys: [],
        insertcargo:{
          name: ''
        },
        showModal: false,
      }
    },
  })
</script>

<style src="vue3-perfect-scrollbar/dist/vue3-perfect-scrollbar.css"></style>
<template>
  <div style="width: 600px">
    <vue-table-dynamic 
      :params="params"
      @cell-change="onCellChange"
      @select="onSelect"
      @selection-change="onSelectionChange"
      ref="table"
    >
    </vue-table-dynamic>
    <button v-on:click="add_clean_line"> добавить данные </button>
    <button v-on:click="delete_line"> удалить данные </button>
      <button v-on:click="GetAllData"> все данные </button>

  </div>
</template>

<script>
import VueTableDynamic from 'vue-table-dynamic'
export default {
  name: 'Demo',
  data() {
    return {

      params: {
<<<<<<< HEAD
        data: [
          ['Дата', 'таск', 'статус'],
          [10.02, 'Купить хлеба', '4'],
          [10.02, 'Построить реактор', '1'],
          [10.02, 'Захватить мир', '404']
=======
      check_tmp: [],
      data: [
          ['id','Дата', 'таск', 'статус',],
          ['1',10.02, 'Купить хлеба', '2'],
          ['2',10.02, 'Построить реактор', '1',],
          ['3',10.02, 'Захватить мир', '404', ]
>>>>>>> 8f3bbe0ea592e8cb87ff5715e9404773e9253f41
        ],
        header: 'row',
        showCheck: true,
        edit: {
          row: [1],
          column: [1],
          cell: [[-1, -1]]
        }
      }
    }
  },
  methods: {
    onCellChange (rowIndex, columnIndex, data) {
      console.log('onCellChange: ', rowIndex, columnIndex, data)
      console.log('table data: ', this.$refs.table.getData())

    },
    add_clean_line(){
        this.params.data.push(['id','date', 'task', 'status',])
    },
     onSelectionChange (checkedDatas, ) {
          console.log('onSelectionChange: ', checkedDatas)

           for(var i = 0; i < checkedDatas.length;i++){

         this.params.check_tmp.push(checkedDatas[i][0])
           }




        },
        GetAllData(){
        console.log(this.params.check_tmp)

        },
        delete_line(){
        for(var i = 1;i < this.params.check_tmp.length;i++){
            this.params.data.splice(i,i)
        }
        this.params.check_tmp = []
        },






  },
  components: { VueTableDynamic }
}
</script>
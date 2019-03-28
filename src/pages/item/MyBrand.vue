<template>
    <div>
      <v-data-table
        :headers="headers"
        :items="brand"
        :pagination.sync="pagination"
        :total-items="totalBrands"
        :loading="loading"
        class="elevation-1"
      >
        <template slot="items" slot-scope="props">
          <td class="text-xs-center">{{ props.item.id }}</td>
          <td class="text-xs-center">{{ props.item.name}}</td>
          <td class="text-xs-center">{{ props.item.image }}</td>
          <td class="text-xs-center">{{ props.item.letter}}</td>
        </template>
      </v-data-table>
    </div>
</template>

<script>
    export default {
        name: "MyBrand",
      data(){
          return{
            headers:[
              {text:"品牌id",value:"id",align:'center',sortable:true},
              {text:"品牌名称",value:"name",align:'center',sortable:false},
              {text:"品牌LOGO",value:"image",align:'center',sortable:false},
              {text:"品牌首字母",value:"letter",align:'center',sortable:true}
            ],
            brands:[],
            pagination:{},
            totalBrands:0,
            loading:false
          }
      },
      created(){
          this.brand=[
            {id:2032,name:"OPPO",image:"1.jpg",letter:"O"},
            {id:2032,name:"飞利浦",image:"2.jpg",letter:"F"},
            {id:2032,name:"华为",image:"3.jpg",letter:"H"},
            {id:2032,name:"酷派",image:"4.jpg",letter:"K"},
            {id:2032,name:"魅族",image:"5.jpg",letter:"M"}
          ];
          this.totalBrands=15;
      }
    }
</script>

<style scoped>

</style>

<template>
  <div>
      <Table :columns="father.columns" border :data="father.data" :disabled-hover="true">
          <template slot-scope="{ row }" slot="slot-menuController" >
              <strong>{{row.menu}}</strong>
          </template>
          <template slot-scope="{ index }" slot="slot-menuSub" >
              <CustomShowModify v-model="father.data[index].subMenu" ></CustomShowModify>
          </template>

      </Table>
  </div>

</template>

<script>
	export default {
		name: "one",
        data(){
              return {
                  father:{
                      columns:[
                          {title:'类目',slot:"slot-menuController",maxWidth:200,align:'center'},
                          {title:'授权项目',slot:"slot-menuSub",align:'center', },
                      ],
                      data:[
                          {menu:'充值分析',subMenu:[
                                  ['/data/game/payer','物品货币',false],
                                  ['/data/game/payer','商城分析',true],
                                  ['/data/game/money','回本分析',true],
                              ]
                          },

                          {menu:'详细日志',subMenu:[['/data/log/daily','充值日志',true]]},

                      ],
                  },
                  abc:'11111',
                  switch1:true,
          }
        },
	}
</script>

<style scoped>

</style>

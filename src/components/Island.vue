// eslint-disable-next-line vue/valid-template-root
<template>
    <div>
        <table class="table is-bordered is-narrow is-hoverable is-fullwidth island">
        <thead></thead>
        <tbody>
            <!-- ひな壇の席 -->
            <tr>
                <td colspan=2 v-if="myData[0] != null">
                    <!-- 表示する情報が存在する場合 -->
                    <Desk v-bind:item="myData[0]"></Desk>
                </td>
                <td colspan=2 v-else style="border: 0px none;">
                    <!-- 在籍者なしのため、ボーダーを消去-->
                </td>
            </tr>
            <!-- 座席２列４席 -->
            <tr>
                <td ><Desk v-bind:item="myData[1]"></Desk></td>
                <td ><Desk v-bind:item="myData[2]"></Desk></td>
            </tr>
            <tr>
                <td ><Desk v-bind:item="myData[3]"></Desk></td>
                <td ><Desk v-bind:item="myData[4]"></Desk></td>
            </tr>
            <tr>
                <td ><Desk v-bind:item="myData[5]"></Desk></td>
                <td ><Desk v-bind:item="myData[6]"></Desk></td>
            </tr>
            <tr>
                <td><Desk v-bind:item="myData[7]"></Desk></td>
                <td><Desk v-bind:item="myData[8]"></Desk></td>
            </tr>
        </tbody>
        </table>
    </div>
</template>

<script>

import Desk from './Desk.vue'

export default {
  name: 'Island',
  data: function(){
      return {
        myData: null
      }
  },
  props: {
    'info': {
        default:null
    },
    'ids': {
        default: null
    }
  },
    created: function(){
        fetch('http://41-kbs218vm/api/wb/' + this.ids)
        .then( Response =>{
            return Response.json()
        })
        .then( json => {
            //this.myData = json
            this.myData = Array(9);     //9つの配列を確保する
            for (let i =0; i < json.length; i++){
                if(json[i].seq.length==5){
                    let index = parseInt(json[i].seq.substr(3,2),10);
                    if(index >=0 && index < this.myData.length){
                        this.myData[index] = json[i];
                    }
                }   
            }
        })
        .catch( error => {
            this.error = error
        });
    },
  components: {
    Desk
  }
}
</script>
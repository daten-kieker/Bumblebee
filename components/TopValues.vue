<template>
  <div>

    <h3>Top values</h3>
    <table class="table">
      <!-- <thead>
      <tr>
        <th>Value</th>
        <th>Count</th>
      </tr>
      </thead> -->
      <tbody>
      <tr v-for="(item, index) in values" :key="index">
        <td style="width:80%;" > <div class="top-bar" :style="{'width': normVal(item.count)+'%'  }"> <p>{{ item.value | varCheck}}</p> </div> </td>
        <td style="width:20%;" >{{ item.count | varCheck }}</td>
      </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
  export default {

    props: ['values', 'total'],

    data() {
      return {}
    },

    methods:{
      normVal(val) {
        return ((val * 100) / this.total);
      }
    }

  }

</script>

<style lang="scss" scoped>

  .top-bar{
    background-color: #4db6ac;
    position: relative;
    height: 100%;
    p{
      position: absolute;
      top: 0;
      left: 0;
      width: max-content;
    }
  }

  // sidechart
  .sidechart {
    margin-bottom: 5px;
    position: relative;
    font-size: 10px;

    &:hover {
      background-color: rgba(235, 235, 235, 0.527);
    }

    .bartext {
      background-color: #aeccde;
      width: 50%;
    }

    .totaltext {
      position: absolute;
      top: 0;
      left: 50%;
    }

    .counttext {
      position: absolute;
      top: 0;
      left: 30%;
    }

  }

  thead{
		tr{
			height: 25px !important;
		}
  }

  tr{
    border-bottom: 2px solid transparent !important;
    th{
      color: rgba(0, 0, 0, 1) !important;
      border-bottom: 2px solid transparent !important;
    }
    td{
      height: 15px !important;
      font-size: 11px !important;
    }

    &:hover{
      .top-bar{
        background-color: #3c948b;
      }
    }
  }


</style>

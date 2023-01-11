<template lang="">
  <div class="content-wrapper">
    <div class="container-fluid">
<div class="row">
<div class="col-12">
<div class="callout callout-info">
<h5><i class="fas fa-info"></i> Note:</h5>
This page has been enhanced for printing. Click the print button at the bottom of the invoice to test.
</div>

<div class="invoice p-3 mb-3">

<div class="row">

    <div class="row invoice-info">

<div class="col-sm-4 invoice-col">

<b>Order ID:</b> {{order_id}}<br>
<b>Order Date:</b> 2/22/2014<br>
<b>Account:</b> 968-34567<br>
</div>
<div class="col-sm-4 invoice-col">
From
<input v-model="order_starting_date" data-provide="datepicker">
</div>

<div class="col-sm-4 invoice-col">
To
<input v-model="order_ending_date" data-provide="datepicker">
</div>


</div>
</div>




<div class="row">
<div class="col-12 table-responsive">
<table class="table table-striped">
    <thead>
<tr>

<th colspan="1">Product</th>
<th class="table-secondary" colspan="2" style="horizontal-align : middle;text-align:center; ">Monday</th>
<th class="table-secondary" colspan="2" style="horizontal-align : middle;text-align:center; ">Tuesday</th>
<th class="table-secondary"  colspan="2" style="horizontal-align : middle;text-align:center; ">Wednesday</th>
<th class="table-secondary"  colspan="2" style="horizontal-align : middle;text-align:center; ">Thursday</th>
<th  class="table-secondary" colspan="2" style="horizontal-align : middle;text-align:center; ">Friday</th>
<th  class="table-secondary" colspan="2" style="horizontal-align : middle;text-align:center; ">Saturday</th>

</tr>
<tr >

<th></th>
<th class="table-warning" scope="col" style="horizontal-align : middle;text-align:center;">Req Qty</th>
<th class="table-danger" scope="col" style="horizontal-align : middle;text-align:center;">Avl  Qty</th>
<th class="table-warning" scope="col" style="horizontal-align : middle;text-align:center;">Req Qty</th>
<th class="table-danger" scope="col" style="horizontal-align : middle;text-align:center;">Avl  Qty</th>
<th class="table-warning" scope="col" style="horizontal-align : middle;text-align:center;">Req Qty</th>
<th class="table-danger" scope="col" style="horizontal-align : middle;text-align:center;">Avl  Qty</th>
<th  class="table-warning" scope="col" style="horizontal-align : middle;text-align:center;">Req Qty</th>
<th class="table-danger" scope="col" style="horizontal-align : middle;text-align:center;">Avl  Qty</th>
<th class="table-warning" scope="col" style="horizontal-align : middle;text-align:center;">Req Qty</th>
<th class="table-danger" scope="col" style="horizontal-align : middle;text-align:center;">Avl  Qty</th>
<th class="table-warning" scope="col" style="horizontal-align : middle;text-align:center;">Req Qty</th>
<th class="table-danger" scope="col" style="horizontal-align : middle;text-align:center;">Avl  Qty</th>
<th ></th>
</tr>
</thead>

<tbody>
<tr v-for="item,index in form" :key="item">

<td style="horizontal-align : middle;text-align:center;"><input type="text" class="form-control" v-model="item.produce_name"></td>
<td style="horizontal-align : middle;text-align:center;"><input v-model="item.mon_order" class="form-control" type="number" /></td>
<td style="horizontal-align : middle;text-align:center;"><input type="number" v-model="item.mon_avl_qty" class="form-control" disabled > </td>
<td style="horizontal-align : middle;text-align:center;"><input v-model="item.tue_order" class="form-control" type="number" /></td>
<td style="horizontal-align : middle;text-align:center;"><input type="number" v-model="item.tue_avl_qty" class="form-control" disabled> </td>
<td style="horizontal-align : middle;text-align:center;"><input v-model="item.wed_order" class="form-control" type="number" /></td>
<td style="horizontal-align : middle;text-align:center;"><input type="number" v-model="item.wed_avl_qty" class="form-control" disabled> </td>
<td style="horizontal-align : middle;text-align:center;"><input v-model="item.thu_order" class="form-control" type="number" /></td>
<td style="horizontal-align : middle;text-align:center;"><input type="number" v-model="item.thu_avl_qty" class="form-control" disabled> </td>
<td style="horizontal-align : middle;text-align:center;"><input v-model="item.fri_order" class="form-control" type="number" /></td>
<td style="horizontal-align : middle;text-align:center;"><input type="number" v-model="item.fri_avl_qty" class="form-control" disabled> </td>
<td style="horizontal-align : middle;text-align:center;"><input v-model="item.sat_order" class="form-control" type="number" /></td>
<td style="horizontal-align : middle;text-align:center;"><input type="number" v-model="item.sat_avl_qty" class="form-control" disabled> </td>
<td>    <button type="button" class="btn btn-danger btn-sm" @click="removeRow(index)">X</button></td>


</tr>

</tbody>
</table>
</div>

</div>

<div class="row">

<div class="col-6">
<p class="lead">Order Instructions:</p>
<i class="fa fa-cc-visa" aria-hidden="true"></i>
<i class="fa fa-cc-visa" aria-hidden="true"></i>
<i class="fa fa-cc-visa" aria-hidden="true"></i>
<i class="fa fa-cc-visa" aria-hidden="true"></i>

<div class="form-group">
<label>Textarea</label>
<textarea class="form-control" rows="3" placeholder="Enter ..." data-dashlane-rid="b0a2a52f21d5461a" data-form-type="other"></textarea>
</div>
</div>

<div class="col-6">
<p class="lead">Amount Due 2/22/2014</p>
<div class="table-responsive">
<table class="table">
<tbody><tr>
<th style="width:50%">Subtotal:</th>
<td>$250.30</td>
</tr>
<tr>
<th>Tax (9.3%)</th>
<td>$10.34</td>
</tr>
<tr>
<th>Shipping:</th>
<td>$5.80</td>
</tr>
<tr>
<th>Total:</th>
<td>$265.24</td>
</tr>
</tbody></table>
</div>
</div>

</div>


<div class="row no-print">
<div class="col-12">

<button type="button" class="btn btn-success float-right"><i class="far fa-credit-card"></i> Submit
Order
</button>
<button  @click="saveOrder()" type="button" class="btn btn-primary float-right" style="margin-right: 5px;">
<i class="fas fa-download"></i>Save Order
</button>
</div>
</div>
</div>

</div>
</div>
</div>

</div>
</template>


<script>
import { ref } from 'vue'

export default {
  name: 'OrderForm',
    data(){
        return{
          form:ref([{produce_name:'',mon_order:0,tue_order:0,wed_order:0,thu_order:0,fri_order:0,sat_order:0}])
          ,
          order_id:'',
          order_starting_date:'',
          order_ending_date:''
        }
    }
    ,
    methods:{
        async getsupply(){
            let res = await this.$frappe.getSuppllayBalance()
            console.log(res.data.message)
            let data = res.data.message
            this.form = []
            data.forEach(element => {
                this.form.push({
                    produce_name:element.produce_name,mon_order:0,
                    mon_avl_qty:element.mon_avl_qty,
                    tue_order:0,
                    tue_avl_qty:element.tue_avl_qty,
                    wed_order:0,
                    wed_avl_qty:element.wed_avl_qty,
                    thu_order:0,
                    thu_avl_qty:element.thu_avl_qty,
                    fri_order:0,
                    fri_avl_qty:element.fri_avl_qty,
                    sat_order:0,
                    sat_avl_qty:element.sat_avl_qty
                })
            });
            
        },
        async createOrder(){
        this.userData = this.$sessionUserData()
        console.log(this.userData.name)
      let body = {
        "docstatus": 0,
        "customer": this.userData.name,
      }
      let create_order = await this.$frappe.new_doc('Orders',body);
      let data = create_order.data.data
      this.order_id = data.name
      this.order_starting_date = data.order_starting_date
      this.order_ending_date = data.order_ending_date
      console.log(data)
      console.log(data)
      this.orderData = data

    },
        async saveOrder(){
        console.log(this.form)

        let child_table = []

        // how to write foreach loop in vue js
        this.form.forEach((item,index) => {
          console.log(item)
          console.log(index)
          let child_data = {"produce_name":'',"monday_order":'',"tuesday_order":'',"wednesday_order":'',"thursday_order":'',"friday_order":'',"saturday_order":''}
            child_data.produce_name = item.produce_name
            child_data.monday_order = item.mon_order
            child_data.tuesday_order = item.tue_order
            child_data.wednesday_order = item.wed_order
            child_data.thursday_order = item.thu_order
            child_data.friday_order = item.fri_order
            child_data.saturday_order = item.sat_order
            child_table.push(child_data)

        
          
        })
        console.log("test",child_table)
  
      let body = {
        "docstatus": 0,
        "order_items_deatils": child_table
      }
      let save_order = await this.$frappe.update_doc('Orders',this.order_id,body);
      let data = save_order.status_code
        console.log(data)
        if(data == 200){
          this.$popIt.success('Success','Order Saved Successfully')
        }
        else{
          this.$popIt.error('Error!','Order Not Saved')
        }
    },//end of save order
        addRow(index){
        this.form.push({produce_name:'tesst'})
        },
        removeRow(index){
            if(this.form.length > 1){
        this.form.splice(index,1)
      }
        }
    },
    mounted() {
        this.getsupply()
        this.createOrder()
    },
}
</script>

<style lang="">
    
</style>
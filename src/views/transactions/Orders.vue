<template>
    <div class="content-wrapper"> 
    
        <div class="card">
<div class="card-header">
<h3 class="card-title">Orders</h3>
<div class="card-tools">
<button type="button" class="btn btn-tool" data-card-widget="collapse" title="Collapse">
<i class="fas fa-minus"></i>
</button>
<button type="button" class="btn btn-tool" data-card-widget="remove" title="Remove">
<i class="fas fa-times"></i>
</button>
</div>
</div>
<div class="card-body p-0">
<table class="table table-striped projects">
<thead>
<tr>
<th style="width: 1%">
#
</th>
<th style="width: 20%">
Order Name
</th>
<th style="width: 30%">
Order Item Details
</th>
<th>
Order Progress
</th>
<th style="width: 8%" class="text-center">
Status
</th>
<th style="width: 20%">
</th>
</tr>
</thead>
<tbody>

<tr>
<td>
#
</td>
<td>
<a>
AdminLTE v3
</a>
<br>
<small>
Created 01.01.2019
</small>
</td>
<td>
<ul class="list-inline">
<li class="list-inline-item">
  <i class="fa fa-user"></i>
</li>
<li class="list-inline-item">
    <i class="fa fa-user"></i>
</li>
<li class="list-inline-item">
    <i class="fa fa-user"></i>
</li>
<li class="list-inline-item">
    <i class="fa fa-user"></i>
</li>
</ul>
</td>
<td class="project_progress">
<div class="progress progress-sm">
<div class="progress-bar bg-green" role="progressbar" aria-valuenow="77" aria-valuemin="0" aria-valuemax="100" style="width: 77%">
</div>
</div>
<small>
77% Complete
</small>
</td>
<td class="project-state">
<span class="badge badge-success">Success</span>
</td>
<td class="project-actions text-right">
<a class="btn btn-primary btn-sm" href="#">
<i class="fas fa-folder">
</i>
View
</a>


</td>
</tr>
</tbody>
</table>
</div>

</div>
     </div>
</template>



<script>
   

    export default {
        'name': 'Orders',
        data(){
            return {
                title: 'My Orders',
                detailUrl: '/my-orders/',

            }
        },
        methods: {
            async fetchOrders(){
                // $('#transactions-table').DataTable().destroy();
                let res = await this.$frappe.get_list(
                    'Sales Invoice',
                    'fields=["name", "title", "status", "modified", "grand_total", "currency"]&order_by=modified DESC&limit=1000'
                );
                console.log('res', res)
                if(res.status_code==200){
                    // console.log(res)
                    this.transactions = res.data;
                } else {
                    this.$popIt.error('Error!', res.text);
                }
            }
        },
        mounted(){
            // if(this.)
            if(!['/login', '/register', '/signup'].includes(this.$route.path)){
                this.user = this.$sessionUserData();
            }
            setTimeout(()=>{
                this.fetchOrders();
            }, 2000);
            // console.log(this.user.full_name)
        },
        components: {
    
        },
    }
</script>

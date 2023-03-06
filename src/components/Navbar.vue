<template>
    <div class="container">
        <ul class="list-inline float-right">
            <li v-for="nav in navItems" :key="nav">
                {{ nav }}
            </li>
            <li>
                <input type="text" v-model="input" placeholder="Search " />
            </li>
            <li class="nav-item">
             <a class="nav-link" href="#">
                <i class="fa fa-bell">
                <span class="badge badge-info ">11</span>
                </i>         
             </a>
       </li>
            
        </ul>
    </div>
</template>

<script >
export default{
    data(){
        return{
            navItems:['Home']
        }
    }
}
</script>

<style scoped>
li{
    display: inline;
    width: 100%;
    height: 100px;
    background-color: transparent;
    color: white;
    padding: 20px;
    margin: 7px;
    margin-top: 2px;
    text-align: center;
}

ul{
    margin-top: 15px;
    float: right; 
    position: sticky;
    width: 100%;
}

</style>

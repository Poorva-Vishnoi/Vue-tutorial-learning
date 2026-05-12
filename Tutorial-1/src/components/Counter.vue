<template>
    <h1>Counter</h1>

    <div>
        <button @click="decrement">Decrement</button>
        <h2 
        class="static"
        :class="[isActive ? 'default-heading' : 'bg-danger']">{{ count }}</h2>
        <button @click="increment">Increment</button>
    </div>
</template>

<script>
export default{
    data(){
        return{
            count:0,
            isActive:false,
            // hasError:false,
            // object:{
            //     'default-heading': true,
            //     'bg-danger': false ,
            // },
            activeClass: 'default-heading',
            dangerClass:'bg-danger',
        }
    },
    methods:{
        increment(){
            this.count++;
            if(this.count>0){
                // this.object['default-heading']=true;
                this.isActive=false;
            //     this.hasError=false;
            }
        },
        decrement(){
            this.count--;
            if(this.count<0){
                // this.object['default-heading']=false;
                this.isActive=true;
            //     this.hasError=true;
            }
        }
    },
}
</script>

<style>
h1 {
    margin: 20px 0;
    text-align:center;
}
.default-heading{
    color: red;
}
.bg-danger{
    background-color: plum;
}
.static{
    font-size: 50px;
}

</style>
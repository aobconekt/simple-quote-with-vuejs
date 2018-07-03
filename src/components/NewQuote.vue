<template>
    <div class="row">
        <form action="">
            <div class="col-sm-8 col-sm-offset-2 xs-12 col-md-6 col-md-offset-3 form-group">
                <label for="">Quote</label>
                <textarea class="form-control" name="" id="" cols="10" rows="5" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary form-control" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
        
    </div>
</template>
<script>
export default {
    data: function(){
        return {
            quote: ''
        }
    },
    methods:{
        createNew(){
            if(this.quote=='' || this.quote.length <= 0){
                return false;
            }else{
                this.$emit('quoteAdded', this.quote);
                this.quote= '';
            }
        }
    }
}
</script>

<style scoped>
form{
    padding: 10px;
}

</style>



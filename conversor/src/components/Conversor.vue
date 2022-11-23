<template>
<div class="conversor">
    <h2>{{moedaA}} para {{moedaB}}</h2>
    <input class="input" type="text" v-model="moedaA_value" :placeholder="moedaA">
    <input class="btn" type="button" value="Converter" @click="converter">
    <h2>{{moedaB_value}}</h2>
</div>
</template>

<script>
export default{
    name: 'Conversor',
    props:['moedaA', 'moedaB'],
    data () {
        return {
            moedaA_value: '',
            moedaB_value: 0

        }
    }, 
    methods: {
        converter() {
            let de_para = this.moedaA + "_" + this.moedaB;
            let url= "https://api.invertexto.com/v1/currency/" + de_para + "?token=1999|q5L8WqlolYbyjQhalYaos3bwTeIwM4p9"

            fetch(url).then(res => {
                return res.json()})
                .then( json => {
                let cotacao = json[de_para].price;
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
            })
        }
    }
}
</script>

<style scoped>
.conversor{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 #9C254D;
    border: 2px solid;
    border-radius: 5px;

}

.btn{
    padding: 10px;
    border-radius:5px;
    border: none;
    background-color: #2A3990;
    color:#fff ;
}

.btn:hover{
    cursor: pointer;
    background-color:#EF9A53;
}

.input{
    border-radius: 5px;
    padding: 10px;
    border: none;
}
</style>
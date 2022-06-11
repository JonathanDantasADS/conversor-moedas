<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
        <input type="button" value="Converter" @click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "Conversor",
    props: ["moedaA", "moedaB"],
        data(){
            return{
                moedaA_value: "",
                moedaB_value: 0
            };
        },
        methods: {
            
            converter() {
                let de_para = `${this.moedaA}-${this.moedaB}`;
                let url = `http://economia.awesomeapi.com.br/json/last/${de_para}`;
                let depara = `${this.moedaA}${this.moedaB}`;

                fetch(url)
                    .then(res=>{
                        return res.json();
                }
                )   
                    .then(json=>{
                        let cotacao = json[depara].bid;
                        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                    })
            }

        }
};
</script>

<style scoped>

.conversor{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgb(130, 130, 130);
}

</style>
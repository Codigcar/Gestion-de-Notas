<template>
    <div id="app">
        <h3>{{ msg }}</h3>
        <div class="form">
            <div class="form-group">
                <label for="">Titulo</label>
                <input class="form-control" type="text" v-model="nota.titulo">
            </div>
            <div class="form-group">
                <label for="">Texto</label>
                <textarea class="form-control" v-model="nota.texto"></textarea>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "GestionDeNotas",
        data(){
            return{
                msg:'Gestion de Notas',
                nota:{
                    titulo:'',
                    texto:''
                }
            }
        }
    }
</script>

<style scoped>
    .form{
        text-align: left;
    }

</style>
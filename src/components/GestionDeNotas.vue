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
        <button class="btn btn-primary" @click="agregarNota">Enviar</button>
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
                },
                notas:[
                    {
                        titulo:'Ir al Colegio',
                        texto:'Curso 1 a las 9.00 a.m.',
                        fecha: new Date(Date.now()).toLocaleDateString()
                    }
                ]
            }
        },
        methods:{
            agregarNota:function () {
                let {texto,titulo} = this.nota;
                this.notas.push({
                    texto,
                    titulo,
                    fecha: new Date(Date.now()).toLocaleString()
                })

            }
        }
    }
</script>

<style scoped>
    .form{
        text-align: left;
    }

</style>
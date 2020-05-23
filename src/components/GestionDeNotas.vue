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
            <button class="btn btn-primary" v-bind:disabled="nota.titulo.length === 0 || nota.texto.length === 0" @click="agregarNota">Agregar</button>
        </div>
        <div class="col-sm-12">
            <div class="col-sm-4 nota" v-for="(nota, index) in notas" v-bind:key="nota" >
                <div class="card">
                    <div class="card-block" >
                        <div class="card-title">{{ nota.titulo }}</div>
                        <div class="card-subtitle mb-2 text-muted">{{ nota.fecha }}</div>
                        <p class="card-text">{{ nota.texto }}</p>
                    </div>
                    <button class="close" @click="eliminarNota(index)">&times;</button>
                </div>
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
                },
                notas:[
                    {
                        titulo:'Almuerzo',
                        texto:'2:00 p.m. - 3:00 p.m.',
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
                this.nota.texto='';
                this.nota.titulo='';
            },
            eliminarNota:function (index) {
                this.notas.splice(index,1);
            }
        }
    }
</script>

<style>
    .form{
        text-align: left;
    }
    .card{
        text-align: left;
        border: 1px solid #2c3e50;
        border-radius: 4px;
        padding-left: 8px;
        padding-right: 8px;
    }
    .nota{
        padding: 5px;
    }

</style>
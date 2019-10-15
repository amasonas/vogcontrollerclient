<template>
    <div class="animated fadeIn">
        <b-card header-tag="header">
            <div slot="header">
                <i class="icon-user"></i> Cadastro de funcionário
            </div>
            <b-card-body>
                <b-row>
                    <b-form>

                        <b-form-group>
                            <label for="name">Nome completo</label>
                            <b-form-input type="text" id="name" v-model="user.name"></b-form-input>
                        </b-form-group>

                        <b-form-group>
                            <label for="name">E-mail</label>
                            <b-form-input type="email" id="name" v-model="user.email"></b-form-input>
                        </b-form-group>

                        <b-form-group>
                            <label for="name">Cpf</label>
                            <b-form-input type="text" id="name" v-model="user.cpf"></b-form-input>
                        </b-form-group>

                        <b-form-group>
                            <label for="name">Senha</label>
                            <b-form-input type="password" id="name" v-model="user.password"></b-form-input>
                        </b-form-group>

                        <b-form-group>
                            <label for="name">Confirmação de senha</label>
                            <b-form-input type="password" id="name" v-model="user.confirmation"></b-form-input>
                        </b-form-group>

                        <b-button variant="success" block :disabled="!canPersist()" >Salvar {{canPersist()}}</b-button>
                    </b-form>
                </b-row>
            </b-card-body>
        </b-card>

    </div>
</template>

<script>
    export default {
        name: 'cards',

        data: function() {
            return {
                user:{},
                show: true
            }
        },
        methods: {
            canPersist: function(){
                if(this.user.password){
                    return this.user.password === this.user.confirmation;
                } else {
                    return false;
                }
            }
        }
    }
</script>

<style scoped>
    .fade-enter-active {
        transition: all .3s ease;
    }
    
    .fade-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    
    .fade-enter,
    .fade-leave-to {
        transform: translateX(10px);
        opacity: 0;
    }
</style>
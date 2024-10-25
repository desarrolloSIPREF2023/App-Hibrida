<template>
    <div id="auth">
        <div class="row h-100">
            <div class="col-lg-5 col-12 bg-white">
                <div id="auth-left">
                    <div class="auth-logo">
                        <a><img src="../assets/logo/logo.jpg" alt="Logo"></a>
                    </div>
                    <h1 class="auth-title" style="font-size: 3.3em !important;">Iniciar Sesión</h1>
                    <p class="auth-subtitle mb-3">Autenticación de usuario</p>

                    <div>
                        <div class="form-group position-relative has-icon-left mb-4">
                            <input type="number" class="form-control form-control-xl" placeholder="Número de Acceso" v-model="datos.number" @input="limitCharts(datos.number)">
                            <div class="form-control-icon">
                                <i class="bi bi-person"></i>
                            </div>
                        </div>
                        <div class="form-group position-relative has-icon-left mb-4">
                            <input type="password" class="form-control form-control-xl" placeholder="Contraseña" v-model="datos.password" @keypress.enter="loginWithEnter">
                            <div class="form-control-icon">
                                <i class="bi bi-shield-lock"></i>
                            </div>
                        </div>

                        <div class="form-group">
                            <button type="button" class="btn btn-primary btn-block btn-lg shadow-lg mt-3" :disabled="datos.textButtonLogin" @click="datos.signIn">
                                <span v-if="datos.textButtonLogin == false">Acceder</span>
                                <div v-else>
                                    <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
                                    verificando acceso...
                                </div>
                            </button>
                        </div>
                    
                    </div>
                    <div class="pt-3 text-center details-serv"></div>
                </div>
            </div>
            <div class="col-lg-7 d-none d-lg-block">
                <div id="auth-right"></div>
            </div>
        </div>
    </div>
</template>

<script>

<style src="../assets/css/auth.css"
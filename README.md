# login.js
Sprint 5
let registros = [];

function agregarRegistro(){
    let in_usuario = document.getElementById('in_usuario').value;
    let in_contrasena = document.getElementById('in_contrasena').value;
    let registro = {
        usuario: in_usuario,
        contrasena: in_contrasena
    }
    registros.push(registro);
};

function iniciar_sesion( usuario,contrasena,rcaptcha){
for (var i in registros) {
        if (registros[i].usuario === usuario  && registros[i].contrasena === contrasena && validar_captcha(rcaptcha)=== true) {
            return true
        }
        else{
            return false
            }
    } 
    
}

function validar_captcha(rcaptcha){
if (rcaptcha != 5) {
    return  false;
    }
return true;
}


module.exports.registros = registros;
module.exports.validar_captcha = validar_captcha;
module.exports.iniciar_sesion = iniciar_sesion;
module.exports.agregarRegistro = agregarRegistro;

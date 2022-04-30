<template>
  <q-page padding>
    <h2>Formulario</h2>

    <pre>{{nombre}} - {{seleccion}} - {{terminos}} </pre>

    <q-form
      class="row q-col-gutter-md"
      @submit.prevent="procesarFormulario"
      @reset="reset"
    >


      <div class="col-12 col-sm-6">
        <q-input
          label="Nombre"
          v-model="nombre"
          :rules="[val => val && val.lenth >0 || 'Por favor escribe algo']"
        />
      </div>




      <div class="col-12 col-sm-6">
          <q-select
          label="Área"
          v-model="seleccion"
          :options="opciones"
          :rules="[val => val && val.lenth >0 || 'Por favor selecciona una opción']"
          />
      </div>

      <div class="col-12">
        <q-toggle

          label="Aceptar los términos y condiciones"
          v-model="terminos"
        />

      </div>

      <div class="col-12">
            <q-btn
            label="Submit"
            color="primary"
            type="submit"
            />
            <q-btn
                  label="Reset"
                  color="primary"
                  outline
                  class="q-ml-sm"
                  :ripple="false"
                  type="reset"
            />
      </div>
    </q-form>
  </q-page>
</template>



<script>
import {ref} from 'vue'
import {useQuasar} from 'quasar'
export default {
    setup () {
        const $q =useQuasar()
        const nombre = ref(null)
        const seleccion = ref(null)
        const terminos = ref(false)
        const opciones = ['Social', 'Económica', 'Medio ambiental']

        const procesarFormulario = () => {
          console.log('diste click')
          if (terminos.value === false){
                $q.notify('Debes aceptar los términos y condiciones')
          }
        }

        const reset = () => {
            nombre.value = null
            seleccion.value = null
            terminos.value = false

        }

        return {
            nombre,
            seleccion,
            opciones,
            procesarFormulario,
            terminos,
            reset,
        }
    }
}

</script>


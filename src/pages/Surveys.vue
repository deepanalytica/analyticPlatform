<template>
  <q-page padding>
    <h2>Formulario</h2>

    <q-form class="row q-col-gutter-md" >

      <div class="col-12 col-sm-6">

        <q-input
          label="Nombre"
        />

      </div>

      <div class="col-12">
            <q-btn
            label="Submit"
            color="primary"
            />
            <q-btn
                  label="Reset"
                  color="primary"
                  outline
                  class="q-ml-sm"
                  :rippler="false"
            />
      </div>
    </q-form>
  </q-page>
</template>

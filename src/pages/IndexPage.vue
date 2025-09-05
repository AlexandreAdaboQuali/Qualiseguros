<template>
  <div>
    <q-page class="flex flex-center">
      <img
        src="~assets/background-qualiseguros.png"
        alt="Background Qualiseguros"
        style="height: auto; width: auto; max-width: 100%; max-height: 100%"
      />
      <q-dialog 
        persistent 
        v-model="popRedirect" 
        content-class="my-image-dialog"
        :maximized="false"
        :full-width="false"
        :full-height="false"
      >
        <q-card class="my-image-card">
          <q-card-section class="row items-center justify-between q-pb-none dialog-header">
            <div class="col-auto row items-center">
              <!-- Logo MDS -->
              <img
                src="~assets/mds-logo.svg"
                alt="MDS Logo"
                style="height: 24px; margin-right: 8px"
              />
              <q-separator
                vertical
                inset
                class="bg-quali-color-blue q-mx-sm"
                style="height: 26px"
              />
              <!-- Logo Qualicorp -->
              <img src="~assets/qualicorp-logo.svg" alt="Qualicorp Logo" style="height: 24px" />
            </div>
            <div class="col-auto dialog-header-text galano-font">Seu seguro Qualicorp é MDS</div>
          </q-card-section>

          <q-img
            src="~assets/seguros_viagem-banner.png"
            alt="Cachorro e menina com bagagem"
            class="dialog-image"
            :ratio="16 / 9"
          />

          <q-card-section class="dialog-text-content">
            <p>
              A partir de agora, todas as
              <strong>contratações e renovações de Seguros Qualicorp</strong> serão feitas pela
              <strong>MDS Brasil</strong>, graças à parceria firmada entre as duas empresas. Para
              mais informações, fale com a MDS pelo telefone <strong>(11) 3169-8999</strong> ou pelo
              WhatsApp <strong>(11) 94842-6895</strong>.<br />
              Agora, caso precise alterar algum dado cadastral do seu seguro atual, envie um e-mail
              para <strong>segurosqualicorp@qualicorp.com.br</strong>.
            </p>
          </q-card-section>

          <q-card-actions class="dialog-footer">
            <q-btn
              label="ir para o site da MDS"
              class="bg-quali-color-blue galano-font dialog-btn"
              style="text-transform: none; font-weight: 600"
              @click="goToMdsSite"
            />
          </q-card-actions>
        </q-card>
      </q-dialog>
    </q-page>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const popRedirect = ref(true)
function goToMdsSite() {
  window.location.href = 'https://www.mdsgroup.com.br/pt/contatos/'
}
//
</script>

<style lang="scss">
.bg-quali-color-blue {
  background-color: #171a88 !important;
  color: white !important;
}

/* Estilos para o dialog da imagem */
.my-image-dialog {
  max-width: 95vw !important;
  width: 800px !important;
  max-height: 95vh !important;
  height: auto !important;
  border-radius: 16px !important;
  overflow: hidden !important;
  margin: 0 auto !important;
  position: relative !important;
}

/* Responsividade para mobile */
@media (max-width: 768px) {
  .my-image-dialog {
    max-width: 95vw !important;
    width: 95vw !important;
    margin: 2.5vw !important;
  }

  .dialog-header {
    padding: 12px 16px;
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }

  .dialog-header-text {
    font-size: 16px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    align-self: flex-end;
  }

  .dialog-text-content {
    padding: 10px 12px;
    font-size: 12px;
  }

  .dialog-footer {
    padding: 12px 16px;
  }

  .dialog-btn {
    width: 100% !important;
  }
}

/* Estilos para desktop - alinhamento à direita */
@media (min-width: 769px) {
  .my-image-dialog {
    max-width: 800px !important;
    width: 800px !important;
    margin: 0 auto !important;
  }

  .dialog-footer {
    display: flex;
    justify-content: flex-end;
  }

  .dialog-btn {
    min-width: 200px;
  }
}

.my-image-card {
  border-radius: 16px;
  background-color: white;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.dialog-header {
  padding: 16px 24px;
  background-color: white;
  border-bottom: 1px solid #eee;
}

.dialog-header-text {
  color: #022561;
  font-weight: 700;
  font-size: 18px;
}

.dialog-image {
  width: calc(100% - 32px);
  height: auto;
  max-height: 300px;
  object-fit: cover;
  margin: 16px;
  border-radius: 8px;
}

.dialog-text-content {
  padding: 10px 12px;
  color: #1a1919;
  font-size: 14px;
  line-height: 1.4;
}

.galano-font {
  font-family: Galano Grotesque;
}

.dialog-footer {
  padding: 12px 24px;
  background-color: white;
  border-top: 1px solid #eee;
}
</style>

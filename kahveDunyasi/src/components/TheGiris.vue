<template>
  <q-page class="login-page">
    <div class="background-image"></div>
    <q-container class="q-pa-md">
      <q-card class="q-ma-auto">
        <q-card-section>
          <div
            class="text-left"
            style="margin-top: 30px; margin-bottom: -20px; "
          >
            <strong
              style="
                font-family: Gotham-Medium, sans-serif;
                font-size: 29.4px;
                left: 20px;
                padding: 15px;
                margin-top: 20px;
              "
            >
              Üye Girişi
            </strong>
          </div>
        </q-card-section>

        <q-card-section
          class="q-pt-lg"
          style="display: flex; justify-content: center"
        >
          <q-form @submit="login">
            <q-input
              v-model="email"
              filled
              type="email"
              placeholder="E-posta"
              dense
              style="padding: 15px; width: 400px; height: 55px; font-size: 17px"
            ></q-input>

            <q-input
              v-model="password"
              filled
              type="password"
              placeholder="Şifre"
              dense
              style="padding: 15px; width: 400px; height: 55px; font-size: 16px"
            ></q-input>

            <q-btn
              type="submit"
              label="Giriş Yap"
              color="primary"
              dense
              block
              style="
                padding: 15px;
                width: 400px;
                height: 70px;
                top: 90px;
                background-color: #005e5c !important;
              "
            ></q-btn>

            <q-btn
              @click="showCaptcha"
              color="positive"
              label="Ben robot değilim"
              icon="check_circle"
              style="bottom: 24px;"
            ></q-btn>
          </q-form>
        </q-card-section>

        <q-card-actions align="left" class="q-pb-lg">
          <router-link
            to=""
            class="text-primary"
            style="
              position: absolute;
              top: 215px;
              left: 5px;
              padding: 15px;
              font-size: 13px;
              color: #3596b5 !important;
              margin-top: 10px;
              margin-left: 14px;
            "
            >Parolanızı mı Unuttunuz?</router-link
          >
        </q-card-actions>

        <p
          style="
            text-align: center;
            position: absolute;
            margin-top: -220px;
            margin-left: 135px;
            font-family: Gotham-Book, sans-serif;
            font-size: 15px;
          "
        >
          Hesabınız yok mu?
        </p>

        <q-card-actions align="left" class="q-pb-lg">
          <router-link
            to=""
            class="text-primary"
            style="
              position: absolute;
              margin-top: -434px;
              left: 223px;
              padding: 15px;
              color: #3596b5 !important;
              font-family: Gotham-Book, sans-serif;
              font-size: 14px;
              margin-left: 34px;
            "
          >
            Kayıt ol</router-link
          >
        </q-card-actions>
      </q-card>
    </q-container>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      remember: false,
    };
  },
  methods: {
    showCaptcha() {
      grecaptcha.ready(() => {
        grecaptcha
          .execute('6LcpNSopAAAAADPuw70ItFfdC3_gMJsQBAKe4cLN', {
            action: 'submit',
          })
          .then((token) => {
            // Captcha doğrulaması başarılı, token'i kullanarak istediğiniz işlemleri yapabilirsiniz.
            console.log('Captcha doğrulandı, token:', token);
            // Örneğin, token'i sunucuya göndererek doğrulama yapabilirsiniz.
          })
          .catch((error) => {
            // Captcha doğrulaması sırasında hata oluştu
            console.error('Captcha doğrulama hatası:', error);
          });
      });
    },
  },
};
</script>

<style scoped>
.login-page {
  height: 800px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('../assets/images/resim.jpg');
  filter: contrast(150%);
  background-size: cover;
  z-index: -1;
  opacity: 0.5; /* İstediğiniz opaklık seviyesini ayarlayabilirsiniz */
}
.login-card {
  max-width: 1000px;
}
.q-pt-lg {
  width: 470px;
  height: 501px;
}
</style>


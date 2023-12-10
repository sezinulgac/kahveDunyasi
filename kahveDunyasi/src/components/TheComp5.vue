<template>
  <div class="header">
    <div class="header-background"></div>
    <div class="header-content">
      <h1>Kurumsal Hediye</h1>
    </div>
  </div>
  <br />
  <br />
  <p
    class="header-description"
    style="
      text-align: center;
      color: #6c0c33;
      font-size: 24px;
      font-family: Gotham-Light;
    "
  >
    Kurumsal Hediyeler İçin Kahve Dünyası Lezzetleri Harika Bir Seçenek! <br />
    <br />
    Kurumsal firmalara özel fiyat avantajlarıyla, birbirinden farklı Kahve
    Dünyası <br />
    lezzetleri hakkında bilgi almak için çikolata kataloğumuza
    <a href="#" class="link"> buradan</a>, kahve <br />
    kataloğumuza <a href="#" class="link"> buradan</a> göz atabilirsiniz. Özel
    günler ve bayramlarda, <br />
    müşterilerinizi veya çalışanlarınızı mutlu edecek hediye alternatiflerini
    size <br />
    anlatabilmemiz için aşağıdaki formu doldurarak bize ulaşabilirsiniz.
  </p>

  <div class="q-flex q-pa-md">
    <div
      class="q-gutter-y-md column"
      style="display: block; margin: auto; max-width: 50%"
    >
      <q-input
        outlined
        v-model="name"
        label="İsim"
        :dense="dense"
        align-self="center"
      />
      <q-input
        outlined
        v-model="surname"
        label="Soyisim"
        :dense="dense"
        align-self="center"
      />
      <q-input
        outlined
        v-model="phone"
        label="Telefon"
        :dense="dense"
        align-self="center"
      />
      <q-input
        outlined
        v-model="email"
        label="E-posta"
        :dense="dense"
        align-self="center"
      />
      <q-input
        outlined
        v-model="companyName"
        label="Firma İsmi"
        :dense="dense"
        align-self="center"
      />
      <q-checkbox
        v-model="specialBox"
        val="teal"
        label=" Özel kutu tasarımı istiyorum."
        color="teal"
      ></q-checkbox>
    </div>
  </div>

  <div class="special-request" style="">
    <p
      class="special-request-text"
      style="
        text-align: center;
        width: 700px;
        height: 45px;
        margin: auto;
        margin-bottom: 15px;
        font-size: 16px;
        background-color: #f7f8f9;
        font-family: Gotham-Book, sans-serif;
        color: black !important;
      "
    >
      Özel kutu tasarım isteği minimum 1.000 adet olan siparişlerde geçerlidir.
    </p>
  </div>

  <div class="textarea-container" style="text-align: center">
    <textarea
      class="special-request-text"
      placeholder="Mesajınızı yazın"
      id="mesaj"
      cols="58"
      rows="8"
      style="width: 41%"
      v-model="message"
      @input="updateCharacterCount"
    ></textarea>
  </div>

  <p style="margin-left: 380px">
    <a href="" style="text-decoration: none; color: black">
      {{ remainingCharacters }} karakter kaldı
    </a>
  </p>

  <div
    class="checkbox-container"
    style="display: flex; align-items: center; justify-content: center"
  >
    <q-checkbox
      v-model="dataProcessingConsent"
      val="teal"
      color="teal"
      label="Kişisel verilerimin aydınlatma metninde belirtilen işleme amaçlarıyla 
      sınırlı olmak üzere yurtdışına aktarılmasına açık rızamla kabul ediyorum."
      style="margin-right: 10px"
      :ripple="true"
      true-value="true"
      false-value="false"
      class="bold-text"
    ></q-checkbox>

    <span
      class="checkbox-label"
      style="
        color: black;
        font-size: 16px;
        font-family: Gotham-Book, sans-serif;
        margin-bottom: 20px;
        font-weight: bold;
      "
    ></span>
  </div>

  <div class="special-request2" style="">
    <p
      class="special-request2-text"
      style="
        text-align: center;
        width: 700px;
        height: 45px;
        margin: auto;
        margin-bottom: 15px;
        font-size: 16px;
        background-color: #f7f8f9;
        font-family: Gotham-Book, sans-serif;
        color: black !important;
      "
    >
      Bu sayfadaki bilgiler sizinle iletişime geçebilmek için alınmaktadır. "Kişisel <br>
      Verilerin Korunması Kanunu Aydınlatma Metni"ni buradan okuyabilirsiniz.
    </p>
  </div>
  <q-btn
    type="submit"
    label="GÖNDER"
    color="primary"
    dense
    block
    style="
      padding: 15px;
      width: 400px;
      height: 70px;
      top: 10px;
      left: 400px;
      text-align: center;
      background-color: #005e5c !important;
    "
  ></q-btn>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      surname: "",
      phone: "",
      email: "",
      companyName: "",
      specialBox: false,
      message: "",
      dataProcessingConsent: false,
      maxCharacters: 1000,
    };
  },
  computed: {
    remainingCharacters() {
      return this.maxCharacters - this.message.length;
    },
  },
  methods: {
    updateCharacterCount() {
      this.remainingCharacters = this.maxCharacters - this.message.length;
    },
  },
};
</script>

<style lang="scss">
.header {
  position: relative;
  width: 100%;
  height: 145px;
  color: white;
  text-align: center;
  overflow: hidden;
}
  .header-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #69042d;
    opacity: 0.8;
    z-index: 1;
  }

  .header-content {
    position: relative;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }

  h1 {
    font-size: 2.5em;
  }

  .special-request {
    margin-top: 0;
    margin-bottom: 0;
  }

</style>
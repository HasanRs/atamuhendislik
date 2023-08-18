<script>
import emailjs from '@emailjs/browser';
import { message } from 'antd';

export default {
  data() {
    return {
      name: '',
      company: '',
      from_mail: '',
      message: ''
    }
  },
  methods: {
    sendEmail(e) {
      try {
        emailjs.sendForm('service_wp240cp', 'template_16lp18j', e.target, 'ZAafNt7-LenI2N80m',
          {
            name: this.name,
            company: this.company,
            from_mail: this.from_mail,
            message: this.message
          })
          .then((result) => {
            console.log(result);
            console.log(this.name);
            console.log(this.company);
            console.log(this.from_mail);
            console.log(this.message);
          });
      }
      catch (error) {
        console.log(error)
      }
      finally {
        message.success('Mesajınız başarıyla gönderildi.');
        this.name = ''
        this.company = ''
        this.from_mail = ''
        this.message = ''
      }
    }
  }
}
</script>
<template>
  <main>
    <section class="w-full mx-auto my-12">
      <div class="relative flex justify-center max-h-full overflow-hidden lg:px-0 md:px-12">
        <div
          class="relative z-10 flex flex-col flex-1 px-4 py-10 bg-white shadow-2xl lg:py-24 md:flex-none md:px-28 sm:justify-center"
        >
          <div class="w-full max-w-md mx-auto md:max-w-sm md:px-0 md:w-96 sm:px-4">
            <div class="flex flex-col">
              <div>
                <h2 class="text-4xl text-black">Bizimle İletişime Geç</h2>
                <p class="mt-2 text-sm text-gray-500">
                  Sizden gelen her soru ve geri bildirim bizim için değerlidir.<br />
                  İhtiyaçlarınıza yönelik çözümlerimiz hakkında daha fazla bilgi almak veya projelerinizle ilgili
                  detayları konuşmak için bize ulaşın.<br />
                </p>
              </div>
            </div>
            <form @submit.prevent="sendEmail" ref="form">
              <input autocomplete="false" name="hidden" style="display: none" />
              <input name="_redirect" type="hidden" value="#" />
              <div class="mt-4 space-y-6">
                <div>
                  <label class="block mb-3 text-sm font-medium text-gray-600" name="name"> Ad Soyad </label>
                  <input
                    class="block w-full px-6 py-3 text-black bg-white border border-gray-200 appearance-none rounded-xl placeholder:text-gray-400 focus:border-blue-500 focus:outline-none focus:ring-blue-500 sm:text-sm"
                    placeholder="Ad Soyad"
                    v-model="name"
                    name="name"
                  />
                </div>
                <div class="col-span-full">
                  <label class="block mb-3 text-sm font-medium text-gray-600" name="company"> Firma Adı </label>
                  <input
                    class="block w-full px-6 py-3 text-black bg-white border border-gray-200 appearance-none rounded-xl placeholder:text-gray-400 focus:border-blue-500 focus:outline-none focus:ring-blue-500 sm:text-sm"
                    placeholder="Firma Adı"
                    v-model="company"
                    name="company"
                  />
                </div>
                <div class="col-span-full">
                  <label class="block mb-3 text-sm font-medium text-gray-600" name="email"> E-mail </label>
                  <input
                    class="block w-full px-6 py-3 text-black bg-white border border-gray-200 appearance-none rounded-xl placeholder:text-gray-400 focus:border-blue-500 focus:outline-none focus:ring-blue-500 sm:text-sm"
                    placeholder="Email"
                    autocomplete="off"
                    type="email"
                    v-model="from_mail"
                    name="from_mail"
                  />
                </div>
                <div>
                  <div>
                    <label class="block mb-3 text-sm font-medium text-gray-600" name="message"> Proje Detayları </label>
                    <div class="mt-1">
                      <textarea
                        class="block w-full px-6 py-3 text-black bg-white border border-gray-200 appearance-none rounded-xl placeholder:text-gray-400 focus:border-blue-500 focus:outline-none focus:ring-blue-500 sm:text-sm"
                        placeholder="Ne üzerinde çalışmak istersiniz?"
                        rows="4"
                        v-model="message"
                        name="message"
                      ></textarea>
                    </div>
                  </div>
                </div>
                <div class="col-span-full">
                  <input
                    class="items-center justify-center w-full px-6 py-2.5 text-center text-white duration-200 bg-black border-2 border-black rounded-full nline-flex hover:bg-transparent hover:border-black hover:text-black focus:outline-none focus-visible:outline-black text-sm focus-visible:ring-black"
                    type="submit"
                    value="Gönder"
                  />
                </div>
              </div>
            </form>
          </div>
        </div>
        <div class="hidden bg-white lg:block lg:flex-1 lg:relative sm:contents">
          <div class="absolute inset-0 object-cover w-full h-full bg-white" alt="" height="1866" width="1664">
            <img
              class="object-center w-full h-auto bg-gray-200"
              src="https://images.unsplash.com/photo-1603172159066-6ade2af706c4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1035&q=80"
              alt=""
              width="1310"
              height="873"
            />
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

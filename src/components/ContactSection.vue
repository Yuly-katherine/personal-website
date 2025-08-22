<template>
  <section class="text-white mt-20" id="contact">
    <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">
      Let's Connect
    </h2>
    <div
      class="grid md:grid-cols-2 gap-4 relative px-4 xl:px-16 mt-8 aos-init aos-animate"
      data-aos="zoom-in-up"
    >
      <div>
        <p class="text-[#adb7be]">
          If you have any questions, please feel free to fill out the contact
          form or write me directly to my email.
        </p>
        <div class="col-lg-4 col-md-4 mb-lg-0 mt-5">
          <div class="flex mb-10 items-center">
            <div
              class="p-2"
              style="
                background: #111a3e;
                width: 50px;
                height: 46px;
                display: flex;
                justify-content: center;
                border-radius: 50%;
                overflow: hidden;
                border: 1px solid#111a3e;
                backdrop-filter: blur(9px);
                -webkit-backdrop-filter: blur(9px);
              "
            >
              <img
                src="https://img.icons8.com/metro/50/ffffff/new-post.png"
                alt="new-post"
                class="w-6"
              />
            </div>
            <div class="ml-5 text-white">
              <h4>Email</h4>
              <p>kathegomv@gmail.com</p>
            </div>
          </div>
          <div class="flex mb-10 items-center">
            <div
              class="p-2"
              style="
                background: #111a3e;
                width: 50px;
                height: 46px;
                display: flex;
                justify-content: center;
                border-radius: 50%;
                overflow: hidden;
                border: 1px solid#111a3e;
                backdrop-filter: blur(9px);
                -webkit-backdrop-filter: blur(9px);
              "
            >
              <img
                src="https://img.icons8.com/?size=100&id=3tC9EQumUAuq&format=png&color=ffffff"
                alt="phone"
                class="w-6"
              />
            </div>
            <div class="ml-5 text-white">
              <a href="https://github.com/Yuly-katherine" target="_blank">
                GitHub</a
              >
            </div>
          </div>
          <div class="flex mb-10 items-center">
            <div
              class="p-2"
              style="
                background: #111a3e;
                width: 50px;
                height: 46px;
                display: flex;
                justify-content: center;
                border-radius: 50%;
                overflow: hidden;
                border: 1px solid#111a3e;
                backdrop-filter: blur(9px);
                -webkit-backdrop-filter: blur(9px);
              "
            >
              <img
                src="https://img.icons8.com/ios-filled/50/ffffff/linkedin.png"
                alt="linkedin"
                class="w-6"
              />
            </div>
            <div class="ml-5 text-white">
              <a
                href="https://www.linkedin.com/in/yulykgomezv/"
                target="_blank"
              >
                LinkedIn</a
              >
            </div>
          </div>
        </div>
      </div>
      <div
        style="
          background: #111a3e;
          width: 100%;
          height: 100%;
          border-radius: 20px;
          overflow: hidden;
          border: 1px solid #111a3e;
          backdrop-filter: blur(9px);
          -webkit-backdrop-filter: blur(9px);
        "
      >
        <form
          @submit.prevent="submitForm"
          ref="formRef"
          :model="infoForm"
          class="flex flex-col p-2 aos-init aos-animate"
          data-aos="zoom-in-up"
        >
          <div class="mb-6">
            <label for="email" class="text-white block mb-2 text-sm font-medium"
              >email</label
            ><input
              type="email"
              id="email"
              class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
              placeholder="email@email.com"
              name="email"
              required
              v-model="infoForm.email"
            />
          </div>
          <div class="mb-6">
            <label
              for="subject"
              class="text-white block mb-2 text-sm font-medium"
              >Subject</label
            ><input
              type="subject"
              id="subject"
              class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
              placeholder="subject"
              name="subject"
              required
              v-model="infoForm.subject"
            />
          </div>
          <div class="mb-6">
            <label
              for="message"
              class="text-white block mb-2 text-sm font-medium"
              >Message</label
            ><textarea
              id="Message"
              class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
              placeholder="Let's talk about ... "
              name="message"
              required
              v-model="infoForm.message"
            ></textarea>
          </div>
          <button
            type="sumit"
            class="z-1 w-[100%!important] px-6 md:px-7 py-3 rounded-full sm:w-max flex justify-center text-white bg-[#f59e0b] border-2 border-transparent cursor-pointer"
          >
            Send Message
          </button>
        </form>
      </div>
      <div
        class="bg-gradient-to-tr opacity-25 from-[#570cac] to-[#f59e0b] blur-2xl h-20 w-80 z-0 absolute -top-1/2 -left-4 transform -translate-x-2/3 -translate-1/2"
      ></div>
    </div>
  </section>
</template>

<script setup>
//----------IMPORTS----------//
import { ref, reactive } from "vue";

//----------VARIABLES----------//
const formRef = ref(null);
const infoForm = reactive({
  email: "",
  subject: "",
  message: "",
});

//----------METHODS----------//
const submitForm = async () => {
  
  try {
    const formData = new FormData();
    formData.append("email", infoForm.email);
    formData.append("subject", infoForm.subject);
    formData.append("message", infoForm.message);

    formData.append("_captcha", "false");
    formData.append("_template", "box");
    formData.append(
      "_autoresponse",
      "Thanks for contacting me, I will answer you soon 😊."
    );

    const response = await fetch("https://formsubmit.co/ajax/kathegomv@gmail.com", {
      method: "POST",
      headers: { Accept: "application/json" },
      body: formData,
    });

    if (response.ok) {
      alert(" Message sent successfully!");
      infoForm.email = "";
      infoForm.subject = "";
      infoForm.message = "";
    } else {
      alert(" Failed to send message.");
    }
  } catch (error) {
    console.error(error);
    alert(" Error sending message.");
  }
};

</script>

<style scoped>
</style>
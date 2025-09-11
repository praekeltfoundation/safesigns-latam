<!-- { section: "56e39341-e47c-4662-b124-b7b5c254fe11", x: -1560, y: -240} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_2" and contact.arm == "GAMIFIED" and
       contact.onboarding_complete == true

trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_g3")

```

<!-- { section: "6b382a3b-6002-46e6-b0f4-5a8e70f741f7", x: -1104, y: -120} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "1d342d19-9b9e-4962-b81a-9e3936cda936",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_gamified_mod3", "spa", [],
      translated_body_params: [],
      translated_document: [],
      translated_header: [],
      translated_image: [],
      translated_url: [],
      translated_video: [],
      buttons: ["0"]
    )

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_22)
end

```

<!-- { section: "b7b86a5a-438b-4dc2-8a04-5cc4398dade9", x: 624, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "Buenísimo 👍"]) do
      text("El reto de ayer era hacer tu primer día de práctica zen 🧘 
🎵 ✍️ ¿Cómo te fue con el reto de ayer?")
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "Buenísimo 👍")
  then(Catch_all_1)
end

```

<!-- { section: "10b5d96e-ebfe-45b4-ba54-a1bec6b576b3", x: 576, y: -648} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "dbc7f180-4f3f-4b7a-9a14-dab34d5624da", x: 1608, y: 48} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text("No te preocupes, ¡Hoy podrás ponerte al día!")
  then(Message_4)
end

```

<!-- { section: "90377797-0d05-4f9d-a445-f01bcb515a8d", x: 1656, y: 264} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text("Increíble, ¡Apuesto que se va a notar en tus respuestas de hoy!")
  then(Message_4)
end

```

<!-- { section: "980085be-f96e-4ff6-b729-3cda61890edb", x: 2136, y: 72} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Vale 👍"]) do
      text("Recuerda que, entre más larga tu racha, ¡más stickers vas acumulando!")
    end

  then(Message_5 when ref_Message_4 == "Vale 👍")
  then(Catch_all_2)
end

```

<!-- { section: "48106215-ac54-4891-b491-e4a1d67104cd", x: 2280, y: -696} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "9d2ce732-d86c-41ed-aae8-69f972eac288", x: 2592, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este tercer episodio, Pilar y Mari hablarán sobre cómo podemos ser apoyo para alguien que esté pasando por una situación difícil. 🫂 Además, puedes pensar en cómo tú pedirías ayuda si algún día lo necesitas 🫰"
  )

  then(Messge_6)
end

```

<!-- { section: "e156db86-e580-4009-894a-7335a174e8b8", x: 2976, y: 120} -->

```stack
card Messge_6, "Messge_6",
  version: "1",
  uuid: "e7629ef9-bb28-53c5-870d-24bf828ea340",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Messge_6 =
    buttons(["Ok 👌"]) do
      text(
        "Recuerda que, si hay algo que te haga sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Lo más importante es que te sientas bien! 🫶"
      )
    end

  then(Message_7 when ref_Messge_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "9880bb46-1aeb-46ea-a350-2922ee5f3108", x: 3216, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Messge_6)
end

```

<!-- { section: "002bca1b-2f8f-4846-be5f-7d707784a5ea", x: 3384, y: 96} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "QUESTION" do
  ref_Message_7 =
    ask(
      "Pensando en este tema, siempre es bueno acordarnos que tener a alguien en quien confiar es increíble 😎

Para ti, ¿qué características crees debe tener alguien para que lo consideres como un(a) buen(a) amigo(a)? Escribe o manda por nota de voz al menos dos características"
    )

  then(Branch_1f764e)
end

```

<!-- { section: "bab9194c-05d1-4cbf-a606-5442b7b0b36a", x: 4944, y: 96} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por tu respuesta! Ahora sí, empecemos con el podcast🎧

Recuerda que si hay algo que te haga sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Lo más importante es que te sientas bien! 🫶"
  )

  then(Message_9)
end

```

<!-- { section: "5218e6df-a97b-4046-b5b6-84dbea62e407", x: 5352, y: 96} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "MEDIA_AUDIO" do
  audio("1768ef34-c2fd-48f9-a480-4cb5085a995e-G_M3_P1.mp3")
  then(Message_10)
end

```

<!-- { section: "5770e794-5028-45d4-8bc2-d4e30f6f4499", x: 5760, y: 96} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Ya escuché el audio"]) do
      text("¿Lista? Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_11 when ref_Message_10 == "Ya escuché el audio")
  then(Catch_all_4)
end

```

<!-- { section: "9ac674c7-7a99-4b67-b1ab-56458eb7d8d6", x: 6216, y: 120} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "TEXT_MESSAGE" do
  text("¡Complejo el tema de hoy! Vamos a reflexionar un poco.")
  then(Message_12)
end

```

<!-- { section: "4ad80f7b-53aa-4687-9ec5-60dd99a56817", x: 6672, y: 120} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["¿De quién? Chisme🔥", "No me importa🙄", "Es un asunto serio🤔"]) do
      text(
        "Como nos contaron Mari y Pilar, imagina que en el grupo de whatsapp de los chicos del equipo de fútbol están compartiendo fotos con contenido sexual de algunas compañeras. ¿Qué piensas de esta situación?"
      )
    end

  then(Message12_1 when ref_Message_12 == "¿De quién? Chisme🔥")
  then(Message12_2 when ref_Message_12 == "No me importa🙄")
  then(Message12_3 when ref_Message_12 == "Es un asunto serio🤔")
  then(Catch_all_5)
end

```

<!-- { section: "c9697edb-b9f7-45c4-b8aa-fd1890d8eb66", x: 5496, y: -576} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "0af10636-4a7a-490d-8b37-36220db599e6", x: 6576, y: -600} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "b936cad2-2099-4818-bc15-d1cf86f232a5", x: 8040, y: -288} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "MEDIA_AUDIO" do
  audio("f4d33dfe-a136-4c3c-b7c8-dea59eb7d001-G_M3_P1_R1.mp3")
  then(Message_13_)
end

```

<!-- { section: "95470ef2-61f6-44ca-8c48-a594a834d759", x: 7968, y: 336} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "MEDIA_AUDIO" do
  audio("ea5a8497-889b-4c8b-8464-ad819f2d7402-G_M3_P1_R2.mp3")
  then(Message_13_)
end

```

<!-- { section: "5082a47c-8321-402d-80c1-d0512454dc47", x: 7944, y: 792} -->

```stack
card Message_13_3, "Message_13_3",
  version: "1",
  uuid: "d0b53090-c491-560e-9fdb-e2ba5b1436df",
  code_generator: "MEDIA_AUDIO" do
  audio("9224212b-5416-4aab-8370-9fece783b466-G_M3_P1_R3.mp3")
  then(Message_13_)
end

```

<!-- { section: "7ac75bf7-c1de-4391-a122-2fac8e653297", x: 8616, y: 384} -->

```stack
card Message_13_, "Message_13_",
  version: "1",
  uuid: "d9dcee57-d398-5973-aa45-c69f79836a9c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13_ =
    buttons(["Sigue el podcast 🎧"]) do
      text("Cuando termine el audio, pulsa el botón *Sigue el podcast* 🎧")
    end

  then(Message_14_1 when ref_Message_13_ == "Sigue el podcast 🎧")
  then(Catch_all_8)
end

```

<!-- { section: "4031b6ea-645a-4e8d-b3f7-8f73708bb27a", x: 8712, y: -912} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13_)
end

```

<!-- { section: "d5d5d119-81c6-4569-860c-070ed3e24832", x: 9072, y: 456} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "MEDIA_AUDIO" do
  audio("560d3e8a-525e-4939-aa26-eb99c35651e6-G_M3_P2.mp3")
  then(Message_14)
end

```

<!-- { section: "d9bb46a5-55a5-45f5-9ee5-b59c401886d5", x: 9504, y: 432} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_15 when ref_Message_14 == "Ya escuché el audio")
  then(Catch_all_9)
end

```

<!-- { section: "9dac4005-e3f0-45d7-9900-ae0d8063a8fb", x: 9840, y: -1104} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "728b985f-47da-443e-94e6-56c79d4e21cd", x: 9936, y: 456} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "QUESTION" do
  ref_Message_15 = ask("¿Qué piensas de lo que han comentado Pilar y Mar?")
  then(Branch_7b1924)
end

```

<!-- { section: "8296bdb4-3b51-4c77-91b3-ec836719679f", x: 11232, y: 408} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["¡Lista! 🏁"]) do
      text(
        "Vamos a contarte un par de situaciones para que nos puedas contar qué opinas de cada una ¿Lista?"
      )
    end

  then(Message_17 when ref_Message_16 == "¡Lista! 🏁")
  then(Catch_all_10)
end

```

<!-- { section: "dde6bfad-475c-4290-9c09-4a96edf4fc92", x: 11016, y: -1104} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16)
end

```

<!-- { section: "d88b3729-41c4-4304-b6ec-ec19ea26c957", x: 11736, y: 432} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "LIST" do
  ref_Message_17 =
    list("List", [
      "Busquemos ayuda🗣️",
      "¿Qué? No te creo 😲",
      "Eso te pasa por boba",
      "¡Funemos al tipo!"
    ]) do
      text(
        "Imagina que, un día, entras a tu salón y ves que una amiga está llorando. Te cuenta en secreto que el novio la está chantajeando que va a compartir sus fotos íntimas si ella lo deja 📸
¿Qué le dirías tú?"
      )
    end

  then(Message17_1 when ref_Message_17 == "Busquemos ayuda🗣️")
  then(Message17_2 when ref_Message_17 == "¿Qué? No te creo 😲")
  then(Message17_3 when ref_Message_17 == "Eso te pasa por boba")
  then(Message17_4 when ref_Message_17 == "¡Funemos al tipo!")
  then(Catch_all_11)
end

```

<!-- { section: "0ed0d920-45be-40fb-ae4a-99d00de6eae2", x: 11784, y: -1200} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_17)
end

```

<!-- { section: "b11a8959-4945-4c5e-8cce-38f11ec11f92", x: 15168, y: 192} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Siguiente pregunta"]) do
      text("Cuando finalice el audio, presione el botón de siguiente pregunta.")
    end

  then(Message_19 when ref_Message_18 == "Siguiente pregunta")
  then(Catch_all_14)
end

```

<!-- { section: "76217bf8-5dd8-4ce4-ab45-ab4ef14d90ab", x: 13296, y: 96} -->

```stack
card Message_18_1, "Message_18_1",
  version: "1",
  uuid: "8a733211-d7eb-5c2b-9a03-0e4bea4cba0b",
  code_generator: "MEDIA_AUDIO" do
  audio("625c5738-4ad2-4813-b1e1-5a901c2825f7-G_M3_P2_R1.mp3")
  then(Message_18)
end

```

<!-- { section: "631fb14c-8e58-4d44-8c0b-ec98c2a17934", x: 13272, y: 504} -->

```stack
card Message_18_2, "Message_18_2",
  version: "1",
  uuid: "f991fbc5-7712-5518-a753-a5e3f160f9ef",
  code_generator: "MEDIA_AUDIO" do
  audio("753aca1b-82c5-4b42-8afc-33ce970103f8-G_M3_P2_R2.mp3")
  then(Message_18)
end

```

<!-- { section: "16cf6b4e-3780-4000-abaf-4f275deb003d", x: 13296, y: 816} -->

```stack
card Message_18_3, "Message_18_3",
  version: "1",
  uuid: "8bf10063-4658-5846-a34e-3c68b1167484",
  code_generator: "MEDIA_AUDIO" do
  audio("6fd73898-d13b-4d61-8b83-5d131048af6e-G_M3_P2_R3.mp3")
  then(Message_18)
end

```

<!-- { section: "974ddc8d-941d-4bc2-91ba-a6a8b2e14be2", x: 13320, y: 1248} -->

```stack
card Message_18_4, "Message_18_4",
  version: "1",
  uuid: "e2145dee-22be-5dbf-bbda-33522ebe4f5a",
  code_generator: "MEDIA_AUDIO" do
  audio("d366d616-08d3-415c-ad12-996bef1af0d9-G_M3_P2_R4.mp3")
  then(Message_18)
end

```

<!-- { section: "920e4fd2-b99f-4f69-affb-f83a5a3ddd8d", x: 13752, y: -1272} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "1b9f1244-e43f-45fc-a36e-1ec713cd85d1", x: 15240, y: -840} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "29fd27f6-47f0-5aec-8054-b4d312e8fcca",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18)
end

```

<!-- { section: "e38e9ea5-0daa-4cf8-8b88-fce668391987", x: 15864, y: 96} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["Las peleas 🥊", "El chisme 🗣️", "El apoyo 🤝"]) do
      text("En tu *grupo de amigas,* ¿qué es lo más común que se presente?")
    end

  then(Message19_1 when ref_Message_19 == "Las peleas 🥊")
  then(Message19_2 when ref_Message_19 == "El chisme 🗣️")
  then(Message19_3 when ref_Message_19 == "El apoyo 🤝")
  then(Catch_all_16)
end

```

<!-- { section: "5aabf310-c548-4427-b36d-b7d77000895c", x: 15816, y: -1272} -->

```stack
card Catch_all_16, "Catch_all_16",
  version: "1",
  uuid: "d4296a10-0d55-5756-9088-6b503693c13b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_19)
end

```

<!-- { section: "8ee1f018-5082-47a5-b426-e8ffca6ba0b4", x: 17424, y: 216} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Cada grupo de amigas tiene su propia dinámica, y es útil reflexionar sobre qué aspectos predominan. Si las peleas o el chisme son comunes, considera cómo podrían abordarse para mejorar la relación. Si el apoyo es lo más frecuente, ¡es un gran signo de un grupo fuerte y solidario! 💫"
  )

  then(Message_21_1)
end

```

<!-- { section: "0ce1a9eb-be5c-4f28-bb0e-ac0c89042947", x: 18624, y: 240} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_21 =
    buttons(["Ya escuché el audio"]) do
      text("¿Lista? Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_22 when ref_Message_21 == "Ya escuché el audio")
  then(Catch_all_17)
end

```

<!-- { section: "2fdd8deb-02fc-4d65-9344-41a61b1b80d0", x: 18672, y: -792} -->

```stack
card Catch_all_17, "Catch_all_17",
  version: "1",
  uuid: "209ee976-ac39-5434-95b8-eaa8c2de1f85",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_21)
end

```

<!-- { section: "947b00a6-bad3-4d73-8747-54cfb3e0a29c", x: 19152, y: 240} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "TEXT_MESSAGE" do
  text("¡Que bueno que ya estás pensando en cómo apoyar mejor a una amiga!")
  then(Message_23)
end

```

<!-- { section: "72cb2ba0-65f3-4d07-8ba9-6a51bd97b173", x: 19560, y: 240} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Completaste el episodio 3 de nuestro podcast! 🥳 Hoy tengo más stickers para que los puedas usar y te ayuden si algún día te enfrentas a una situación como esta."
      )
    end

  then(Message_24_sticker_1 when ref_Message_23 == "¡Manda mis stickers!")
  then(Catch_all_18)
end

```

<!-- { section: "6b63c459-4ba6-4690-b021-1430132668cf", x: 19440, y: -744} -->

```stack
card Catch_all_18, "Catch_all_18",
  version: "1",
  uuid: "e1b87782-5fd0-51c8-b25e-fa1a45e4e585",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_23)
end

```

<!-- { section: "42440152-a538-4a7d-92d4-d2200bf753ac", x: 20448, y: -840} -->

```stack
card Message_24_sticker_1, "Message_24_sticker_1",
  version: "1",
  uuid: "cb446ffc-b076-593f-907a-0a8f1d1167b6",
  code_generator: "MEDIA_IMAGE" do
  image("552fb0b7-e58a-4082-954f-8a0810a8edc5-Modulo3_Ayvv-Copy.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "efdefd55-a8f1-45fe-888d-45381ad349ca", x: 21024, y: 264} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["¡Entendido!  🫡"]) do
      text("¡Van 3 de 6 días de racha en el reto del podcast! No olvides escucharnos mañana! 🎧")
    end

  then(Message_26 when ref_Message_25 == "¡Entendido!  🫡")
  then(Catch_all_19)
end

```

<!-- { section: "5ab07cc3-03f7-404e-9f41-ee31cbacbd42", x: 21192, y: -864} -->

```stack
card Catch_all_19, "Catch_all_19",
  version: "1",
  uuid: "aa2b872e-9152-5c35-9ece-d9c72a2f6ea0",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_25)
end

```

<!-- { section: "9febcb20-4503-441e-bcb9-51fa146fa1a1", x: 21480, y: 264} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "QUESTION" do
  ref_Message_26 =
    ask(
      "Hoy, escuchamos algunos tips que podemos usar para ayudar a alguien a sentirse mejor... ¿Qué frases se te ocurren que podrías decirle a una amiga que está pasando por un mal momento?"
    )

  then(Branch_14832c)
end

```

<!-- { section: "bf2204c2-485a-4a93-8811-c0a780f3218b", x: 22800, y: 264} -->

```stack
card Message_27, "Message_27",
  version: "1",
  uuid: "58095b08-ea56-5e0f-9bba-0cdfec59e6c4",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_27 =
    buttons(["Amigas 👯‍♀️", "Mamá o papá 👩‍👧", "Familiar 👩🧑"]) do
      text(
        "Ahora, te voy a dejar este reto: Para mañana, reflexiona acerca de quien sería para ti la persona que te pueda ofrecer un espacio seguro para contarle tus cosas y ayudarte. ¿Quién es esa persona para ti?"
      )
    end

  then(Message27_1 when ref_Message_27 == "Amigas 👯‍♀️")
  then(Message27_2 when ref_Message_27 == "Mamá o papá 👩‍👧")
  then(Message27_3 when ref_Message_27 == "Familiar 👩🧑")
  then(Catch_all_20)
end

```

<!-- { section: "5baaeb75-e88f-42b1-af19-cac8366a6216", x: 22488, y: -840} -->

```stack
card Catch_all_20, "Catch_all_20",
  version: "1",
  uuid: "33422d10-445d-5f76-96c9-e793d4011333",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_27)
end

```

<!-- { section: "d01fba46-2f33-447a-956b-f2a2b7d277e8", x: 24648, y: 312} -->

```stack
card Message_28, "Message_28",
  version: "1",
  uuid: "fa2bc47c-07ac-5963-8796-2bedea805ae2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_28 =
    buttons(["Entendido 🌸"]) do
      text(
        "Ok, amiga, esto fue todo por hoy. ¡Prepárate porque el episodio de mañana va a estar increíble! Hablaremos sobre lo poderosas que podemos ser 💪 y los cambios que podemos realizar en nuestras vidas."
      )
    end

  then(Message_29 when ref_Message_28 == "Entendido 🌸")
  then(Catch_all_21)
end

```

<!-- { section: "e9a68285-615e-4fba-9f23-d204c559c64e", x: 25128, y: 336} -->

```stack
card Message_29, "Message_29",
  version: "1",
  uuid: "ffd1d764-bd67-5983-8837-8f36a9310a34",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_f04464)
end

```

<!-- { section: "3a26c6e2-f4bd-4a13-8b43-083f3955d6cb", x: 24312, y: -672} -->

```stack
card Catch_all_21, "Catch_all_21",
  version: "1",
  uuid: "317ddc77-c862-5558-91a3-6d411d930f0a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_28)
end

```

<!-- { section: "394a9c5c-c3da-4fed-873f-5ab12bd0ffc1", x: 25560, y: 312} -->

```stack
card Profile_f04464, "Profile_f04464",
  version: "1",
  uuid: "01570d50-4955-5140-bf9f-31b0e5535f7e",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_3")
  then(ModuleCompleted)
end

```

<!-- { section: "0708e608-5dc6-4b95-ab8c-b7f49c249045", x: 18024, y: 216} -->

```stack
card Message_21_1, "Message_21_1",
  version: "1",
  uuid: "a1a8abf5-80a1-551b-893d-f420016ccec9",
  code_generator: "MEDIA_AUDIO" do
  audio("b18eeff2-1cfe-4323-9d0d-9ddcebebd652-G_M3_P3.mp3")
  then(Message_21)
end

```

<!-- { section: "ac0714c2-c131-4e30-ba62-88f058eb9d57", x: 20448, y: -336} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("81906cf7-6ae4-4f9c-9a6e-8440da3399f7-Modulo3_Hablemos-Copy.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "1ad22369-3e23-41cd-9115-cd7a6df1e218", x: 20448, y: 120} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("79961920-563e-4b14-8f67-b677e85a2300-Modulo3_LasChicas-Copy.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "92231cb7-1e21-41c5-854f-5375305749ba", x: 20448, y: 696} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("829dc594-b6bd-46fb-a289-18ba0f40990d-Modulo3_Rapido-Copy.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "ac4a8b94-888e-4ae6-a8e4-29a4fa0ab328", x: 20448, y: 1224} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("91261781-7b71-423b-9c25-34a99828605c-Modulo3_Siempre-Copy.webp")
  text("")
  then(Message_25)
end

```

<!-- { section: "ca1206dd-9bb2-4955-8641-7661cc038152", x: 3864, y: 120} -->

```stack
card Branch_1f764e, "Branch_1f764e",
  version: "1",
  uuid: "fd35952b-41d8-57ad-930c-915f91299a4c",
  code_generator: "CONDITIONALS" do
  then(Message7 when event.message.type == "audio")
  then(Message7 when event.message.type == "text")
  then(Text_ff8356)
end

```

<!-- { section: "3b22ca62-565c-4a05-b14f-2e619c77ca00", x: 3624, y: -384} -->

```stack
card Text_ff8356, "Text_ff8356",
  version: "1",
  uuid: "79d963dc-638c-5899-a52d-f14fed5e0f71",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_7)
end

```

<!-- { section: "fabefa86-6279-4c6d-9e22-231988c1005c", x: 10296, y: 432} -->

```stack
card Branch_7b1924, "Branch_7b1924",
  version: "1",
  uuid: "ebb4ff24-39e1-532b-882d-c10639be7d87",
  code_generator: "CONDITIONALS" do
  then(Message15 when event.message.type == "audio")
  then(Message15 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "a734ada2-a858-4e6e-8607-d66c42ca542d", x: 10008, y: 960} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_15)
end

```

<!-- { section: "dc0823b0-d29e-4c57-bfc7-79765d23e64d", x: 21888, y: 264} -->

```stack
card Branch_14832c, "Branch_14832c",
  version: "1",
  uuid: "963cd308-2fbc-5fa0-bac6-ac751b2a1d2c",
  code_generator: "CONDITIONALS" do
  then(Message26 when event.message.type == "audio")
  then(Message26 when event.message.type == "text")
  then(Catch_all_2_2)
end

```

<!-- { section: "54e0222d-7e9e-4dbe-ab3e-96a43cd12bd5", x: 21768, y: 696} -->

```stack
card Catch_all_2_2, "Catch_all_2_2",
  version: "1",
  uuid: "86031531-4763-5dde-ab3c-b02fc964194a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_26)
end

```

<!-- { section: "f905d26b-9bae-4e73-bb27-d6ad348ceca7", x: 23904, y: 408} -->

```stack
card Safe_Guarding_1, "Safe_Guarding_1",
  version: "1",
  uuid: "3bcf8a17-d6b6-53a8-a659-fd1b02605d0e",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¿Crees que estás pasando por una situación similar de la que hablamos hoy y necesitas ayuda? Aquí tienes líneas de apoyo confidenciales para hablar o reportar tu caso:"
  )

  then(Safe_Guarding_2)
end

```

<!-- { section: "742e5f02-4bab-4778-baca-c2bdea8ab243", x: 24264, y: 432} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text(
    "1. Línea Púrpura (WhatsApp): +57 300 7551846 o *Visita aquí* https://www.sdmujer.gov.co/nuestros-servicios/servicios-para-las-mujeres/linea-purpura  
2. Línea 141 (ICBF) – Atención 24/7
3. Reporte en Línea: *Te Protejo* https://teprotejocolombia.org/"
  )

  then(Message_28)
end

```

<!-- { section: "2deb820e-41ee-4eb3-8329-3f47c0d3329f", x: -720, y: -336} -->

```stack
card Catch_all_22, "Catch_all_22",
  version: "1",
  uuid: "bea5061d-e2fb-4b27-9634-b039dde28943",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "2ac6a541-2a6e-4258-8aa0-aad4eeb8a282", x: 6744, y: 624} -->

@Buhle

Please save insights here

<!-- { section: "9255bb3e-3435-4d11-9de3-29fabc2cc5a3", x: 24, y: 312} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module3_started (yes)

<!-- { section: "245e1d2a-2765-4101-b4c7-c89ce5dfdbe1", x: 4128, y: 456} -->

**@Buhle**

DS note: Flow result: module3_social_support {user input}****

Please save the users response here, gave you both blocks, please dlt the one you dont need

<!-- { section: "5093110a-cf91-4b09-89f1-5b4d22965f47", x: 22152, y: 672} -->

**@Buhle**

please save DS note here, I added in a code block just in case

DS note: Flow result: module3_social_support2 {user input}

<!-- { section: "f27011b7-d7ac-44e9-bed3-b74ef607aed8", x: 25536, y: 600} -->

**@Buhle**

DS note: Flow result: module3_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "517fabac-611c-4dd3-b40c-0d93cac2177a", x: 26280, y: 792} -->

Colombia has one time zone, Colombia Time (COT), which is located in the **UTC−05:00** zone, 5 hours behind Coordinated Universal Time (UTC)

<!-- { section: "4334ee70-640b-495f-8c79-55c545ca836c", x: 24, y: -72} -->

```stack
card Message1 do
  write_result("module3_started", "yes")
  then(Message_2)
end

```

<!-- { section: "054d1038-17af-4547-b368-686d83ed7731", x: 4440, y: 72} -->

```stack
card Message7 do
  write_result("module3_social_support", "@ref_message_7")
  then(Message_8)
end

```

<!-- { section: "de6ac514-c5ff-401b-8b3b-c5a70709e72b", x: 22296, y: 240} -->

```stack
card Message26 do
  write_result("module3_social_support2", "@ref_message_26")
  then(Message_27)
end

```

<!-- { section: "9bbecfb1-b192-4f0a-b5d2-ff00c3bf7f3c", x: 26280, y: 264} -->

```stack
card ModuleCompleted do
  log("Module 3 Complete")
  write_result("module3_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "d4ad4987-f917-48fb-884b-a5f80dee23e8", x: 1104, y: -48} -->

```stack
card Message2_1 do
  write_result("module3_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "3223a8f1-41fa-4080-bd6f-b1899f2740a5", x: 1104, y: 288} -->

```stack
card Message2_2 do
  write_result("module3_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "57c6f3f2-10bf-44ba-9fee-8438ef0433f9", x: 7272, y: -72} -->

```stack
card Message12_1 do
  write_result("module3_beliefs", "a")
  then(Message_13_1)
end

```

<!-- { section: "fa5072af-2e36-4237-9234-50d667f51ebd", x: 7296, y: 288} -->

```stack
card Message12_2 do
  write_result("module3_beliefs", "b")
  then(Message_13_2)
end

```

<!-- { section: "a0a2f947-453e-41c7-99f1-d9d9d3afed52", x: 7296, y: 648} -->

```stack
card Message12_3 do
  write_result("module3_beliefs", "c")
  then(Message_13_3)
end

```

<!-- { section: "90e74bb2-55d5-4122-8977-da9c9b2debfa", x: 10752, y: 408} -->

```stack
card Message15 do
  write_result("module3_opinion", "@ref_message_15")
  then(Message_16)
end

```

<!-- { section: "846c3692-3bc2-47bc-a6f0-d98d64132454", x: 12432, y: 120} -->

```stack
card Message17_1 do
  write_result("module3_attitudes", "a")
  then(Message_18_1)
end

```

<!-- { section: "3bb72293-e59a-4af9-beaa-4101176e33ba", x: 12456, y: 456} -->

```stack
card Message17_2 do
  write_result("module3_attitudes", "b")
  then(Message_18_2)
end

```

<!-- { section: "56e65e14-3f5e-4a08-8992-0a6bb08bb827", x: 12456, y: 792} -->

```stack
card Message17_3 do
  write_result("module3_attitudes", "c")
  then(Message_18_3)
end

```

<!-- { section: "a80eb0fd-1e59-43d6-a874-adb7f5f335ea", x: 12480, y: 1128} -->

```stack
card Message17_4 do
  write_result("module3_attitudes", "d")
  then(Message_18_4)
end

```

<!-- { section: "784808de-a678-4a25-86fb-c350e3638207", x: 16488, y: -144} -->

```stack
card Message19_1 do
  write_result("module3_social_norms", "a")
  then(Message_20)
end

```

<!-- { section: "c76103ea-7cd5-44b6-a574-705ac2dfc10b", x: 16512, y: 216} -->

```stack
card Message19_2 do
  write_result("module3_social_norms", "b")
  then(Message_20)
end

```

<!-- { section: "90e6167b-16ea-4a0c-8130-66cfe1718f8f", x: 16536, y: 624} -->

```stack
card Message19_3 do
  write_result("module3_social_norms", "c")
  then(Message_20)
end

```

<!-- { section: "001944a9-0fc0-4190-991d-f2e93a107303", x: 23352, y: 72} -->

```stack
card Message27_1 do
  write_result("module3_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "0f114d2d-9d09-4714-83be-099ef3f82a73", x: 23352, y: 384} -->

```stack
card Message27_2 do
  write_result("module3_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "f70e8f4b-cc9f-49d1-8224-cb729c9064be", x: 23352, y: 744} -->

```stack
card Message27_3 do
  write_result("module3_behavioral_activation", "c")
  then(Safe_Guarding_1)
end

```

<!-- { section: "7297b375-cdbd-46ae-941b-d61bc0f8aded", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```

<!-- { section: "INTERACTION_TIMEOUT_CELL", x: 0, y: 0} -->

```stack
interaction_timeout(300)

```
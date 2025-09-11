<!-- { section: "e500e27a-ffca-42df-a392-b3e2a61676b3", x: -1224, y: 0} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_g1")

```

<!-- { section: "cd9cdf0b-ffca-4967-b7ad-b6e73df53e76", x: -744, y: 96} -->

```stack
card Branch_450f80, "Branch_450f80",
  version: "1",
  uuid: "16e01661-171b-560c-aaeb-2dbb9c083fb7",
  code_generator: "CONDITIONALS" do
  then(Message_1 when contact.onboarding_complete == true and contact.arm == "GAMIFIED")
  then(RunStack_e94a5d when contact.onboarding_complete == false and contact.arm == "NARRATIVE")
  then(RunStack_126216 when contact.onboarding_complete == true and contact.arm == "NARRATIVE")
  then(RunStack_31c610)
end

```

<!-- { section: "2276bfc0-ec7d-4057-9967-3e57c631cbeb", x: -120, y: -24} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Hola!* 👋
Hoy escucharemos el primer episodio del podcast de Pilar y Mari. Este primer episodio y todos los que vienen están divididos en tres partes"
  )

  then(Message1)
end

```

<!-- { section: "87aa5e5f-4261-4c62-a817-5d0d9fabd8a0", x: 984, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["¡Cuéntame más! "]) do
      text("Este podcast también es un reto 🎯 ")
    end

  then(Message_3 when ref_Message_2 == "¡Cuéntame más! ")
  then(Catch_all_1)
end

```

<!-- { section: "b2bab305-e884-495a-8f5d-db1dde984952", x: 1008, y: -456} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "ab9abeab-0c66-4975-98d7-2eeab25e959a", x: 1464, y: 24} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¿Alguna vez has querido tener el sticker perfecto que haga reir a todas tus amigas o que te pueda sacar de una situación incómoda?"
  )

  then(Message_4)
end

```

<!-- { section: "b74db51d-562c-4a4f-b2e4-fc705408c492", x: 1944, y: 24} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["¡Genial!"]) do
      text(
        "Pilar y Mari te harán preguntas después de cada parte del episodio para saber tu opinión. Si respondes las preguntas, te mandaremos stickers divertidos al final del episodio. No hay respuestas correctas o incorrectas, sólo queremos saber qué opinas."
      )
    end

  then(Message_5 when ref_Message_4 == "¡Genial!")
  then(Catch_all_2)
end

```

<!-- { section: "e68047c4-bf15-4db0-b44d-5af99077c7c4", x: 1944, y: -480} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "2938bf34-f30f-4ee4-ac43-b03c0ec15ef6", x: 2688, y: 0} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["¡Entendido! 🫡 "]) do
      text(
        "¡Mientras más capítulos escuches, más stickers puedes ganar! ¡Trata de no romper tu racha!"
      )
    end

  then(Message_6 when ref_Message_5 == "¡Entendido! 🫡 ")
  then(Catch_all_3)
end

```

<!-- { section: "e883f0c1-3671-49cc-bc58-fa68acce6177", x: 2688, y: -504} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_5)
end

```

<!-- { section: "65af6e00-6285-46cc-ae59-f6a5a2b439df", x: 3384, y: 0} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Ahora, vas a escuchar el primer episodio del podcast de Pilar y Mari en el que hablarán sobre las relaciones sanas y tóxicas ☠️. Recuerda que si hay algo de lo que hablan Pilar y Mar o alguna pregunta te llega a hacer sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Lo más importante es que te sientas bien!"
  )

  then(Message_7)
end

```

<!-- { section: "e4544268-c57c-4518-8a56-59467f8efee4", x: 3864, y: 0} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "MEDIA_AUDIO" do
  audio("5a6c3a84-5ba9-4c08-8a08-63d1e12ff180-G_M1_P1.mp3")
  then(Message_8)
end

```

<!-- { section: "1a3f2585-7e0c-45a9-9078-f7517984b7c1", x: 4416, y: 0} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_9 when ref_Message_8 == "Ya escuché el audio")
  then(Catch_all_4)
end

```

<!-- { section: "1e68690b-a708-4d76-b656-33b2ef523255", x: 4512, y: -576} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_8)
end

```

<!-- { section: "1beeeda3-c4d4-4776-82fb-0acc4ebfad31", x: 4848, y: 0} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "¿Qué opinas de lo que comentan Pilar y Mar? ¿Crees que si alguien te busca todo el tiempo y te llama muy seguido es tierno o una forma de control? 🧐 *Puedes responder usando texto o notas de voz*"
    )

  then(Branch_e77c62)
end

```

<!-- { section: "c041e2ff-8736-49df-a012-4804a87331b7", x: 6168, y: 24} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Sigue el podcast 🎧"]) do
      text("Gracias por tu respuesta ✨")
    end

  then(Message_11 when ref_Message_10 == "Sigue el podcast 🎧")
  then(Catch_all_5)
end

```

<!-- { section: "515d9d2d-ac70-441c-b46c-090031e7be7d", x: 6072, y: -552} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "6fda981f-3bcb-43f3-9480-ccd3959fded7", x: 7056, y: 0} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_12 when ref_Message_11_1 == "Ya escuché el audio")
  then(Catch_all_6)
end

```

<!-- { section: "ad183fb4-628f-4345-9441-ecfda2ba5223", x: 7032, y: -600} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11_1)
end

```

<!-- { section: "d8181708-8070-4ce2-875e-e6610c509abd", x: 7632, y: 0} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["La está cuidando 💖", "No estoy segura 😕", "Es posesivo 🚫"]) do
      text(
        "Ya sabes que el novio de Mari estaba muy pendiente, él no solo le preguntaba dónde estaba sino que le pedía que *siempre* que saliera le enviara su ubicación 📍 

Él siempre quería saber dónde y con quién estaba y le decía a Mari que es porque se preocupaba por ella todo el tiempo…

¿Qué piensas que quiere decir esto? 🤔"
      )
    end

  then(Message12_1 when ref_Message_12 == "La está cuidando 💖")
  then(Message12_2 when ref_Message_12 == "No estoy segura 😕")
  then(Message12_3 when ref_Message_12 == "Es posesivo 🚫")
  then(Catch_all_7)
end

```

<!-- { section: "6831d50d-18b9-4249-8cc7-722286ecb7aa", x: 7680, y: -624} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "ecc15e5a-9061-4f31-9a34-a43187249fec", x: 8760, y: -72} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "MEDIA_AUDIO" do
  audio("c325854b-4cb1-43c7-874c-5ba33de6c6b6-G_M1_P2_R1.mp3")
  then(Message_13_4)
end

```

<!-- { section: "6077daf5-5db3-4c92-b340-265f91c35f08", x: 8760, y: 384} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "MEDIA_AUDIO" do
  audio("3119dbda-7546-4207-b85c-e5db2c188d7c-G_M1_P2_R2.mp3")
  then(Message_13_4)
end

```

<!-- { section: "93231c60-b050-41b9-a11c-a4fcded44440", x: 8736, y: 960} -->

```stack
card Message_13_3, "Message_13_3",
  version: "1",
  uuid: "d0b53090-c491-560e-9fdb-e2ba5b1436df",
  code_generator: "MEDIA_AUDIO" do
  audio("384cec0b-5ab1-4607-9b7c-65d59f69fbc5-G_M1_P2_R3.mp3")
  then(Message_13_4)
end

```

<!-- { section: "870d6079-0d3c-48a8-b14d-29a3e791bd27", x: 9312, y: 432} -->

```stack
card Message_13_4, "Message_13_4",
  version: "1",
  uuid: "65160d77-1092-5a41-8782-0fe572156b17",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13_4 =
    buttons(["Sigue el podcast 🎧"]) do
      text("Cuando termine el audio, pulsa el botón *Sigue el podcast* 🎧")
    end

  then(Message_14_1 when ref_Message_13_4 == "Sigue el podcast 🎧")
  then(Catch_all_10)
end

```

<!-- { section: "2a84bb8e-5b3c-42c2-a2d2-d0a62e662bfc", x: 9360, y: -216} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13_4)
end

```

<!-- { section: "03773d18-57e0-46d0-a2f5-5c802aa253d2", x: 10320, y: 456} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_15 when ref_Message_14 == "Ya escuché el audio!")
  then(Catch_all_11)
end

```

<!-- { section: "87ef8283-7544-4467-ac45-160c4b35b2d7", x: 9864, y: -744} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "abba95db-ba27-4078-b701-8744ca1bcd90", x: 10872, y: 456} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "LIST" do
  ref_Message_15 =
    list("List", [
      "Respondería rápido📱",
      "No contesto🚫",
      "No sé qué haría 🤷",
      "Seguro te quiere",
      "Eso no está bien"
    ]) do
      text(
        "Imagina que la pareja de Mari también se molestaba cuando no ella no le respondía rápido los mensajes😠

¿Qué crees que harías tú si estuvieras en esa situación?"
      )
    end

  then(Message15_1 when ref_Message_15 == "Respondería rápido📱")
  then(Message15_2 when ref_Message_15 == "No contesto🚫")
  then(Message15_3 when ref_Message_15 == "No sé qué haría 🤷")
  then(Message15_4 when ref_Message_15 == "Seguro te quiere")
  then(Message15_5 when ref_Message_15 == "Eso no está bien")
  then(Catch_all_12)
end

```

<!-- { section: "49e2a5f0-46b4-4d0d-a8a1-7683f3ebd6cc", x: 10800, y: -720} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "1306c978-e401-490a-9faf-38c364e771fe", x: 13296, y: -336} -->

```stack
card Message_16_1, "Message_16_1",
  version: "1",
  uuid: "79d2db01-2ced-5381-8796-6f1fb81d9335",
  code_generator: "MEDIA_AUDIO" do
  audio("e9db78b8-d77f-484d-aeda-86273cf660ef-G_M1_P3_R1.mp3")
  then(Message_16_6)
end

```

<!-- { section: "595bae02-290d-4567-bfb7-fbeaa43fc708", x: 13320, y: 288} -->

```stack
card Message_16_2, "Message_16_2",
  version: "1",
  uuid: "4736c50d-9290-5ad0-8477-a21bde650bf8",
  code_generator: "MEDIA_AUDIO" do
  audio("13ecc55d-6b98-47f7-beb4-e8401395730f-G_M1_P3_R2.mp3")
  then(Message_16_6)
end

```

<!-- { section: "82da0f85-cf78-44cf-b1d5-e10d81fbfc37", x: 13320, y: 960} -->

```stack
card Message_16_3, "Message_16_3",
  version: "1",
  uuid: "b029a349-f1f2-5b23-a667-1ceb422da17a",
  code_generator: "MEDIA_AUDIO" do
  audio("e1b17da7-d860-4deb-a8e2-f8aa4bf1583f-G_M1_P3_R3.mp3")
  then(Message_16_6)
end

```

<!-- { section: "df827586-0674-4164-b5b0-a0fe5ba331a1", x: 13272, y: 1584} -->

```stack
card Message_16_4, "Message_16_4",
  version: "1",
  uuid: "070024d6-0908-53d4-8e7d-77e555ebfa9f",
  code_generator: "MEDIA_AUDIO" do
  audio("00ccb948-2de0-44f8-868d-a3f258d80756-G_M1_P3_R4.mp3")
  then(Message_16_6)
end

```

<!-- { section: "faea924a-5106-4112-b567-d5b3b656b336", x: 13248, y: 2400} -->

```stack
card Message_16_5, "Message_16_5",
  version: "1",
  uuid: "5a55a5eb-0a1d-510d-a0db-32beae1c2aa6",
  code_generator: "MEDIA_AUDIO" do
  audio("e563c175-1cb3-4776-9075-4448857a98f7-G_M1_P3_R5.mp3")
  then(Message_16_6)
end

```

<!-- { section: "188ca741-11f9-431a-a802-4a5f2d346c35", x: 13104, y: -960} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "44d2d3be-bafe-4ad7-a4dc-bf6967677eee", x: 13992, y: 912} -->

```stack
card Message_16_6, "Message_16_6",
  version: "1",
  uuid: "d610c451-a0ff-56f4-aff5-faab09313ca9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_6 =
    buttons(["Sigue el podcast 🎧"]) do
      text("Cuando termine el audio, pulsa el botón *Sigue el podcast* 🎧")
    end

  then(Message_17_1 when ref_Message_16_6 == "Sigue el podcast 🎧")
  then(Catch_all_15)
end

```

<!-- { section: "08c81c00-7dcb-4dfc-82ff-d7f61a022afa", x: 14256, y: 240} -->

```stack
card Catch_all_15, "Catch_all_15",
  version: "1",
  uuid: "4bee0862-bdcd-5844-8df1-4816d420e326",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16_6)
end

```

<!-- { section: "65a46551-f5df-46d6-a9d3-12ffe5cbea9e", x: 12840, y: 1320} -->

```stack
card Catch_all_16, "Catch_all_16",
  version: "1",
  uuid: "d4296a10-0d55-5756-9088-6b503693c13b",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "3ec14d5e-cb68-4443-8451-97cc8cf9df5c", x: 12840, y: 2184} -->

```stack
card Catch_all_17, "Catch_all_17",
  version: "1",
  uuid: "209ee976-ac39-5434-95b8-eaa8c2de1f85",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "2aac5218-47cf-4d68-a0f7-bf56d0b567f0", x: 15096, y: 1032} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_18 when ref_Message_17 == "Ya escuché el audio!")
  then(Catch_all_18)
end

```

<!-- { section: "c1dc1c8d-8b6e-43ed-b56d-bb7facae5cd7", x: 14568, y: 1008} -->

```stack
card Message_17_1, "Message_17_1",
  version: "1",
  uuid: "5277b1d8-b73e-5457-b6fc-a3e93bef9c08",
  code_generator: "MEDIA_AUDIO" do
  audio("ef520081-0c72-4e36-93f2-95efa4298a43-G_M1_P4.mp3")
  then(Message_17)
end

```

<!-- { section: "5afd3c1f-9de4-4213-a147-e438fd8e7ce0", x: 9840, y: 480} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "MEDIA_AUDIO" do
  audio("61311100-8044-492c-b62a-8778160518bf-G_M1_P3.mp3")
  then(Message_14)
end

```

<!-- { section: "ace96302-702d-4065-bac6-f3cf0ab20858", x: 15048, y: 264} -->

```stack
card Catch_all_18, "Catch_all_18",
  version: "1",
  uuid: "e1b87782-5fd0-51c8-b25e-fa1a45e4e585",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_17)
end

```

<!-- { section: "4a474414-51ae-4eec-a34e-2609a7cf408e", x: 15720, y: 1032} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Dáselas 📱", "¡No! Es privado 🗣️", "No sé 🤷"]) do
      text(
        "Siguiendo con el tema de los celos, ¿Qué le dirías a una amiga si su novio le insistiera que le dé las contraseñas y usuarios de todas sus redes?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Dáselas 📱")
  then(Message18_2 when ref_Message_18 == "¡No! Es privado 🗣️")
  then(Message18_3 when ref_Message_18 == "No sé 🤷")
  then(Catch_all_19)
end

```

<!-- { section: "5e6c40ba-fecf-45a2-9d99-d80dab830650", x: 15720, y: 240} -->

```stack
card Catch_all_19, "Catch_all_19",
  version: "1",
  uuid: "aa2b872e-9152-5c35-9ece-d9c72a2f6ea0",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18)
end

```

<!-- { section: "f3c4398e-91df-4324-9ea8-bc900bcd8199", x: 17448, y: 1008} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Tus redes sociales son parte de tu vida privada y solo tú puedes decidir si te sientes cómoda compartiéndolas. Algo en qué pensar es que quien tenga acceso a tus redes tiene mucho poder sobre ti -- tiene toda tu información y puede mandar mensajes a tu nombre. 

¿A tu amiga le insisten? ¿Se siente presionada de dar las contraseñas? Si es así, puede ser una señal de alerta de que es controlador, no protector 🚫"
  )

  then(Message_20)
end

```

<!-- { section: "ca33c39a-a14d-4e78-ac2a-d2e6560f0a30", x: 18528, y: 1008} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["Quiero mis stickers"]) do
      text(
        "¡Muy bien! Has llegado al final del primer capítulo del podcast 🥳

¡Para celebrar, tengo unos stickers buenísimos sobre este tema y que puedes usar si llegas a vivir algo similar! "
      )
    end

  then(Sticker_1 when ref_Message_20 == "Quiero mis stickers")
  then(Catch_all_20)
end

```

<!-- { section: "2fc95efe-9e26-4f54-9a45-ba1215c987ed", x: 18576, y: 120} -->

```stack
card Catch_all_20, "Catch_all_20",
  version: "1",
  uuid: "33422d10-445d-5f76-96c9-e793d4011333",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_20)
end

```

<!-- { section: "8572dc46-09ef-4a94-b7fa-502fd4480b90", x: 19920, y: 912} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["¡Entendido!  🫡"]) do
      text(
        "¡Ya completaste el día 1 de 6 en el reto del podcast! Sigue así y completa una racha perfecta 🤩"
      )
    end

  then(Message_23 when ref_Message_22 == "¡Entendido!  🫡")
  then(Catch_all_21)
end

```

<!-- { section: "5ccd1790-304f-4010-8bb2-4927ac0d877a", x: 20064, y: 288} -->

```stack
card Catch_all_21, "Catch_all_21",
  version: "1",
  uuid: "317ddc77-c862-5558-91a3-6d411d930f0a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_22)
end

```

<!-- { section: "6eafadfa-5924-41f1-8c32-223138d0e8c4", x: 20400, y: 936} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "QUESTION" do
  ref_Message_23 =
    ask(
      "¿Crees que aprendiste algo nuevo hoy? Cuéntanos brevemente qué aprendiste. Recuerda que puedes responder usando texto o notas de voz"
    )

  then(Branch_2da197)
end

```

<!-- { section: "49069749-bab0-4fdb-a5a6-d14e92f0a72e", x: 21768, y: 1008} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["Amigas 👯‍♀️", "Mamá 👩‍👧", "Familia 💗"]) do
      text(
        "Ahora te voy a dejar un reto: Para mañana, charla con alguien sobre este tema y pregúntale qué opina. ¿Con quién quieres hablar?"
      )
    end

  then(Message24_1 when ref_Message_24 == "Amigas 👯‍♀️")
  then(Message24_2 when ref_Message_24 == "Mamá 👩‍👧")
  then(Message24_3 when ref_Message_24 == "Familia 💗")
  then(Catch_all_22)
end

```

<!-- { section: "3786712b-de87-47f8-9ff5-c1999d663a40", x: 21672, y: 120} -->

```stack
card Catch_all_22, "Catch_all_22",
  version: "1",
  uuid: "d726a2f0-f36b-5c79-a2fc-f33706cb5037",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_24)
end

```

<!-- { section: "c5ef04a3-cfa8-4233-b4fe-77bdb9ecdf52", x: 24192, y: 1128} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Entendido 🌸"]) do
      text(
        "Ok amiga, esto fue todo por hoy. ¡Prepárate porque el episodio de mañana va a estar increíble! Hablaremos sobre qué podríamos hacer para sentirnos mejor con nosotras mismas💖"
      )
    end

  then(Message_26 when ref_Message_25 == "Entendido 🌸")
  then(Catch_all_23)
end

```

<!-- { section: "aafb9e5f-c001-412a-9f06-6fec9e3fc21b", x: 23448, y: -120} -->

```stack
card Catch_all_23, "Catch_all_23",
  version: "1",
  uuid: "83142d06-58d1-5ed3-a212-b36817b976a4",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_25)
end

```

<!-- { section: "566b200c-6f94-417a-9f9b-4df63e39401c", x: 24744, y: 1176} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_41d474)
end

```

<!-- { section: "c74aca8d-c024-4755-900b-ff1fcca4bfa2", x: -288, y: 912} -->

```stack
card RunStack_31c610, "RunStack_31c610",
  version: "1",
  uuid: "6bfaba9d-cae9-5888-a202-1b046a377fe0",
  code_generator: "RUN_STACK" do
  run_stack("0450f64f-6f36-47c2-a5b0-1d9067ededd2")
end

```

<!-- { section: "14a11d10-1e86-4f72-8210-9e51a4a38eda", x: -72, y: 432} -->

```stack
card RunStack_e94a5d, "RunStack_e94a5d",
  version: "1",
  uuid: "52ed248d-68f6-5a0b-83ac-45d6f9ac3396",
  code_generator: "RUN_STACK" do
  run_stack("25065e06-6925-498c-a343-fe13ae776b81")
end

```

<!-- { section: "31391d97-016a-483e-a495-ffc599675f3e", x: -120, y: 648} -->

```stack
card RunStack_126216, "RunStack_126216",
  version: "1",
  uuid: "d97031dd-3f8e-5c83-a22a-aac11c9093bb",
  code_generator: "RUN_STACK" do
  run_stack("e2e7954a-ab0b-454e-b1fb-ccf0f307afbe")
end

```

<!-- { section: "ea69b48c-1363-4f93-a310-051479222220", x: 25272, y: 1104} -->

```stack
card Profile_41d474, "Profile_41d474",
  version: "1",
  uuid: "8c5e959e-69a6-5179-b5af-b4c4e2985587",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_1")
  then(ModuleCompleted)
end

```

<!-- { section: "fa136558-3655-4783-a04c-50b452b5d28a", x: 19152, y: 624} -->

```stack
card Sticker_1, "Sticker_1",
  version: "1",
  uuid: "3283a246-16cd-504a-96ee-b8f6f3e8ed44",
  code_generator: "MEDIA_IMAGE" do
  image("73eccf30-2d6d-447e-bd41-d83a3ff4e9f4-Modulo1__Ubi-Copy.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "75593444-696e-474b-b8c6-4ccd44dd2727", x: 19200, y: 1056} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("f0c4e277-3e7d-4724-b7fc-73fbc8801fe8-Modulo1_DateCuenta-Copy.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "8df9ed72-9b8a-43c5-b796-ce09526dacf1", x: 19200, y: 1560} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("38eae162-3ef5-4411-ad6d-fbb68adbfa73-Modulo1_DejaDeLlamarme-Copy.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "e007a5f6-c747-4df0-96a1-102dc249bb83", x: 19248, y: 2088} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("48252c20-b4f3-4e60-aed7-6a3a0930b86d-Modulo1_Ewww-Copy.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "e9e75c83-cf7c-43b2-a6f4-02fbeff0e4d7", x: 19736, y: 2088} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("cee1147b-3dc1-45f2-828a-38cc4f89be0b-Modulo1_Limites-Copy.webp")
  text("")
  then(Message_22)
end

```

<!-- { section: "ab7add5e-ce81-43a6-bfd2-4388dcbd9c8e", x: 6624, y: 72} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "MEDIA_AUDIO" do
  audio("b7d784aa-3f2c-4a1d-9550-0f1ea692843f-G_M1_P2.mp3")
  then(Message_11_1)
end

```

<!-- { section: "dfa77ec6-60f7-4034-a34c-344b057c75c4", x: 23064, y: 1104} -->

```stack
card Message_1_25, "Message_1_25",
  version: "1",
  uuid: "48339b01-516f-5120-bd83-e8820cefd267",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¿Crees que estás pasando por una situación similar de la que hablamos hoy y necesitas ayuda? Aquí tienes líneas de apoyo confidenciales para hablar o reportar tu caso:"
  )

  then(Message_2_25)
end

```

<!-- { section: "54705e90-f27f-402a-992e-0840778a21c0", x: 23544, y: 1104} -->

```stack
card Message_2_25, "Message_2_25",
  version: "1",
  uuid: "b6f63875-a1fa-5a86-8a82-53010e59756c",
  code_generator: "TEXT_MESSAGE" do
  text(
    "1. Línea Púrpura (WhatsApp): +57 300 7551846 o *Visita aquí* : https://www.sdmujer.gov.co/nuestros-servicios/servicios-para-las-mujeres/linea-purpura
2. Línea 141 (ICBF) – Atención 24/7
3. Reporte en Línea: *Te Protejo*: https://teprotejocolombia.org/"
  )

  then(Message_25)
end

```

<!-- { section: "b17aced8-05ad-4c88-a382-1130a5f4e698", x: 5256, y: 0} -->

```stack
card Branch_e77c62, "Branch_e77c62",
  version: "1",
  uuid: "e4862c15-914b-5f99-8a11-9b6df0edfba8",
  code_generator: "CONDITIONALS" do
  then(Message9 when event.message.type == "audio")
  then(Message9 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "26c745dc-9c1c-49a4-a3bd-ada0177c569f", x: 5256, y: 480} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_9)
end

```

<!-- { section: "5efbf47e-4198-4eab-bc52-caeec16cf8d0", x: 20832, y: 1008} -->

```stack
card Branch_2da197, "Branch_2da197",
  version: "1",
  uuid: "6212fcfe-7853-561a-aa1e-9e496030a929",
  code_generator: "CONDITIONALS" do
  then(Message23 when event.message.type == "audio")
  then(Message23 when event.message.type == "text")
  then(Catch_all_2_2)
end

```

<!-- { section: "4030253c-3edc-4d6d-9807-69091e942003", x: 20376, y: 1488} -->

```stack
card Catch_all_2_2, "Catch_all_2_2",
  version: "1",
  uuid: "86031531-4763-5dde-ab3c-b02fc964194a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_23)
end

```

<!-- { section: "035a3237-233c-4920-bf8d-3d7b6407ef6c", x: 2712, y: 312} -->

Emoji does not show up

<!-- { section: "d3dd3f07-ce9b-413b-a655-19d0515304b8", x: 5856, y: 384} -->

**@Buhle**

Save user response here
DS note: Flow result: module1_boundaries {user input}

<!-- { section: "a58ffe08-5d20-4f4b-80f8-8736383278ee", x: 21144, y: 1368} -->

**@Buhle**

Save insight here, I added a code block below in case you need it

DS note: Flow result: module1_learnings {user input}

<!-- { section: "85721a5c-550d-4821-8005-c3d4b8e2f408", x: 25608, y: 1608} -->

**@Buhle**

schedule follow up - post module 1 gamified flow eng

Schedule Quiz post module 1 to start next day (6pm)

Update contact.next_engagement_time

<!-- { section: "fe51536d-5e8e-4080-a88c-3878de3a04f6", x: 11040, y: 1272} -->

**@Buhle**

Save insights here

<!-- { section: "060e0776-a2ab-43b2-a011-582e45c35981", x: 456, y: 552} -->

**@Buhle**

DS note: Flow result: module1_started (yes)

I think this is a code block, added one below

<!-- { section: "0df66d9c-328f-4ff1-94ba-40cac8980927", x: 8160, y: 1104} -->

**@Buhle**

Save user insights here

<!-- { section: "9bf6a708-e9c5-475c-a1cf-95b8c34ced1e", x: 22104, y: 1392} -->

**@Buhle**

Save insight here

<!-- { section: "baccb8fa-be7f-4d51-8494-c0b85ce25d1b", x: 24816, y: 1560} -->

**@Buhle**

DS note: Flow result: Flow result: module1_completed (yes)

<!-- { section: "cb943697-aca3-460f-9123-00e043989010", x: 23496, y: 1464} -->

Add a hyperlink over the bolded words: 1. **Visita aquí**: [https://www.sdmujer.gov.co/nuestros-servicios/servicios-para-las-mujeres/linea-purpura](https://www.sdmujer.gov.co/nuestros-servicios/servicios-para-las-mujeres/linea-purpura)3.**Te protejo:** [https://teprotejocolombia.org/](https://teprotejocolombia.org/)

<!-- { section: "750f568b-4881-450b-83cd-894b9484d3a2", x: 8592, y: -312} -->

As of 07/07 this audio file is not working, I have reuploaded it on 08/07 missing here. Why did this all of a sudden stop working

<!-- { section: "b7d6d7a4-eac5-4940-b5bc-c0c4aa8fc28e", x: 15792, y: 1560} -->

old: Siguiendo con el tema de los celos, ¿Qué le dirías a una amiga si su novio, como Camilo, le insistiera que le dé las contraseñas y usuarios de todas sus redes?

<!-- { section: "bc4729dd-cd5d-4e16-80b6-e894a0cf61d4", x: 432, y: -48} -->

```stack
card Message1 do
  write_result("module1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "7b2eec68-df28-4e6d-80da-1b1a8bd7a63c", x: 21240, y: 1008} -->

```stack
card Message23 do
  log("Saving message 23 response")
  write_result("module1_learnings", "@ref_message_23")
  then(Message_24)
end

```

<!-- { section: "c706f8d2-5ab3-498c-bcf3-9d2a942785e2", x: 25848, y: 1152} -->

```stack
card ModuleCompleted do
  log("Module 1 Complete")
  write_result("module1_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "29b90f2d-694a-404f-81f1-c30f2b3f53ca", x: 5664, y: 0} -->

```stack
card Message9 do
  log("Saving message 9 response")
  write_result("module1_boundaries", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "76981e5a-2fe2-4067-aed9-21aa4ba22946", x: 8136, y: -96} -->

```stack
card Message12_1 do
  write_result("module1_beliefs", "a")
  then(Message_13_1)
end

```

<!-- { section: "5681dad5-dbfd-4d2f-87cb-8fc6663cf607", x: 8136, y: 336} -->

```stack
card Message12_2 do
  write_result("module1_beliefs", "b")
  then(Message_13_2)
end

```

<!-- { section: "c5d945bd-b4ce-4341-b05d-e64acf946547", x: 8136, y: 672} -->

```stack
card Message12_3 do
  write_result("module1_beliefs", "c")
  then(Message_13_3)
end

```

<!-- { section: "88f68462-05ba-4beb-b795-00fec7a8d0d7", x: 11448, y: 192} -->

```stack
card Message15_1 do
  write_result("module1_attitudes1", "a")
  then(Message_16_1)
end

```

<!-- { section: "f24cee4f-b991-4f1e-bdeb-81fb882f56b3", x: 11448, y: 504} -->

```stack
card Message15_2 do
  write_result("module1_attitudes1", "b")
  then(Message_16_2)
end

```

<!-- { section: "7ae5555e-069c-4972-9d7c-d3d0f1a9ec67", x: 11448, y: 816} -->

```stack
card Message15_3 do
  write_result("module1_attitudes1", "c")
  then(Message_16_3)
end

```

<!-- { section: "3bf8c21f-afbc-4c5d-bbdf-f795e5e8b4cf", x: 11448, y: 1128} -->

```stack
card Message15_4 do
  write_result("module1_attitudes1", "d")
  then(Message_16_4)
end

```

<!-- { section: "1509c32d-e178-41ff-908d-f3cc1ede7f25", x: 11448, y: 1440} -->

```stack
card Message15_5 do
  write_result("module1_attitudes1", "e")
  then(Message_16_5)
end

```

<!-- { section: "3199aa00-5ea7-44dd-acad-4e99528cc68d", x: 16536, y: 816} -->

```stack
card Message18_1 do
  write_result("module1_attitudes2", "a")
  then(Message_19)
end

```

<!-- { section: "d4a75852-1108-4066-8257-03dff68cb43c", x: 16536, y: 1152} -->

```stack
card Message18_2 do
  write_result("module1_attitudes2", "b")
  then(Message_19)
end

```

<!-- { section: "2a98266a-94a8-4b4e-b233-fbf85223ee22", x: 16536, y: 1464} -->

```stack
card Message18_3 do
  write_result("module1_attitudes2", "c")
  then(Message_19)
end

```

<!-- { section: "a54a7177-f8a4-4d5a-8d42-b48bbc28d6b2", x: 22392, y: 1008} -->

```stack
card Message24_2 do
  write_result("module1_behavioral_activation", "b")
  then(Message_1_25)
end

```

<!-- { section: "68251139-25e2-4dc1-a187-6f55fa957298", x: 22392, y: 696} -->

```stack
card Message24_1 do
  write_result("module1_behavioral_activation", "a")
  then(Message_1_25)
end

```

<!-- { section: "8e88675e-78df-462f-aa2a-e2bbe47ac448", x: 22392, y: 1320} -->

```stack
card Message24_3 do
  write_result("module1_behavioral_activation", "c")
  then(Message_1_25)
end

```

<!-- { section: "b57e1e1a-5905-4821-8742-d7e4d8aa264e", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```

<!-- { section: "INTERACTION_TIMEOUT_CELL", x: 0, y: 0} -->

```stack
interaction_timeout(300)

```
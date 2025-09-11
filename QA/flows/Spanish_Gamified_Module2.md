<!-- { section: "e34d37df-c7c5-4551-9c4b-205e766e0df3", x: -1488, y: -24} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_only_phrase(event.message.text.body, "test_g2_2") or
       (contact.contact_module == "MODULE_1" and contact.arm == "GAMIFIED" and
          contact.onboarding_complete == true and contact.quiz_post_module1_complete == true)

```

<!-- { section: "538044a6-0f61-4589-b8d9-1e71086cc225", x: -336, y: -24} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Listo, vamos a empezar con el segundo episodio del podcast de Pilar y Mari. ¡Ya nos vamos conociendo mejor!"
  )

  then(Message1)
end

```

<!-- { section: "f2c400d6-7d11-4ab7-8cf6-ba560cff6daf", x: 672, y: 24} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "Súper bien 👍"]) do
      text(
        "El reto de ayer era conversar con alguien de confiaza acerca de las relaciones sanas o tóxicas ¿Cómo te fue con el reto de ayer?"
      )
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "Súper bien 👍")
  then(Catch_all_1)
end

```

<!-- { section: "83b2eb67-ad4c-4df6-9e76-199a0b4e4c21", x: 984, y: -864} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "f65d2a8b-1aa2-47c7-afaa-37396a102911", x: 1824, y: -120} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "No te preocupes, todavía hay tiempo para hacerlo. ¡Es importante empezar a crear tu red apoyo!"
  )

  then(Message_4)
end

```

<!-- { section: "a601a0b2-6bab-4183-ab8b-1ec6dc7927c6", x: 1848, y: 384} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text("Increíble, ¡Es importante empezar a crear tu red apoyo!")
  then(Message_4)
end

```

<!-- { section: "478a1637-6794-45ec-9a2b-678715bda6ad", x: 2424, y: 120} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Vale 👍"]) do
      text("Además, recuerda que, entre más larga tu racha, ¡más stickers vas acumulando!")
    end

  then(Message_5 when ref_Message_4 == "Vale 👍")
  then(Catch_all_2)
end

```

<!-- { section: "98e910c6-5db8-453c-aeaa-42332c87747c", x: 2280, y: -696} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "62b04e66-01d0-4f28-bcd4-fbd9be815555", x: 3072, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este segundo episodio. Pilar y Mari hablarán sobre qué podríamos hacer para sentirnos mejor con nosotras mismas 💖"
  )

  then(Message_6)
end

```

<!-- { section: "a38a47af-fbaf-4ce9-9052-c9240d2c6e16", x: 3768, y: 120} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Acuérdate que si, hay algo de lo que hablan Pilar y Mari o alguna pregunta te llega a hacer sentir incómoda, puedes parar y volver te sientas lista. ¡Para mí es muy importante que te sientas bien!🫰"
      )
    end

  then(Message_8 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "1ca16e72-3f2c-4b6b-8a03-5cf5b63a3727", x: 3768, y: -792} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6)
end

```

<!-- { section: "fef24006-78f9-4210-bd58-581c6f99a5e4", x: 4296, y: 192} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "MEDIA_AUDIO" do
  audio("38361a19-02ec-4ffb-ac76-7c957b9c433e-G_M2_P1.mp3")
  then(Message_7)
end

```

<!-- { section: "d974bf2a-37eb-400f-b534-0c4c08fa01f2", x: 4752, y: 144} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_9 when ref_Message_7 == "Ya escuché el audio")
  then(Catch_all_4)
end

```

<!-- { section: "657db809-1007-49ba-8f39-54e8b96b1eb8", x: 4440, y: -768} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "144c44a5-9f62-49b2-8668-86130bd0ef76", x: 5208, y: 96} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "Como dicen Mari y Pilar, está bien no estar bien. Pero, como menciona Pilar, a veces es dificil hablar de estos temas...😣

*Para ti*, ¿Qué tan fácil es hablar de estos temas con tus personas de confianza?

*Recuerda que puedes responder en texto o notas de voz*"
    )

  then(Branch_91a7c6)
end

```

<!-- { section: "26b2f8a6-75ce-4304-839f-a6a97458f4dd", x: 6600, y: 120} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Sigue el podcast 🎧"]) do
      text("¡Gracias por contarnos! ✨")
    end

  then(Message_11_ when ref_Message_10 == "Sigue el podcast 🎧")
  then(Catch_all_13)
end

```

<!-- { section: "d9026258-71cd-4e46-b120-c85efd33bd6d", x: 7416, y: 144} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_12 when ref_Message_11_1 == "Ya escuché el audio!")
  then(Catch_all_5)
end

```

<!-- { section: "db1881b4-3b6f-4707-b798-aba3fdcd322d", x: 7512, y: -696} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11_1)
end

```

<!-- { section: "89607111-9341-436f-9566-6885bed317a7", x: 7992, y: 144} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "QUESTION" do
  ref_Message_12 =
    ask(
      "Pilar no se ha estado sintiendo bien en los últimos días. Las cosas no han estado bien y eso la ha dejado sintiéndose muy triste y confundida. Ella sabe que necesita hacer algo para sentirse mejor, pero no está segura de cómo hacerlo.

Si esto te estuviera pasando a ti, ¿qué harías?🤔

*Recuerda que puedes responder en texto o notas de voz*"
    )

  then(Branch_1fd2f0)
end

```

<!-- { section: "660a86ff-6dde-49af-9697-ea101a0ee6fb", x: 9336, y: 144} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Sigue el podcast 🎧"]) do
      text("¡Gracias por compartirnos estas ideas para sentirnos mejor! ✨")
    end

  then(Message_14_ when ref_Message_13 == "Sigue el podcast 🎧")
  then(Catch_all_6)
end

```

<!-- { section: "c2ecdc2d-226c-4bdf-968d-4150aa61ce5e", x: 9504, y: -768} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13)
end

```

<!-- { section: "f89621cc-abde-4a15-95ae-719085b82442", x: 10272, y: 144} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_1 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_15 when ref_Message_14_1 == "Ya escuché el audio!")
  then(Catch_all_7)
end

```

<!-- { section: "8211d1db-1e8e-4aa4-8367-8660af28b2d8", x: 10344, y: -768} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14_1)
end

```

<!-- { section: "e5886392-2e69-40d7-a61b-eba715bfa933", x: 10728, y: 168} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "TEXT_MESSAGE" do
  text("Es normal sentirse abrumada y encontrar formas de calmarse es esencial. 

Aquí van algunas de las ideas que mencionaron Pilar y Mari:")
  then(Message_16)
end

```

<!-- { section: "e74af896-c6d5-46c9-ad20-47f802d0e35d", x: 11112, y: 168} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "TEXT_MESSAGE" do
  text("🧘 Respirar profundo puede ayudarte a reducir la tensión de inmediato. 
🎵 Escuchar música empoderada puede cambiar tu estado de ánimo y darte un descanso mental. 
✍️ Escribir en un diario te permite desahogar tus pensamientos, procesar lo que sientes y reflexionar acerca de lo bueno en tu vida. 
🏃🏽‍♀️ Hacer ejercicio.
😴 Tratar de dormir bien y descansar.
💃🏾 Hacer actividades que por lo general nos llenan de energía.")
  then(Message_17)
end

```

<!-- { section: "fd8df085-40cb-4667-9783-2fb40673abcc", x: 11544, y: 168} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["Vale 👍"]) do
      text(
        "Cualquiera de estas opciones puede ser útil para manejar tus emociones y encontrar un poco de calma 😌"
      )
    end

  then(Message_18 when ref_Message_17 == "Vale 👍")
  then(Catch_all_14)
end

```

<!-- { section: "8f7be95f-9946-44ad-bedf-b05c9e0c51ae", x: 12072, y: 168} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "TEXT_MESSAGE" do
  text("Ahora, vamos a pensar un poco más sobre el tema de hoy.")
  then(Message_19)
end

```

<!-- { section: "523996ed-666e-40c7-83b6-03f10e2b97da", x: 12480, y: 168} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["Debería buscar ayuda", "No es para tanto 🙄", "No sé 😢"]) do
      text(
        "Imagina que que Pilar, últimamente, no se está sintiendo muy bien. La relación con su pareja ahora solo es peleas y celos. Llora todos los días, se irrita fácilmente y se ha alejado de sus amigas 😢

Ella se siente avergonzada por todo lo que está pasando y se niega a contárselo a alguien porque, a pesar de todo, su novio le da regalos y cree que él la ama demasiado. Además, piensa que la van a juzgar. 

¿Qué piensas sobre esto? 🤔"
      )
    end

  then(Message19_1 when ref_Message_19 == "Debería buscar ayuda")
  then(Message19_2 when ref_Message_19 == "No es para tanto 🙄")
  then(Message19_3 when ref_Message_19 == "No sé 😢")
  then(Catch_all_12)
end

```

<!-- { section: "9730a12e-6218-4f77-aedd-5490353f6fdc", x: 13968, y: 192} -->

```stack
card Message_20_1, "Message_20_1",
  version: "1",
  uuid: "3c0640c4-ff8d-5995-9bf2-1f14c9dd3e9a",
  code_generator: "MEDIA_AUDIO" do
  audio("cf3555b0-7716-47ce-a92a-e5d42f8d97f2-G_M2_P3_R1.mp3")
  then(Message_20_4)
end

```

<!-- { section: "f84e74ff-6390-49de-8b34-d2264055b18d", x: 13968, y: 504} -->

```stack
card Message_20_2, "Message_20_2",
  version: "1",
  uuid: "7f14b299-04c1-5c54-b977-1eac1d3d9530",
  code_generator: "MEDIA_AUDIO" do
  audio("edb461ca-66a1-4463-bf7c-ac332e483308-G_M2_P3_R2.mp3")
  then(Message_20_4)
end

```

<!-- { section: "0e9d592c-642a-453d-a022-d15644ca687d", x: 13968, y: 864} -->

```stack
card Message_20_3, "Message_20_3",
  version: "1",
  uuid: "585d1da4-fa3c-548a-b6df-91a1f83d6182",
  code_generator: "MEDIA_AUDIO" do
  audio("a8e39dec-ecd1-4ae1-9bdf-32a9c6ea00e2-G_M2_P3_R3.mp3")
  then(Message_20_4)
end

```

<!-- { section: "28a2cc04-341f-41be-859d-748ff01fc9d8", x: 14616, y: 432} -->

```stack
card Message_20_4, "Message_20_4",
  version: "1",
  uuid: "18b248bf-9ff1-5267-836c-be8bdc3578c9",
  code_generator: "MEDIA_AUDIO" do
  audio("25f861d6-e55c-43bb-8d5d-2d863098bc81-G_M2_P3_R4.mp3")
  then(Message_21)
end

```

<!-- { section: "b37e456a-ba99-435a-bbe6-1903e65a40cd", x: 15096, y: 432} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_21 =
    buttons(["Eso es normal👍", "No es para tanto🙄", "Cuenta con nosotras"]) do
      text(
        "En tu caso, si le contaras a tus *amigas* que te estás sintiendo mal últimamente en tu relación de pareja, ¿qué te dirían?"
      )
    end

  then(Message21_1 when ref_Message_21 == "Eso es normal👍")
  then(Message21_2 when ref_Message_21 == "No es para tanto🙄")
  then(Message21_3 when ref_Message_21 == "Cuenta con nosotras")
  then(Catch_all_8)
end

```

<!-- { section: "0c28f7b3-9694-4e73-81b8-769fac02c81d", x: 15144, y: -840} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_21)
end

```

<!-- { section: "30f69ca7-827c-4c61-87b7-c7e5a9b2daa9", x: 16776, y: 96} -->

```stack
card Message_22_1, "Message_22_1",
  version: "1",
  uuid: "01841d9d-ff48-506e-a331-a939c3ae304f",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Esta respuesta puede hacer que sientas que tus problemas no son tan serios. Aunque es útil recibir perspectiva, es importante que te sientas validada y apoyada por tu grupo 🤗"
  )

  then(Message_23)
end

```

<!-- { section: "1026ab5e-580e-4ee3-b5c9-466ea1632f39", x: 16752, y: 504} -->

```stack
card Message_22_2, "Message_22_2",
  version: "1",
  uuid: "2e640323-ec94-58a4-aca6-2179c3a38dd6",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Este comentario puede minimizar tus sentimientos y hacerte sentir incomprendida. Es importante que te sientas validada y apoyada por tu grupo 🤗"
  )

  then(Message_23)
end

```

<!-- { section: "1e3a50ca-1ee4-41db-8881-ea56270f3076", x: 16752, y: 840} -->

```stack
card Message_22_3, "Message_22_3",
  version: "1",
  uuid: "fa2a20bc-0689-5f92-8070-4b6e3773b4b7",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Esta respuesta es solidaria y alentadora. Tu grupo te ofrece un buen apoyo al reconocer tus sentimientos y mostrar que están dispuestas a ayudarte y escucharte. Es importante contar con este tipo de apoyo en momentos difíciles 🤗"
  )

  then(Message_23)
end

```

<!-- { section: "518d03cb-c3ef-4aa5-99e9-9779bc67b02b", x: 17832, y: 576} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Muy bien! Completaste el episodio 2 del podcast 🥳 Hoy tengo más stickers para que los puedas usar y te ayuden si algún día te enfrentas a una situación como esta."
      )
    end

  then(Sticker_1 when ref_Message_23 == "¡Manda mis stickers!")
  then(Catch_all_9)
end

```

<!-- { section: "2356c449-9f1c-4e47-b24f-dc40bcf7b646", x: 17784, y: -672} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_23)
end

```

<!-- { section: "2a464fd6-2781-4112-90df-cb669fde4ca8", x: 19056, y: 504} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Ya estás en el día 2 de 6 en el reto del podcast! Yo sé que vas a lograr tener una racha perfecta 🙌"
  )

  then(Message_26)
end

```

<!-- { section: "f5b0ed83-f60a-4235-8d91-4d9cf28259cd", x: 19560, y: 504} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["Después del cole", "Antes de dormir", "Al levantarme"]) do
      text(
        "Ahora te voy a dejar este reto: Para mañana, haz tu primer día de práctica y piensa ¿Cuándo quieres hacer tu rutina para que no se te olvide?"
      )
    end

  then(Message26_1 when ref_Message_26 == "Después del cole")
  then(Message26_2 when ref_Message_26 == "Antes de dormir")
  then(Message26_3 when ref_Message_26 == "Al levantarme")
  then(Catch_all_10)
end

```

<!-- { section: "fc0d5018-d1fb-4524-bf63-9fa704c6a78d", x: 22056, y: 504} -->

```stack
card Message_27, "Message_27",
  version: "1",
  uuid: "58095b08-ea56-5e0f-9bba-0cdfec59e6c4",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_27 =
    buttons(["Entendido 🌸"]) do
      text(
        "Ok amiga, esto fue todo por hoy. ¡Prepárate porque, en el episodio de mañana, hablaremos sobre cómo podemos ser apoyo para alguien que esté pasando por una situación difícil!"
      )
    end

  then(Message_28 when ref_Message_27 == "Entendido 🌸")
  then(Catch_all_11)
end

```

<!-- { section: "378a1a22-6f25-420a-98ab-cbdb1501a1b7", x: 22536, y: 504} -->

```stack
card Message_28, "Message_28",
  version: "1",
  uuid: "fa2bc47c-07ac-5963-8796-2bedea805ae2",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_c16c7c)
end

```

<!-- { section: "89687717-dfe7-42ec-9345-9f1978306fc3", x: 19536, y: -360} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_26)
end

```

<!-- { section: "7477056e-9ae0-44cc-a51a-1ce41a21d4b8", x: 22056, y: -288} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_27)
end

```

<!-- { section: "99f5d425-ab11-4dd6-ab85-04620c2c892f", x: 12504, y: -792} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_19)
end

```

<!-- { section: "2b9ee1e1-cb4e-4852-8b4e-5a8ca63328dd", x: 6504, y: -648} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "1e0c7794-8680-47c9-80fc-f993d1b7deed", x: 22992, y: 504} -->

```stack
card Profile_c16c7c, "Profile_c16c7c",
  version: "1",
  uuid: "069c5d76-fe0b-5517-94ff-68b07388e6b1",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_2")
  then(ModuleCompleted)
end

```

<!-- { section: "f2f429f2-703c-4db4-b4e7-d0381fb30435", x: 18480, y: 48} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("f414614a-0565-44d5-8a2d-1d79b1c9eb1f-Módulo2_MipersonaFav.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "21be71c1-344b-4ce9-bb8b-6abf72678347", x: 18456, y: 480} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("ac19e2a4-9c44-4731-887e-658c4021b789-Módulo2_Meamo.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "5fee6779-654c-4881-8efd-93a861943d91", x: 18408, y: 1008} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("403f1e6c-b481-4116-8b3c-ce54a0183bd5-Módulo2_InteligenciaEmocional.webp")
  text("")
  then(Image_610ba5)
end

```

<!-- { section: "9a7cc2f0-1f41-4e2d-8a24-be1bb604c5bd", x: 7032, y: 144} -->

```stack
card Message_11_, "Message_11_",
  version: "1",
  uuid: "7cadbd10-97d6-55dd-ba9d-ff103177acc6",
  code_generator: "MEDIA_AUDIO" do
  audio("e69408ad-2d32-417e-bdf2-4df14372b5ed-G_M2_P2.mp3")
  then(Message_11_1)
end

```

<!-- { section: "3fc908b9-9482-4296-8e6e-45651c15b7c5", x: 9768, y: 168} -->

```stack
card Message_14_, "Message_14_",
  version: "1",
  uuid: "33d77f34-b487-5244-b303-29d16121f8f9",
  code_generator: "MEDIA_AUDIO" do
  audio("8498ef17-905f-456f-89b1-3e4a62cbb147-G_M2_P3.mp3")
  then(Message_14_1)
end

```

<!-- { section: "8ea2d2ea-226e-4ed5-a574-c7d143a7cdd2", x: 5664, y: 48} -->

```stack
card Branch_91a7c6, "Branch_91a7c6",
  version: "1",
  uuid: "7fffa77e-39e0-5027-a564-8c53ab31d36d",
  code_generator: "CONDITIONALS" do
  then(Message9 when event.message.type == "audio")
  then(Message9 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "4cf3a872-b535-4dcb-a34b-9c152ed977e9", x: 5280, y: 696} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_9)
end

```

<!-- { section: "15fade51-9fab-4c40-a3bf-0995a314b1da", x: 8424, y: 120} -->

```stack
card Branch_1fd2f0, "Branch_1fd2f0",
  version: "1",
  uuid: "d31f9710-7903-5170-8e6c-1f20f695ad13",
  code_generator: "CONDITIONALS" do
  then(Message12 when event.message.type == "audio")
  then(Message12 when event.message.type == "text")
  then(Catch_all_12_1)
end

```

<!-- { section: "f6b4eaa4-b1e6-4088-a1fc-1f1eadaca212", x: 8256, y: 912} -->

```stack
card Catch_all_12_1, "Catch_all_12_1",
  version: "1",
  uuid: "0fede328-1fb1-5e95-9dcf-fa66f2a3c877",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_12)
end

```

<!-- { section: "3f94c615-56ce-43fe-ae66-bdaa9a9ee0bd", x: 21000, y: 552} -->

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

<!-- { section: "77c437a0-38af-45fb-bbad-be54d85a409c", x: 21504, y: 648} -->

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

  then(Message_27)
end

```

<!-- { section: "2c7805af-ec88-484e-b7c0-80ef7fc461d1", x: 18896, y: 1008} -->

```stack
card Image_610ba5, "Image_610ba5",
  version: "1",
  uuid: "e6397ccf-cd80-468c-a2f2-ed312e2e3986",
  code_generator: "MEDIA_IMAGE" do
  image("f78ed5b3-450a-4c8e-b0e2-7c72c959bd93-Módulo2_Brilla.webp")
  text("")
  then(Message_25)
end

```

<!-- { section: "10ca70d4-d2ab-435e-a4f3-3d360e7d06b2", x: 18504, y: -528} -->

```stack
card Sticker_1, "Sticker_1",
  version: "1",
  uuid: "66cd7f3a-c6c1-4c5a-8b54-13195c39e8a3",
  code_generator: "MEDIA_IMAGE" do
  image("afc7af4e-5e15-493f-8e2a-279443720d01-copy2Modulo2_Vibrando.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "b7e5bb3c-4243-4d3d-b10f-b0af6bc8e199", x: 11496, y: -768} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "dc4ca43d-a77c-4803-a6ef-42706a3ac817",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_17)
end

```

<!-- { section: "b614101d-4e2e-457f-831a-c200c9442fa9", x: 6096, y: 96} -->

```stack
card Message9 do
  write_result("module2_social_support", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "3525fbb2-ad6b-4212-9d12-cd4dd0bab7d1", x: 8832, y: 144} -->

```stack
card Message12 do
  write_result("module2_mental_health", "@ref_message_12")
  then(Message_13)
end

```

<!-- { section: "ee606718-c601-48d2-8786-5a483826b316", x: 23568, y: 456} -->

```stack
card ModuleCompleted do
  log("Module 2 Complete")
  write_result("module2_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "60acc57d-f722-459c-b0b7-3c0e8f1c8dad", x: 96, y: -24} -->

```stack
card Message1 do
  log("Module 2 Started")
  write_result("module2_started", "yes")
  then(Message_2)
end

```

<!-- { section: "fb640fb7-ea51-4be0-acc2-39c5ac665bb7", x: 1344, y: -120} -->

```stack
card Message2_1 do
  write_result("module2_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "dd57880d-d779-48fe-b432-ff0897be03c7", x: 1344, y: 240} -->

```stack
card Message2_2 do
  write_result("module2_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "05765245-4da3-4778-9855-a6dd2e31bbc5", x: 12968, y: 228} -->

```stack
card Message19_1 do
  write_result("module2_beliefs", "a")
  then(Message_20_1)
end

```

<!-- { section: "6a59f267-7078-4cc0-a09c-654242c4683d", x: 12984, y: 552} -->

```stack
card Message19_2 do
  write_result("module2_beliefs", "b")
  then(Message_20_2)
end

```

<!-- { section: "256cf0e2-1cb9-4ddd-9de4-763cdff19caa", x: 12984, y: 888} -->

```stack
card Message19_3 do
  write_result("module2_beliefs", "c")
  then(Message_20_3)
end

```

<!-- { section: "19d54701-3f85-41e7-8c61-8cdcafa1f8bd", x: 15624, y: 216} -->

```stack
card Message21_1 do
  write_result("module2_social_norms", "a")
  then(Message_22_1)
end

```

<!-- { section: "7f3f8a66-4d84-440b-88bb-69c4830706c4", x: 15648, y: 552} -->

```stack
card Message21_2 do
  write_result("module2_social_norms", "b")
  then(Message_22_2)
end

```

<!-- { section: "9221f773-524f-4d4e-98aa-d43c7234a60f", x: 15648, y: 888} -->

```stack
card Message21_3 do
  write_result("module2_social_norms", "c")
  then(Message_22_3)
end

```

<!-- { section: "5b327fe7-ec8a-4db5-8f52-61e77f714e3a", x: 20064, y: 288} -->

```stack
card Message26_1 do
  write_result("module2_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "c3873596-a87d-406f-8aa8-feb45e16134f", x: 20088, y: 648} -->

```stack
card Message26_2 do
  write_result("module2_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "76514b76-798c-4b07-8513-2f9ad6434426", x: 20112, y: 984} -->

```stack
card Message26_3 do
  write_result("module2_behavioral_activation", "c")
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
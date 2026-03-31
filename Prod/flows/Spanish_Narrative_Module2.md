<!-- { section: "efd53897-74bb-45fa-862e-521eef180549", x: -2208, y: -24} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_only_phrase(event.message.text.body, "test_n2_2") or
       (contact.arm == "NARRATIVE" and contact.contact_module == "MODULE_1" and
          contact.quiz_post_module1_complete == true and contact.onboarding_complete == true)

```

<!-- { section: "c45911c1-681a-4f71-bce6-dd9ddd8b2ee7", x: -504, y: -24} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text("*¡Hola!* 👋
Bienvenida al segundo episodio de la historia de Pilar.")
  then(Message1)
end

```

<!-- { section: "d30c9e21-4563-4d5c-ae51-e9338c9fb127", x: 816, y: -24} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "¡Buenísimo! 👍"]) do
      text(
        "El reto de ayer era conversar con alguien de confiaza acerca de las relaciones sanas o tóxicas ¿Cómo te fue con el reto de ayer?"
      )
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "¡Buenísimo! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "cf2df98a-2d70-47d4-a572-661af5a610bc", x: 816, y: -336} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "a59ddf08-66e0-4844-884d-d6553fa7d4d1", x: 1872, y: -24} -->

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

<!-- { section: "5ecb5ee5-ee3f-4fc8-b935-bdaf9d5c022f", x: 1872, y: 432} -->

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
  code_generator: "TEXT_MESSAGE" do
  text("En este segundo episodio sabremos por qué la policía llamó a la mamá de Pilar 💖")
  then(Message_5)
end

```

<!-- { section: "22989e5a-2822-46c5-8546-2716f067a9da", x: 2832, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Ok"]) do
      text(
        "Recuerda que si hay algo de la historia de Pilar o alguna pregunta te hace sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!"
      )
    end

  write_result("message_5", ref_Message_5)
  then(Message_6 when ref_Message_5 == "Ok")
end

```

<!-- { section: "3933b1d2-f824-499c-9130-099f1dc1ce8e", x: 3384, y: 96} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "MEDIA_AUDIO" do
  audio("e63f2618-ca79-4844-be9d-d4ff55de7257-M2_P1_A1.mp3")
  then(Message_7)
end

```

<!-- { section: "939ba2e8-d0a4-4477-b247-cbed87245b04", x: 3936, y: -720} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "edb96205-f120-4f06-9817-e1372f63d4cf", x: 3936, y: 96} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_7", ref_Message_7)
  then(Message_8 when ref_Message_7 == "Ya escuché el audio!")
  then(Catch_all_3)
end

```

<!-- { section: "32b1cf2c-75bc-4d01-8d92-b8ea5f75dc14", x: 4464, y: 96} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["Respirar sí ayuda💨", "Yo me bloquearía😣", "Eso no funciona🙄"]) do
      text(
        "A veces cuando creemos que una situación se sale de nuestras manos podemos sentirnos muy angustiados. En el episodio escuchamos que Laura se alteró al saber que su amiga, estaba desaparecida. En ese momento, su hermana intenta calmarla por medio de la respiración...

¿Qué piensas sobre esto? 🤔"
      )
    end

  then(Message8_1 when ref_Message_8 == "Respirar sí ayuda💨")
  then(Message8_2 when ref_Message_8 == "Yo me bloquearía😣")
  then(Message8_3 when ref_Message_8 == "Eso no funciona🙄")
  then(Catch_all_4)
end

```

<!-- { section: "ad9f01c8-4b61-44eb-b628-3e58f53a4826", x: 4584, y: -720} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_8)
end

```

<!-- { section: "51d4040a-e639-4e60-9bcd-b800cb9bdd0a", x: 5640, y: -144} -->

```stack
card Message_9_1, "Message_9_1",
  version: "1",
  uuid: "c3a0f754-7f11-5ee1-8038-7f0744548590",
  code_generator: "TEXT_MESSAGE" do
  text(
    "La respiración es una técnica sencilla que puede ser muy efectiva para calmarse en momentos de estrés. Nos puede ayudar a recuperar el control cuando las emociones se sienten intensas."
  )

  then(Message_10)
end

```

<!-- { section: "c02916f8-8279-4162-89ee-caa69d41000b", x: 6144, y: 312} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "QUESTION" do
  ref_Message_10 =
    ask(
      "Recuerda: está bien no estar bien siempre. A veces es dificil regular nuestras emociones, sobre todo cuando estas son intensas...😣

Para ti, ¿qué tan fácil es para ti regular tus emociones?

*Recuerda que puedes responder en texto o notas de voz*"
    )

  then(Branch_4fcb2f)
end

```

<!-- { section: "fb515882-04d6-4d5c-a30a-a477fdd1b243", x: 7608, y: 312} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["Siguiente audio"]) do
      text("¡Gracias por contarme ✨")
    end

  write_result("message_11", ref_Message_11_1)
  then(Message_12 when ref_Message_11_1 == "Siguiente audio")
  then(Catch_all_5)
end

```

<!-- { section: "63ba06b6-64ec-4a98-adc9-b76672b1b3a8", x: 7608, y: 0} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11_1)
end

```

<!-- { section: "fe69fc13-b5a5-490f-88e7-d41da47d1c06", x: 8064, y: 192} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "MEDIA_AUDIO" do
  audio("e8dd82d7-d725-4c8b-8e3e-6049587b292e-M2_P2_A1.mp3")
  then(Message_12_1)
end

```

<!-- { section: "ef664d3d-b8b7-468b-be1c-92a3644aa4f2", x: 8904, y: 192} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "QUESTION" do
  ref_Message_13 =
    ask(
      "Parece que Pilar está pasando por una situación complicada😔. Se nota un poco preocupada, triste y confundida. 
Si tu te estuvieras sintiendo así, ¿qué harías?🤔

*Recuerda que puedes responder en texto o notas de voz*"
    )

  then(Branch_2e1be6)
end

```

<!-- { section: "33a2113f-618a-42b4-b812-97f9efa24910", x: 11352, y: -648} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_17)
end

```

<!-- { section: "98955252-4194-46bd-bed5-c54a30d214b1", x: 10152, y: 168} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "TEXT_MESSAGE" do
  text("¡Gracias por compartirnos tus ideas!")
  then(Message_15)
end

```

<!-- { section: "10d54b2a-1236-43ad-b68e-98d4d9d2893e", x: 10776, y: -648} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16)
end

```

<!-- { section: "d7c83390-7496-483b-9709-068611bc7e93", x: 10488, y: 168} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En general, es normal sentirnos angustiados si estamos pasando por una situación difícil. Sin embargo, en esos momentos es muy válido permitirnos sentir esas emociones y buscar apoyo. Aquí van algunas ideas adicionales:"
  )

  then(Message_16)
end

```

<!-- { section: "75d3bd77-3d6d-43b2-85c0-37fe1c82fe81", x: 10848, y: 168} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["Siguiente pregunta"]) do
      text(
        "🔍 Reconocer las sensaciones que sientes (dolor de cabeza, tensión facial, nudo en la garganta) te permite conectar con lo que está pasando en tu cuerpo.
😌 Aceptar que esta situación te hace sentir emociones desagradables te permite conectar con tu ser más vulnerable.
👩‍❤️‍👩 Hablar con alguien de confianza sobre cómo te sientes puede ayudarte a no sentirte sola y a encontrar regugio.
🧘 Aceptar que a veces nos equivocamos, te permite soltar la culpa y el juicio hacia ti misma.
📖 Escribir lo que sientes puede ayudarte a desahogarte y aclarar tu mente."
      )
    end

  write_result("message_16", ref_Message_16)
  then(Message_17 when ref_Message_16 == "Siguiente pregunta")
  then(Catch_all_7)
end

```

<!-- { section: "5d4b0252-ac76-4d2f-8a28-2842b2b9bf1b", x: 11376, y: 168} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["Eso es normal👍", "No es para tanto🙄", "Cuenta con nosotras"]) do
      text(
        "¿Si le contaras a tus *amigas* que te vienes sintiendo mal últimamente, qué te dirían?"
      )
    end

  then(Message17_1 when ref_Message_17 == "Eso es normal👍")
  then(Message17_2 when ref_Message_17 == "No es para tanto🙄")
  then(Message17_3 when ref_Message_17 == "Cuenta con nosotras")
  then(Catch_all_6)
end

```

<!-- { section: "818d3926-f62c-49eb-be88-83fdbe0ec900", x: 12576, y: -96} -->

```stack
card Message_18_1, "Message_18_1",
  version: "1",
  uuid: "8a733211-d7eb-5c2b-9a03-0e4bea4cba0b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Esta respuesta puede hacer que sientas que tus problemas no son tan serios. Aunque es útil recibir perspectiva, es importante que te sientas validada y apoyada por tu grupo."
  )

  then(Message_19)
end

```

<!-- { section: "9483a94d-d17b-4643-b968-1dc83d176683", x: 13152, y: 336} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "No siempre es fácil pedir ayuda a otros, ¡pero es un súper poder a poner en práctica! Cuando lo usas puedes descubrir que tienes a más personas de las que pensabas dispuestas a ayudarte 💁‍♀️"
  )

  then(Message_20_)
end

```

<!-- { section: "9ba26e83-fe93-4938-a1d3-e5a2d4b6f06d", x: 13632, y: 336} -->

```stack
card Message_20_, "Message_20_",
  version: "1",
  uuid: "8f5fca40-9def-58ee-b7c0-e79677456838",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20_ =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "Muy bien! Has escuchado el episodio 2 de la historia de Pilar 🥳

Son temas complejos, por ello para ayudarte a navegarlos te dejo unos stickers buenísimos sobre este tema y que puedes usar para responder si llegas a vivir algo similar"
      )
    end

  write_result("message_20", ref_Message_20_)
  then(Message_21_sticker_1 when ref_Message_20_ == "¡Manda mis stickers!")
  then(Catch_all_12)
end

```

<!-- { section: "a1ce710f-c4bc-4bff-a450-d4f421ca3ecb", x: 14808, y: 408} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "QUESTION" do
  ref_Message_22 =
    ask(
      "¿Has escuchado la canción \"Mientras me curo del cora\" 💖 de Karol G? 

Hay una parte de la letra que dice: *\"Está bien no sentirse bien, es normal, no es delito, y mañana será más bonito\".* 

¿Conoces alguna otra canción que te haga sentir mejor cuando estás pasando por un mal momento? Escribe el nombre aquí"
    )

  then(Branch_64e016)
end

```

<!-- { section: "1e77e216-2062-4fc2-a4f3-d5f9b179df59", x: 16248, y: 120} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_23)
end

```

<!-- { section: "d4b15a27-91cd-468c-af95-de77489d3508", x: 16248, y: 384} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["Después de la U 🏫", "Antes de dormir 😴", "Al levantarme 🌞"]) do
      text(
        "Ahora te voy a dejar este reto: Para mañana, en algún momento del día, aplica una estrategia para sentirte mejor ¿cuándo quisieras hacerla para que no se te olvide?"
      )
    end

  then(Message23_1 when ref_Message_23 == "Después de la U 🏫")
  then(Message23_2 when ref_Message_23 == "Antes de dormir 😴")
  then(Message23_3 when ref_Message_23 == "Al levantarme 🌞")
  then(Catch_all_8)
end

```

<!-- { section: "e82b2d84-ad39-4a3a-884c-ac82b0f4a78e", x: 18672, y: 456} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["¡Quiero saberlo!🧐"]) do
      text(
        "Ok amiga esto fue todo por hoy. ¡Prepárate! Porque el episodio de mañana va a estar increíble ¿Qué crees? ¿Será que mañana sabremos dónde está Pilar?"
      )
    end

  write_result("message_24", ref_Message_24)
  then(Message_25 when ref_Message_24 == "¡Quiero saberlo!🧐")
  then(Catch_all_9)
end

```

<!-- { section: "a531dde3-315a-45dd-8690-c74681fa71e1", x: 18672, y: 168} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_24)
end

```

<!-- { section: "1ec3b4cc-ef17-4aa5-980b-130787a1f573", x: 19224, y: 456} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_375453)
end

```

<!-- { section: "f1194683-0f33-45af-939c-bdf435a274ef", x: 13608, y: -648} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_20_)
end

```

<!-- { section: "5796e694-e922-49f9-a0fe-d6c90ed89581", x: 8472, y: -744} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12_1)
end

```

<!-- { section: "6899bc8d-9b15-42cf-b88c-c12badf3e673", x: 5640, y: 312} -->

```stack
card Message_9_2, "Message_9_2",
  version: "1",
  uuid: "a7a44162-d023-584e-886e-0db24185236b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Sentirse bloqueada o incapaz de reaccionar ante una situación estresante es normal. Sin embargo, aprender algunas técnicas que nos pueden ayudar en esos momentos como la respiración puede ser útil para manejar esos momentos."
  )

  then(Message_10)
end

```

<!-- { section: "309012c0-995f-4253-bdb7-4f194c1d354f", x: 5640, y: 792} -->

```stack
card Message_9_3, "Message_9_3",
  version: "1",
  uuid: "58f08f6d-1c0f-5772-b91b-b7163ce1a543",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Es común creer que algo tan simple como respirar funcione en un momento como estos. Sin embargo, ¿qué tal si lo intentas algún día? ¡Te aseguro que esto puede marcar una gran diferencia en momentos de angustia!"
  )

  then(Message_10)
end

```

<!-- { section: "85ec19de-9d5f-40ca-9256-9deabaa8fca7", x: 8472, y: 192} -->

```stack
card Message_12_1, "Message_12_1",
  version: "1",
  uuid: "b3faf013-4802-5596-99ea-9df4b6c14c5b",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_1 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_12", ref_Message_12_1)
  then(Message_13 when ref_Message_12_1 == "Ya escuché el audio!")
  then(Catch_all_13)
end

```

<!-- { section: "927b2e22-0336-4f84-b939-f5e6f1aa85e3", x: 12576, y: 264} -->

```stack
card Message_18_2, "Message_18_2",
  version: "1",
  uuid: "f991fbc5-7712-5518-a753-a5e3f160f9ef",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Este comentario puede minimizar tus sentimientos y hacerte sentir incomprendida. Es importante que te sientas validada y apoyada por tu grupo."
  )

  then(Message_19)
end

```

<!-- { section: "b63b35ef-b0b5-48fb-ac13-4424327186dd", x: 12576, y: 648} -->

```stack
card Message_18_3, "Message_18_3",
  version: "1",
  uuid: "8bf10063-4658-5846-a34e-3c68b1167484",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Esta respuesta es solidaria y alentadora. Tu grupo te ofrece un buen apoyo al reconocer tus sentimientos y mostrar que están dispuestas a ayudarte y escucharte. Es importante contar con este tipo de apoyo en momentos difíciles."
  )

  then(Message_19)
end

```

<!-- { section: "7613e7c6-a72a-4fcf-9dad-67c3cc0c02d9", x: 14208, y: -624} -->

```stack
card Message_21_sticker_1, "Message_21_sticker_1",
  version: "1",
  uuid: "7bcad0af-edec-5046-9d8a-298767885d4b",
  code_generator: "MEDIA_IMAGE" do
  image("ee43bc6b-18a7-4d0d-8d51-d454af665360-Módulo2_Brilla.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "ecf4407f-7bf4-4081-84ef-e738a9a4c974", x: 14184, y: -144} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("771ab573-dfa4-4eab-8332-2fad71641537-Módulo2_InteligenciaEmocional.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "7e450698-2c8c-42a3-860b-d413dac7a060", x: 14160, y: 336} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("4704ed84-9184-41ca-83e7-0c2bb384b4cc-Módulo2_Meamo.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "365542af-29f3-4c71-b8dc-273962ac5018", x: 14160, y: 792} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("a47d22ef-7565-4c0e-a72a-5cb7a9fc1b94-Módulo2_MipersonaFav.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "eca244ee-8615-4948-995f-70b6485a5f46", x: 14160, y: 1392} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("7067555e-30c5-4f00-94ec-a5b22397d8ba-copy2Modulo2_Vibrando.webp")
  text("")
  then(Message_22)
end

```

<!-- { section: "55a8440b-d0e6-43dd-8411-a0cc529ac856", x: 6584, y: 312} -->

```stack
card Branch_4fcb2f, "Branch_4fcb2f",
  version: "1",
  uuid: "88629154-7842-53a9-ba8c-3bc2cad9a957",
  code_generator: "CONDITIONALS" do
  then(Message10 when event.message.type == "audio")
  then(Message10 when event.message.type == "text")
  then(Text_6c79a6)
end

```

<!-- { section: "c0585e5f-d6db-4b6b-8107-21c70c2cb419", x: 6120, y: 888} -->

```stack
card Text_6c79a6, "Text_6c79a6",
  version: "1",
  uuid: "862e2696-9a6f-5201-ab49-c9a6b15b10d0",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_10)
end

```

<!-- { section: "8cd32f28-04a8-4808-a99b-f7814ed775ae", x: 9288, y: 192} -->

```stack
card Branch_2e1be6, "Branch_2e1be6",
  version: "1",
  uuid: "7cc496f7-6b9d-5e81-9517-1ec6c6d0ab3b",
  code_generator: "CONDITIONALS" do
  then(Message13 when event.message.type == "audio")
  then(Message13 when event.message.type == "text")
  then(Text_72ac41)
end

```

<!-- { section: "db4e6f7e-5970-4a85-a244-6f3ddc61feb2", x: 9192, y: 624} -->

```stack
card Text_72ac41, "Text_72ac41",
  version: "1",
  uuid: "4ffd575b-86ff-509f-afbb-7ba99b4112aa",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_13)
end

```

<!-- { section: "753ab3f9-6d8a-450f-8be8-30af8fb3b91c", x: 15264, y: 408} -->

```stack
card Branch_64e016, "Branch_64e016",
  version: "1",
  uuid: "6e9f32c6-025c-5a46-b8b1-91253f0e8e41",
  code_generator: "CONDITIONALS" do
  then(Message22 when event.message.type == "text")
  then(Text_400e5d)
end

```

<!-- { section: "a23e8da6-3480-49db-bc0b-401df4c3f20f", x: 15168, y: 792} -->

```stack
card Text_400e5d, "Text_400e5d",
  version: "1",
  uuid: "2f8714fc-fb3c-586b-8af6-5ade7144e2dc",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_22)
end

```

<!-- { section: "4049f427-7abb-46a5-ae28-5040ed608b97", x: 17712, y: 384} -->

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

<!-- { section: "4876a793-dc47-41f6-be57-2d1f6da14e22", x: 18216, y: 384} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text("• Línea MAAD: lineamaad@uniandes.edu.co

• Ombudsperson: ombudsperson@uniandes.edu.co

• Decanatura de Estudiantes: centrodeapoyo@uniandes.edu.co

• Consejerxs MAAD: ombudsperson.uniandes.edu.co/maqd1/consejerxs-maad")
  then(Message_24)
end

```

<!-- { section: "b1b44d3a-5874-474b-958a-cd501801f9db", x: 19704, y: 456} -->

```stack
card Profile_375453, "Profile_375453",
  version: "1",
  uuid: "dbb23524-74cf-4e79-9ced-4795b7d1bead",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_2")
  then(ModuleCompleted)
end

```

<!-- { section: "9231e41c-b051-45b3-b383-276c24698804", x: 15696, y: 960} -->

**@Buhle**

save user response here

<!-- { section: "cbceb0c2-4c1e-48e5-80b2-c25882ca3389", x: 20208, y: 936} -->

**@Buhle**

Set follow up message to go off at 6pm Time zone is Colombia / Bogota time

<!-- { section: "698ed1b7-f0df-4399-9dfd-fd3cd08acfaa", x: 12096, y: 1128} -->

**@Buhle**

save user response here

<!-- { section: "dbac173a-8a4d-4fa1-adfc-e0e62f37ad49", x: 5136, y: 1536} -->

**@Buhle**

save user response here

<!-- { section: "cd4cb63a-92c3-4b00-9e66-19021e45cdf4", x: 20184, y: 456} -->

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

<!-- { section: "b0503eb3-0d97-46ca-8edf-50debae4dca9", x: 240, y: -24} -->

```stack
card Message1 do
  log("Module 2 Started")
  write_result("module2_started", "yes")
  then(Message_2)
end

```

<!-- { section: "31c12ada-5b10-43c9-87b8-849c01e526ee", x: 1320, y: -24} -->

```stack
card Message2_1 do
  write_result("module2_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "1f71bac9-9e5d-47c1-804f-898fe3dfda21", x: 1320, y: 432} -->

```stack
card Message2_2 do
  write_result("module2_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "bcd6fc5e-e36d-44a4-89fb-14f79076183a", x: 4968, y: -48} -->

```stack
card Message8_1 do
  write_result("module2_beliefs", "a")
  then(Message_9_1)
end

```

<!-- { section: "89faf74e-38c2-4f5d-9435-f4925fb8c581", x: 4968, y: 336} -->

```stack
card Message8_2 do
  write_result("module2_beliefs", "b")
  then(Message_9_2)
end

```

<!-- { section: "82422245-b3cc-43a8-88b5-5f398aa1e495", x: 4968, y: 696} -->

```stack
card Message8_3 do
  write_result("module2_beliefs", "c")
  then(Message_9_3)
end

```

<!-- { section: "b1162431-8355-4390-80b8-2ab983363923", x: 16872, y: 384} -->

```stack
card Message23_1 do
  write_result("module2_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "f7f8e32a-62c1-4f7d-8744-0a193abd6b5f", x: 16872, y: 720} -->

```stack
card Message23_2 do
  write_result("module2_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "3feb7a1c-d9a3-4d46-84a9-175a78fc7818", x: 16872, y: 1056} -->

```stack
card Message23_3 do
  write_result("module2_behavioral_activation", "c")
  then(Safe_Guarding_1)
end

```

<!-- { section: "ba6fef3e-85b0-4407-92be-dfdd8db1d5e4", x: 15720, y: 384} -->

```stack
card Message22 do
  write_result("module2_mental_health", "@ref_message_22")
  then(Message_23)
end

```

<!-- { section: "5bf0c111-458f-4662-9a62-54f5108ee24a", x: 11976, y: -144} -->

```stack
card Message17_1 do
  write_result("module2_social_norms", "a")
  then(Message_18_1)
end

```

<!-- { section: "14fb6460-062c-4d22-9d4f-987c3c4d81cd", x: 12000, y: 192} -->

```stack
card Message17_2 do
  write_result("module2_social_norms", "b")
  then(Message_18_2)
end

```

<!-- { section: "851c12e5-6936-4235-a91f-308adf7d6140", x: 12000, y: 576} -->

```stack
card Message17_3 do
  write_result("module2_social_norms", "c")
  then(Message_18_3)
end

```

<!-- { section: "a53d8d18-8599-40e0-810c-47ca10ef10e0", x: 7056, y: 312} -->

```stack
card Message10 do
  write_result("module2_social_support", "@ref_message_10")
  then(Message_11_1)
end

```

<!-- { section: "88d5654c-43be-4330-85ef-052212b2dedd", x: 9696, y: 168} -->

```stack
card Message13 do
  write_result("module2_attitudes", "@ref_message_13")
  then(Message_14_1)
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
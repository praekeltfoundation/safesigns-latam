<!-- { section: "cf644ec1-959d-42e8-a98b-1a97bbaed495", x: -864, y: -72} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_only_phrase(event.message.text.body, "test_g4_2") or
       (contact.contact_module == "MODULE_3" and contact.quiz_post_module3_complete == true and
          contact.arm == "GAMIFIED")

```

<!-- { section: "7eee5188-7743-4951-94a9-7190180d18fa", x: -384, y: -72} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*Ahora sí,* estamos listas para escuchar el cuarto episodio del podcast de Pilar y Mari. ¡Ya pasamos la mitad!🏃‍♀️‍➡️"
  )

  then(Message1)
end

```

<!-- { section: "c619586d-390c-48a7-ae8f-213b8acc30e5", x: 984, y: -72} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "Sí, ¡Buenísimo! 👍"]) do
      text("El reto de ayer era pensar en quién sería tu persona de confianza, ¿lo cumpliste?")
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "Sí, ¡Buenísimo! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "de7af468-fbd5-49ec-928d-6a1fd5831177", x: 984, y: -384} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "76e51cc2-4ca9-40af-a8b0-4ef4b07a1b10", x: 2136, y: -72} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text("No te preocupes, todavía tienes tiempo. Es clave tener tu red de apoyo")
  then(Message_4)
end

```

<!-- { section: "5a77d0ad-e89b-4cfc-9887-96b88821311b", x: 2136, y: 288} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text("Increíble, ¡ya sabes en quién puedes confiar!")
  then(Message_4)
end

```

<!-- { section: "90c4f999-903f-464e-b79b-aa9594c0acc5", x: 2664, y: -72} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Vale 👍"]) do
      text("Recuerda que, entre más larga tu racha, ¡más stickers vas acumulando!🙌")
    end

  write_result("message_4", ref_Message_4)
  then(Message_5 when ref_Message_4 == "Vale 👍")
  then(Catch_all_2)
end

```

<!-- { section: "e16aa118-dfd6-4a2c-9240-65cfe95965c4", x: 2616, y: -1104} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "36a0d6a8-5391-4ecc-baab-1da056725f24", x: 3312, y: -72} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este episodio, Pilar y Mari hablarán sobre lo poderosas que podemos ser 💪 y los cambios que podemos realizar en nuestras vidas."
  )

  then(Message_6)
end

```

<!-- { section: "dc4019df-9401-47ab-b7e9-fd0998ceae3f", x: 3792, y: -72} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Recuerda que si hay algo de lo que hablan Pilar y Mari o alguna pregunta te llega a hacer sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!🫰"
      )
    end

  write_result("message_6", ref_Message_6)
  then(Message_7 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "e61ded93-8a51-4dc8-b531-03f6e6f46f93", x: 3816, y: -1080} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6)
end

```

<!-- { section: "084f6543-d180-487d-8f3c-051aa28221bf", x: 4824, y: -72} -->

```stack
card Messgae_8, "Messgae_8",
  version: "1",
  uuid: "8d5717ce-c677-54b3-993b-a4185ceb62be",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Messgae_8 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine esta parte del podcast, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_8", ref_Messgae_8)
  then(Message_9 when ref_Messgae_8 == "Ya escuché el audio")
  then(Catch_all_4)
end

```

<!-- { section: "59dd81dd-ea35-4bea-8b88-6ac261bd8d65", x: 4344, y: -72} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "MEDIA_AUDIO" do
  audio("0aaee490-b425-472f-b3df-b211f34768a7-G_M4_P1.mp3")
  then(Messgae_8)
end

```

<!-- { section: "49fe4763-05e6-4d2a-ac57-3b1b692afba8", x: 4800, y: -1104} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Messgae_8)
end

```

<!-- { section: "cede5314-8373-45ec-bb1c-eb73f0002f7f", x: 5544, y: -72} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Como lo dijeron Pilar y Mari, todas tenemos características que nos hacen las personas que somos y nos hacen especiales, ¡son nuestro superpoder! 💪

Algunas somos personas muy perseverantes y lo demostramos en la cancha de fútbol ⚽ otras somos curiosas y por eso nos encanta aprender📚"
  )

  then(Message_10)
end

```

<!-- { section: "5f481719-0428-465d-b7ea-b3decf6e82f7", x: 6024, y: -72} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "QUESTION" do
  ref_Message_10 =
    ask(
      "¿Qué características tuyas sientes que te hacen especial y dónde las demuestras? Escribe al menos una y dime por qué es importante para ti "
    )

  then(Branch_1f3902)
end

```

<!-- { section: "1935d0ec-f993-4d6b-8470-121f9bbcb030", x: 8232, y: -72} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_11", ref_Message_11_1)
  then(Message_12 when ref_Message_11_1 == "Ya escuché el audio")
  then(Catch_all_5)
end

```

<!-- { section: "3ce674b8-90ff-4bf9-8e13-a9fccf1cce1d", x: 7656, y: -72} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "MEDIA_AUDIO" do
  audio("920c6165-4f40-4670-91d9-a6f4c8c9cb98-G_M4_P2.mp3")
  then(Message_11_1)
end

```

<!-- { section: "e819abb4-215c-4fdf-9085-07939746090f", x: 8232, y: -312} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11_1)
end

```

<!-- { section: "65887f26-132b-4207-a583-5653235d5af8", x: 9048, y: -72} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["En peleas de pareja", "En retos de la U", "En problemas en casa"]) do
      text(
        "Todas tenemos momentos en que necesitamos esa chispita para poder seguir adelante. Tú, ¿cuándo has necesitado más recordarte a ti misma que tienes un superpoder?"
      )
    end

  then(Message12_1 when ref_Message_12 == "En peleas de pareja")
  then(Message12_2 when ref_Message_12 == "En retos de la U")
  then(Message12_3 when ref_Message_12 == "En problemas en casa")
  then(Catch_all_6)
end

```

<!-- { section: "f36e03d8-bf4b-47ab-9221-92d1e2c05075", x: 9048, y: -312} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "2283600e-8e6d-4fed-aeee-952d4f66880f", x: 10704, y: -312} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! A veces hay situaciones de pareja que se pueden volver complejas por muchas razones. Tu superpoder seguro te ayuda a llevar tu relación de una mejor manera 🌟 *Recuerda: nuestros superpoderes crecen entre más los pongamos en práctica* ¡Sigue así!"
  )

  then(Message_14_1)
end

```

<!-- { section: "50250aa1-9fd3-4a5c-9b4f-ee1b156e2256", x: 10704, y: 72} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! A veces no es fácil sortear situaciones de la universidad que pueden complicarse por muchas razones. Tu superpoder seguro te ayuda a llevar mejor estos retos🌟 *Recuerda: nuestros superpoderes crecen entre más los pongamos en práctica* ¡Sigue así!"
  )

  then(Message_14_1)
end

```

<!-- { section: "69274871-e286-4a2a-a6fe-3ad1f119cc58", x: 10704, y: 456} -->

```stack
card Message_13_3, "Message_13_3",
  version: "1",
  uuid: "d0b53090-c491-560e-9fdb-e2ba5b1436df",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! A veces no es fácil manejar situaciones en casa que pueden volverse complejas por muchas razones. Tu superpoder seguro te ayuda a navegar mejor tus relaciones en casa🌟 *Recuerda: nuestros superpoderes crecen entre más los pongamos en práctica* ¡Sigue así!"
  )

  then(Message_14_1)
end

```

<!-- { section: "3839d36c-e219-453b-b10f-71a9b75e4741", x: 12072, y: -24} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_14", ref_Message_14)
  then(Message_15 when ref_Message_14 == "Ya escuché el audio!")
  then(Catch_all_7)
end

```

<!-- { section: "313d16ff-72bb-496d-bc37-e6f28d9b833b", x: 12048, y: -1032} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "dcc6d265-830c-4edf-8440-0eadef392bcd", x: 13080, y: -72} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["¡Por supuesto! 💪", "A veces lo dudo 🤔", "No lo creo🤷‍♀️"]) do
      text(
        "Te cuento que Pilar y Mari habían tenido el sueño de crear este podcast, desde que estaban en séptimo. 

Cuando empezaron, tenian muchas dudas, pero finalmente se arriesgaron y ahora tú lo estás escuchando 🫰

En tu caso, ¿crees que si te propones hacer algo harías todo lo posible para alcanzarlo?"
      )
    end

  then(Message15_1 when ref_Message_15 == "¡Por supuesto! 💪")
  then(Message15_2 when ref_Message_15 == "A veces lo dudo 🤔")
  then(Message15_3 when ref_Message_15 == "No lo creo🤷‍♀️")
  then(Catch_all_8)
end

```

<!-- { section: "457ab1b1-d9bb-4d78-819f-7f8d4882051b", x: 13008, y: -1176} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "f46b7cb7-0ef2-456b-b7c1-54dac3438b6e", x: 14832, y: -144} -->

```stack
card Message_16_1, "Message_16_1",
  version: "1",
  uuid: "79d2db01-2ced-5381-8796-6f1fb81d9335",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Genial! Creer en ti misma es fundamental.* Todos tenemos la capacidad de enfrentar desafíos. Como hicieron Pilar y Mari, seguramente tú también has superado momentos complicados antes y eso te ha hecho más fuerte 🤩

Hablar con alguien de confianza y reflexionar acerca de tu superpoder puede ayudarte a ver la situación con más claridad y encontrar soluciones. "
  )

  then(Message_17)
end

```

<!-- { section: "2149b66f-6345-4820-887e-c8af2b049c6e", x: 14808, y: 384} -->

```stack
card Message_16_2, "Message_16_2",
  version: "1",
  uuid: "4736c50d-9290-5ad0-8477-a21bde650bf8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*Es normal tener dudas en situaciones difíciles*, pero es importante recordar que todos tenemos la capacidad de enfrentar desafíos. Pilar y Mari también dudaron al principio, pero perseveraron, son más fuertes ahora y estan logrando su sueño 💪

Hablar con alguien de confianza, reflexionar acerca de tu superpoder, puede ayudarte a ver la situación con más claridad y encontrar soluciones."
  )

  then(Message_17)
end

```

<!-- { section: "f42c05c0-8f86-4bdc-8f2a-090c1a8b006d", x: 14832, y: 984} -->

```stack
card Message_16_3, "Message_16_3",
  version: "1",
  uuid: "b029a349-f1f2-5b23-a667-1ceb422da17a",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*Es normal tener dudas en situaciones difíciles*, pero es importante recordar que todos tenemos la capacidad de enfrentar desafíos. Al igual que Pilar y Mari, seguramente tú también has superado momentos complicados antes y eso te ha hecho más fuerte. *Date* una oportunidad *para* intentarlo 🤗

Hablar con alguien de confianza, reflexionar acerca de tu superpoder, puede ayudarte a ver la situación con más claridad y encontrar soluciones."
  )

  then(Message_17)
end

```

<!-- { section: "99c45f8f-877f-4e24-994c-48383f6213c5", x: 15744, y: 384} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "TEXT_MESSAGE" do
  text("Ahora, pensemos en estas situaciones en el marco de las relaciones de pareja 🤔")
  then(Mesage_18)
end

```

<!-- { section: "737e0f80-2fe0-4dcb-ad34-5f791fbc5938", x: 16464, y: 384} -->

```stack
card Mesage_18, "Mesage_18",
  version: "1",
  uuid: "76403693-41af-5a2e-9738-86c3881afd06",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Mesage_18 =
    buttons(["Le digo que bueno ✅", "Digo NO así se enoje", "No estoy segura 🤷"]) do
      text(
        "Imagínate que la pareja de Mari le ha pedido que deje de ir a entrenar su deporte favorito para estar con él. ¿Qué crees que harías tú si estuvieras en esa situación?"
      )
    end

  then(Message18_1 when ref_Mesage_18 == "Le digo que bueno ✅")
  then(Message18_2 when ref_Mesage_18 == "Digo NO así se enoje")
  then(Message18_3 when ref_Mesage_18 == "No estoy segura 🤷")
  then(Catch_all_9)
end

```

<!-- { section: "28df6e5a-2a3f-4d2b-b553-f6edabb64d9a", x: 16416, y: -552} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Mesage_18)
end

```

<!-- { section: "2c698575-e88c-4c99-b0b7-a1872d1c7a97", x: 18456, y: 264} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Es importante considerar tus propios intereses y no sacrificar lo que te gusta por complacer a tu pareja. Reconocer lo que es importante para ti te ayuda a mantener tu identidad y bienestar en la relación 🫶"
  )

  then(Message_20)
end

```

<!-- { section: "d493ed3b-b297-4689-91d9-390a91b031b2", x: 19128, y: 360} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["Ansiosa y abrumada🥺", "Un poco incómoda🤔", "No es para tanto 🙄"]) do
      text(
        "Otra cosa que ha hecho el novio de Mari es pedirle fotos intímas. Ella se llegó a sentir muy presionada por él para enviarle una foto. Como tu sabes, este tipo de situaciones son comunes actualmente...  📸

¿Cómo crees que se siente Marí estando bajo presión para hacer algo incómodo?"
      )
    end

  then(Message20_1 when ref_Message_20 == "Ansiosa y abrumada🥺")
  then(Message20_2 when ref_Message_20 == "Un poco incómoda🤔")
  then(Message20_3 when ref_Message_20 == "No es para tanto 🙄")
  then(Catch_all_10)
end

```

<!-- { section: "5b7fbae1-5a7e-4dfd-b480-00b765a7dd0e", x: 20760, y: -24} -->

```stack
card Message_21_1, "Message_21_1",
  version: "1",
  uuid: "a1a8abf5-80a1-551b-893d-f420016ccec9",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Sí! Tristemente, en esta situación es normal que una persona se sienta ansiosa y abrumada, pues esta presión puede hacer que dude de sí misma y de sus decisiones 😣 

Estas situaciones pueden hacerle sentir que no tiene el control y que está sola o que no pueden pedir ayuda. Si alguien está en esta situación, es importante poder hablarlo con alguien en su red de apoyo y que se sienta acompañada y no juzgada 🫰"
  )

  then(Message_22)
end

```

<!-- { section: "6b8dc7fa-5efe-4895-9629-0a0df5cee35b", x: 20760, y: 744} -->

```stack
card Message_21_2, "Message_21_2",
  version: "1",
  uuid: "15086714-192f-5851-b22d-ba86a09f629e",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Aunque parezca algo menor y de lo que uno puede zafarse fácil, en esta situación es normal que una persona se sienta ansiosa y abrumada, pues esta presión puede hacer que dude de sí misma y de sus decisiones 😣 

Estas situaciones pueden hacerle sentir que no tiene el control y que está sola o que no pueden pedir ayuda. Si alguien está en esta situación, es importante poder hablarlo con alguien en su red de apoyo y que se sienta acompañada y no juzgada 🫰"
  )

  then(Message_22)
end

```

<!-- { section: "255af5b3-2c47-47eb-b8da-3884b0576876", x: 20784, y: 1512} -->

```stack
card Message_21_3, "Message_21_3",
  version: "1",
  uuid: "c8490566-c6b5-54e6-bc27-0e8e88a3bd8a",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Aunque hay personas que se pueden sentir más fuertes para evitar una situación como esta, en este caso es normal que una persona se sienta ansiosa y abrumada, pues la presión puede hacer que duden de sí mismas y de sus decisiones 😣 

Estas situaciones pueden hacerle sentir a alguien que no tiene el control y que está sola o que no puede pedir ayuda. Si alguien está en esta situación, es importante poder hablarlo con una persona de su red de apoyo y que se sienta acompañada y no juzgada 🫰"
  )

  then(Message_22)
end

```

<!-- { section: "d45ee219-7974-42d0-ae2d-eeae945fce0c", x: 19032, y: -816} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_20)
end

```

<!-- { section: "732b9ab2-1691-4d05-8ad5-c644366f47e8", x: 21984, y: 600} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Súper, ya completaste el episodio 4 del podcast! 🥳 Hoy tengo más stickers para que los puedas usar y te ayuden a recordar lo increíble que eres 🤩"
      )
    end

  write_result("message_22", ref_Message_22)
  then(Message_23_sticker_1 when ref_Message_22 == "¡Manda mis stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "b5251fc3-99ea-4dba-b8a9-ae685b58f5ed", x: 21984, y: -744} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_22)
end

```

<!-- { section: "9266c86f-7135-4af2-8993-375a218e9f60", x: 22704, y: -168} -->

```stack
card Message_23_sticker_1, "Message_23_sticker_1",
  version: "1",
  uuid: "d95ef041-20e2-5f86-8caa-291e871c10b9",
  code_generator: "MEDIA_IMAGE" do
  image("47f36c32-8cc3-471e-82b9-f6a38514f980-Módulo4_AltoAhi.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "2d2a71fa-0ceb-4443-b071-95a589658b44", x: 23352, y: 624} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["¡Entendido!  🫡"]) do
      text(
        "¡Vas 4 de 6 días de racha en el reto del podcast! Vas con toda por tu racha perfecta 🌟"
      )
    end

  write_result("message_24", ref_Message_24)
  then(Message_25 when ref_Message_24 == "¡Entendido!  🫡")
  then(Catch_all_12)
end

```

<!-- { section: "8e24cfcd-4ddc-49ed-8b80-2a76b735d5a8", x: 23400, y: -288} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_24)
end

```

<!-- { section: "de569d8c-1e09-43ee-83dc-2f006be1d503", x: 24168, y: 624} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Apoyada", "Poderosa", "Libre"]) do
      text(
        "Ahora te voy a dejar este reto: ¿Recuerdas ese superpoder que tienes? Para mañana, piensa en una vez en que este superpoder haya marcado la diferencia para ti. Puede ser un logro en particular o tan solo ejemplos de un buen día. ¿Cómo te hizo sentir?"
      )
    end

  then(Message25_1 when ref_Message_25 == "Apoyada")
  then(Message25_2 when ref_Message_25 == "Poderosa")
  then(Message25_3 when ref_Message_25 == "Libre")
  then(Catch_all_13)
end

```

<!-- { section: "5467d4be-fdeb-4a40-a659-1528e16e53c1", x: 24120, y: -336} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_25)
end

```

<!-- { section: "85b859f8-3651-4a82-af92-263bb1aeedd3", x: 26688, y: 744} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["Entendido 🌸"]) do
      text(
        "¡Lo máximo amiga! Sigue sintiéndote así y por ahora esto fue todo por hoy ¡Prepárate porque en el episodio de mañana hablaremos sobre los límites en las relaciones de pareja o amistad! ❤️"
      )
    end

  then(Message_27 when ref_Message_26 == "Entendido 🌸")
  then(Catch_all_14)
end

```

<!-- { section: "d26a64a8-94b2-42d1-b28b-5390fcde7828", x: 27144, y: 744} -->

```stack
card Message_27, "Message_27",
  version: "1",
  uuid: "58095b08-ea56-5e0f-9bba-0cdfec59e6c4",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_c75e44)
end

```

<!-- { section: "0355a52f-7bd0-4cb4-94b8-6d1dd1d0e575", x: 26688, y: 528} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "29fd27f6-47f0-5aec-8054-b4d312e8fcca",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_26)
end

```

<!-- { section: "a3ddbd91-dcd3-4e74-b20a-45559dbb76fe", x: 27600, y: 744} -->

```stack
card Profile_c75e44, "Profile_c75e44",
  version: "1",
  uuid: "e7ab96f5-bb7c-5edc-8a23-b68cadecd4dc",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_4")
  then(ModuleCompleted)
end

```

<!-- { section: "6635289b-86c2-4429-8561-95a6480e19a5", x: 11520, y: -120} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "MEDIA_AUDIO" do
  audio("0e7fd008-1b1f-498f-baa7-353029d3f7f5-G_M4_P3.mp3")
  then(Message_14)
end

```

<!-- { section: "eb063146-8b6e-4e0e-80fd-0387a751a7fa", x: 22704, y: 336} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("35c77fce-b609-4a99-9edc-a2ce8fe0a29a-Módulo4_No.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "7b17026f-1231-4aea-9f8d-aa22dfb3abab", x: 22728, y: 864} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("6cc01d32-a170-49bb-a6ea-2e8f178bb6b0-Módulo4_Nograsias.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "a7e9bdea-699f-42d4-ba7b-fd965aea1b4b", x: 22704, y: 1392} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("273e63f8-8e87-43ff-9d96-65fee48dfdf3-Módulo4_Toma.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "c2685e37-d009-4f5c-9486-466463acdf60", x: 22680, y: 1896} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("e2d6c2ab-e34e-4b02-bffa-c1d819bd8888-Módulo4_Ubicación1.webp")
  text("")
  then(Sticker_6)
end

```

<!-- { section: "547c5c29-fb1a-4314-ac95-ac5ca9fc2f7b", x: 23280, y: 1848} -->

```stack
card Sticker_6, "Sticker_6",
  version: "1",
  uuid: "2f5f19f0-537c-54f3-a374-1691bbfa7557",
  code_generator: "MEDIA_IMAGE" do
  image("53e6ebbb-0e72-4807-8ac6-ccb7442f54e3-Módulo4_Ubicación2.webp")
  text("")
  then(Message_24)
end

```

<!-- { section: "a5443ce8-9905-424d-a957-94f05584290c", x: 25752, y: 744} -->

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

<!-- { section: "59f42749-fc5e-4350-94cd-6240c9af56db", x: 26184, y: 744} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text("• Línea MAAD: lineamaad@uniandes.edu.co

• Ombudsperson: ombudsperson@uniandes.edu.co

• Decanatura de Estudiantes: centrodeapoyo@uniandes.edu.co

• Consejerxs MAAD: ombudsperson.uniandes.edu.co/maqd1/consejerxs-maad")
  then(Message_26)
end

```

<!-- { section: "eb23f200-ef04-4c90-b30e-fb5c779192ba", x: 6528, y: -72} -->

```stack
card Branch_1f3902, "Branch_1f3902",
  version: "1",
  uuid: "e7f1e79d-f324-59f0-9086-3c090ef6ad74",
  code_generator: "CONDITIONALS" do
  then(Message10 when event.message.type == "audio")
  then(Message10 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "65e957e5-a132-4d27-b0a6-f2e14ec7930d", x: 6144, y: 432} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_10)
end

```

<!-- { section: "666cb4b6-5935-451b-861f-5f23c9d4ef48", x: 216, y: -72} -->

```stack
card Message1 do
  write_result("module4_started", "yes")
  then(Message_2)
end

```

<!-- { section: "73d55665-bf29-42d9-99da-d3cdac71eccb", x: 7056, y: -72} -->

```stack
card Message10 do
  write_result("module4_self_reflection", "@ref_message_10")
  then(Message_11)
end

```

<!-- { section: "a6b8d1a8-3cd0-403e-b843-c5a6f0a02c75", x: 28152, y: 744} -->

```stack
card ModuleCompleted do
  log("Module 4 Complete")
  write_result("module4_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "fd7b5b27-1eaa-4ad7-ae40-07222f186df5", x: 1512, y: -72} -->

```stack
card Message2_1 do
  write_result("module4_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "f0369185-ee5d-4a3d-9359-c15cadfc7548", x: 1512, y: 288} -->

```stack
card Message2_2 do
  write_result("module4_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "fd7ab27d-9c30-41e8-bf8c-d45298f6d21f", x: 9888, y: -312} -->

```stack
card Message12_1 do
  write_result("module4_general", "a")
  then(Message_13_1)
end

```

<!-- { section: "88e10bdf-4818-4cd9-b2c6-e5b22450ed48", x: 9888, y: 72} -->

```stack
card Message12_2 do
  write_result("module4_general", "b")
  then(Message_13_2)
end

```

<!-- { section: "e2f078f8-8313-49d2-84f5-a424003c6eb2", x: 9888, y: 456} -->

```stack
card Message12_3 do
  write_result("module4_general", "c")
  then(Message_13_3)
end

```

<!-- { section: "b444a41f-bbd8-4511-b972-bc320bfcf56f", x: 13920, y: -216} -->

```stack
card Message15_1 do
  write_result("module4_beliefs_self_efficacy", "a")
  then(Message_16_1)
end

```

<!-- { section: "99ef11b4-5069-4122-83e7-2d4914fccdb2", x: 13968, y: 144} -->

```stack
card Message15_2 do
  write_result("module4_beliefs_self_efficacy", "b")
  then(Message_16_2)
end

```

<!-- { section: "b3f953a5-9ef7-4cc4-80f2-b35dcb1282d6", x: 13992, y: 504} -->

```stack
card Message15_3 do
  write_result("module4_beliefs_self_efficacy", "c")
  then(Message_16_3)
end

```

<!-- { section: "1c658a5f-4f7e-4c51-adf1-52a3a363fd45", x: 17328, y: 24} -->

```stack
card Message18_1 do
  write_result("module4_attitudes", "a")
  then(Message_19)
end

```

<!-- { section: "3a4f2061-c7f0-4261-bd3f-bdcb17f3bde9", x: 17352, y: 504} -->

```stack
card Message18_2 do
  write_result("module4_attitudes", "b")
  then(Message_19)
end

```

<!-- { section: "a13ba882-7473-4415-9ff1-ad14cc4e0421", x: 17424, y: 936} -->

```stack
card Message18_3 do
  write_result("module4_attitudes", "c")
  then(Message_19)
end

```

<!-- { section: "69ab0955-610b-4065-b736-be6144ccea7a", x: 19848, y: 336} -->

```stack
card Message20_1 do
  write_result("module4_attitudes2", "a")
  then(Message_21_1)
end

```

<!-- { section: "266b6745-bb73-4e07-b37f-280c21640429", x: 19872, y: 720} -->

```stack
card Message20_2 do
  write_result("module4_attitudes2", "b")
  then(Message_21_2)
end

```

<!-- { section: "7049dc27-287c-41a0-b154-8fa3baf04a85", x: 19872, y: 1104} -->

```stack
card Message20_3 do
  write_result("module4_attitudes2", "c")
  then(Message_21_3)
end

```

<!-- { section: "6db5db72-f5e8-48de-8cb9-a69754f9a8d1", x: 24912, y: 216} -->

```stack
card Message25_1 do
  write_result("module4_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "b3ea9938-e294-4071-9c70-f2af0bc7c5a7", x: 24912, y: 744} -->

```stack
card Message25_2 do
  write_result("module4_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "74ca6f9b-7616-4555-baa0-28a0780f4ac6", x: 24912, y: 1176} -->

```stack
card Message25_3 do
  write_result("module4_behavioral_activation", "c")
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
<!-- { section: "33b5c65d-d5a4-4ac5-b54a-f9f962310f43", x: -2856, y: 0} -->

```stack
card Branch_9e8873, "Branch_9e8873",
  version: "1",
  uuid: "7012f2dc-0243-55cf-a046-06ccc5cd125d",
  code_generator: "CONDITIONALS" do
  then(Message_1 when contact.onboarding_complete == true and contact.arm == "NARRATIVE")
  then(RunStack_b303a2_1 when contact.onboarding_complete == true and contact.arm == "GAMIFIED")

  then(
    RunStack_c74805_1
    when contact.onboarding_complete == false and contact.arm == "GAMIFIED"
  )

  then(RunStack_e4ca89_1)
end

```

<!-- { section: "b89b84a5-3a57-447c-9a61-fc9fbb37bc8a", x: -2232, y: 0} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_1 =
    buttons(["¡Entendido! 👍"]) do
      text(
        "*¡Hola!* 👋
Hoy escucharemos el primer episodio de la historia de Pilar. Este primer episodio tiene un audio y una serie de preguntas para saber tu opinión"
      )
    end

  then(Message1 when ref_Message_1 == "¡Entendido! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "8692c7af-9e84-468d-bddc-2ef210368db9", x: -528, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Recuerda que si hay algo de la historia de Pilar o alguna pregunta que te hace sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!"
  )

  then(Message_3)
end

```

<!-- { section: "6d94ae39-7d04-442c-96a8-85e050e2d30e", x: -2232, y: -168} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_1)
end

```

<!-- { section: "527d1236-1265-49fe-8486-9b1178af5ef4", x: -48, y: 0} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "MEDIA_AUDIO" do
  audio("21594b45-b101-4267-a7c2-1435aa7d9c63-M1_P1_A1.mp3")
  then(Message_4)
end

```

<!-- { section: "05f0810d-feb2-45ed-9a2f-0665d5af62cc", x: 408, y: 0} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_4", ref_Message_4)
  then(Message_5 when ref_Message_4 == "Ya escuché el audio!")
  then(Catch_all_2)
end

```

<!-- { section: "fff941c7-a81f-4390-ac2b-87d4877ee56b", x: 408, y: -264} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_4)
end

```

<!-- { section: "6749eb76-bc0d-4c6f-8db5-64854590a2b4", x: 912, y: 0} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "QUESTION" do
  ref_Message_5 =
    ask(
      "¿Qué opinas de lo que te cuento sobre Pilar? ¿Crees que si alguien te busca todo el tiempo y te llama muy seguido es tierno o una forma de control? 🧐 *Puedes responder usando texto o notas de voz*"
    )

  then(Branch_ffa09f)
end

```

<!-- { section: "965f1b12-f9e0-48df-9aab-0afb0bbde99f", x: 2640, y: -264} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_7)
end

```

<!-- { section: "5960547b-0821-4094-ba4f-e16d3ad88923", x: 2232, y: 0} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "TEXT_MESSAGE" do
  text("Gracias por tu respuesta ✨")
  then(Message_7)
end

```

<!-- { section: "92f5b077-c01c-4812-9c98-d07282eecb9e", x: 2640, y: 0} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["La estaba cuidando💖", "La controlaba 🚫", " No estoy segura 😕"]) do
      text(
        "En la historia vimos que Camilo tenía una app para saber dónde estaba Pilar todo el tiempo ¿Qué piensas de eso?"
      )
    end

  then(Message7_1 when ref_Message_7 == "La estaba cuidando💖")
  then(Message7_2 when ref_Message_7 == "La controlaba 🚫")
  then(Message7_3 when ref_Message_7 == " No estoy segura 😕")
  then(Catch_all_3)
end

```

<!-- { section: "d80836be-0d32-4e44-aad4-4f0c93cc19ed", x: 4104, y: 0} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Está bien cuidarse, pero hay una línea entre el cuidado💖 y el control 🚫. Señales de que alguien está ejerciendo control es que nos pongamos nerviosas o nos sintamos vigiladas, que el novio se enoje si no sabe nuestro paradero siempre, o que sintamos que no podemos movernos libremente. Tu tranquilidad es lo más importante"
      )
    end

  write_result("message_8", ref_Message_8)
  then(Message_9 when ref_Message_8 == "Siguiente pregunta")
  then(Catch_all_24)
end

```

<!-- { section: "d9b1f368-72b5-4984-84b9-3f8e4950a42a", x: 4632, y: 0} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Dáselas 📱", "¡No! Es privado 🗣️", "No sé 🤷"]) do
      text(
        "¿Qué le dirias a una amiga si su novio, como Camilo, le insistiera que le dé las contraseñas y usuarios de todas sus redes?"
      )
    end

  then(Message9_1 when ref_Message_9 == "Dáselas 📱")
  then(Message9_2 when ref_Message_9 == "¡No! Es privado 🗣️")
  then(Message9_3 when ref_Message_9 == "No sé 🤷")
  then(Catch_all_4)
end

```

<!-- { section: "28baad4e-2922-4068-8f79-fb59147133c0", x: 4632, y: -576} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_9)
end

```

<!-- { section: "ff0e41ad-5d53-4369-b794-ceba236eeeb3", x: 5736, y: 216} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Tus redes sociales son parte de tu vida privada y solo tú puedes decidir si te sientes cómoda compartiéndolas. Algo en qué pensar es que quien tenga acceso a tus redes tiene mucho poder sobre ti -- tiene toda tu información y puede mandar mensajes a tu nombre. 

¿A tu amiga le insisten? ¿Se siente presionada de dar las contraseñas? Si es así, puede ser una señal de alerta de que es controlador, no protector 🚫"
  )

  then(Message_11_)
end

```

<!-- { section: "ba3a4880-0d4a-4fd1-a135-876fd3ee1a11", x: 6240, y: 216} -->

```stack
card Message_11_, "Message_11_",
  version: "1",
  uuid: "7cadbd10-97d6-55dd-ba9d-ff103177acc6",
  code_generator: "MEDIA_AUDIO" do
  audio("d1934682-b199-4e1a-b017-b9d88add7edf-M1_P2_A1.mp3")
  then(Message_12_)
end

```

<!-- { section: "eb09cb06-03b7-494a-b49e-c1654fe3fdfd", x: 6792, y: 168} -->

```stack
card Message_12_, "Message_12_",
  version: "1",
  uuid: "7aed0933-edce-5bfa-9ad6-88a944f61160",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_ =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_12", ref_Message_12_)
  then(Message_13 when ref_Message_12_ == "Ya escuché el audio")
  then(Catch_all_6)
end

```

<!-- { section: "d9219333-b42c-4d73-b654-ff97608cd83f", x: 6792, y: -168} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_12_)
end

```

<!-- { section: "56710db0-e931-4cb3-bea7-205eb6a243a4", x: 7440, y: 216} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Dile, se afana🌹", "Mala señal 🚨", "No estoy segura🤔"]) do
      text(
        "¿Qué pensarían *tus amigas* si el chico con el que sales es el más papacito del universidad y, a la vez, te pide que digas dónde estás todo el tiempo porque, si no, se enoja?"
      )
    end

  then(Message13_1 when ref_Message_13 == "Dile, se afana🌹")
  then(Message13_2 when ref_Message_13 == "Mala señal 🚨")
  then(Message13_3 when ref_Message_13 == "No estoy segura🤔")
  then(Catch_all_7)
end

```

<!-- { section: "bce36266-c683-4e2d-a976-0dc2c7ab39b4", x: 7440, y: -72} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_13)
end

```

<!-- { section: "cd0d9f6d-23b2-4f7e-a10d-12c14187f94b", x: 8760, y: -96} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Que sea el más papacito de la universidad no justifica que debas estar con él. Si alguien te pide que le informes todo el tiempo dónde estás y se enoja si no lo haces, podría ser una señal de control. Piensa en cómo te hace sentir y si es realmente lo que quieres en una relación. Si oyes algo así, recuérdale a tus amigas que una pareja debe confiar en ti, no vigilarte"
  )

  then(Message_15)
end

```

<!-- { section: "66e333f3-95ae-461a-9542-1635e7a0bf91", x: 8760, y: 336} -->

```stack
card Message_14_2, "Message_14_2",
  version: "1",
  uuid: "13ae0f9a-19f2-570a-ae71-2231bf17343a",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Exacto! Si alguien te pide que le informes todo el tiempo dónde estás y se enoja si no lo haces, podría ser una señal de control. Piensa en cómo te hace sentir y si es realmente lo que quieres en una relación. Si oyes algo así, recuérdale a tus amigas que una pareja debe confiar en ti, no vigilarte"
  )

  then(Message_15)
end

```

<!-- { section: "bd7e65c8-b59a-4a10-8bbb-cf2219c7a05c", x: 8760, y: 792} -->

```stack
card Message_14_3, "Message_14_3",
  version: "1",
  uuid: "1b0aa090-eaab-531e-b1a8-6e733cb2cb59",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Es normal dudar, pero si alguien te pide que le informes todo el tiempo dónde estás y se enoja si no lo haces, podría ser una señal de control. Piensa en cómo te hace sentir y si es realmente lo que quieres en una relación. Si oyes algo así, recuérdale a tus amigas que una pareja debe confiar en ti, no vigilarte"
  )

  then(Message_15)
end

```

<!-- { section: "8ff8ea27-ddde-490c-9332-54f6728abf93", x: 9984, y: 480} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "TEXT_MESSAGE" do
  text(
    "A veces estamos ocupadas y es normal. Es sano poner límites con nuestra pareja y avisarles que no siempre podemos estar pegadas al celular 💁‍♀️"
  )

  then(Message_16_1)
end

```

<!-- { section: "a8f4dbdd-26b5-442e-a4e0-18c4cd2ef11b", x: 10584, y: 192} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_16_1)
end

```

<!-- { section: "7cc678fb-5be8-4ec2-84b2-4c7d3cc278ef", x: 10584, y: 480} -->

```stack
card Message_16_1, "Message_16_1",
  version: "1",
  uuid: "79d2db01-2ced-5381-8796-6f1fb81d9335",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_1 =
    buttons(["¡Quiero stickers!"]) do
      text(
        "¡Muy bien! Has llegado al final del primer episodio de la historia de Pilar 🥳

Son temas complejos, por ello para ayudarte a navegarlos te dejo unos stickers buenísimos sobre este tema y que puedes usar para responder si llegas a vivir algo similar"
      )
    end

  write_result("message_16", ref_Message_16_1)
  then(Message_17_sticker_1 when ref_Message_16_1 == "¡Quiero stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "e9b90b5c-e788-4ea4-9c3f-a505c059ece0", x: 11136, y: 288} -->

```stack
card Message_17_sticker_1, "Message_17_sticker_1",
  version: "1",
  uuid: "95e0aa92-72d6-5d86-ab3d-a9c99660bbbc",
  code_generator: "MEDIA_IMAGE" do
  image("865b771d-b5c6-49ba-a021-1857231122a4-Modulo1__Ubi-Copy.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "4eeece07-f6a3-4f36-be64-a831e8bb28aa", x: 14472, y: 288} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["Amigas 👯‍♀️", "Mamá 👩‍👧", "Familia 💗"]) do
      text(
        "Ahora te voy a dejar un reto: Para mañana, charla con alguien sobre este tema. Pregúntales qué opinan. ¿Con quién quieres hablar?"
      )
    end

  then(Message19_1 when ref_Message_19 == "Amigas 👯‍♀️")
  then(Message19_2 when ref_Message_19 == "Mamá 👩‍👧")
  then(Message19_3 when ref_Message_19 == "Familia 💗")
  then(Catch_all_22)
end

```

<!-- { section: "a02dbb47-2481-4d65-893c-da3a628f3cd8", x: 14472, y: 48} -->

```stack
card Catch_all_22, "Catch_all_22",
  version: "1",
  uuid: "d726a2f0-f36b-5c79-a2fc-f33706cb5037",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_19)
end

```

<!-- { section: "f686568b-38d0-4871-a284-46d1a71f8d5e", x: 16680, y: 312} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["¡Quiero saberlo!🧐"]) do
      text(
        "Ok amiga, esto fue todo por hoy. ¡Prepárate porque el episodio de mañana va a estar increíble! ¿Por qué crees que el policía habrá llamado a la mamá de Pilar?"
      )
    end

  write_result("message_20", ref_Message_20)
  then(Message_21 when ref_Message_20 == "¡Quiero saberlo!🧐")
  then(Catch_all_23)
end

```

<!-- { section: "f840dfff-20e9-4424-9674-9fda54585ef3", x: 16680, y: 24} -->

```stack
card Catch_all_23, "Catch_all_23",
  version: "1",
  uuid: "83142d06-58d1-5ed3-a212-b36817b976a4",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_20)
end

```

<!-- { section: "78c933f8-8b5a-468b-a6a4-834d8b075b33", x: 17232, y: 312} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_c9a342)
end

```

<!-- { section: "7c4bc9c3-c0fe-4723-a021-d28de3969e15", x: 4104, y: -600} -->

```stack
card Catch_all_24, "Catch_all_24",
  version: "1",
  uuid: "6ebc3da7-1ca1-505a-8e92-68d3144096bc",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_8)
end

```

<!-- { section: "e7f4b7a9-57e9-414d-84ce-9509d68557a8", x: 12984, y: 288} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "QUESTION" do
  ref_Message_18 =
    ask(
      "¿Crees que aprendiste algo nuevo hoy? Cuéntanos brevemente qué aprendiste. Recuerda que puedes responder *usando texto o notas de voz*"
    )

  then(Branch_3aa2b4)
end

```

<!-- { section: "0a72c68e-4cb7-4b94-bc0e-ee02f2710a39", x: 17760, y: 312} -->

```stack
card Profile_c9a342, "Profile_c9a342",
  version: "1",
  uuid: "73c3d4c5-7cf1-592f-a09b-5abd7f4cb6bf",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_1")
  then(ModuleCompleted)
end

```

<!-- { section: "dff57023-1a4e-427d-b78e-684623a3afc5", x: 11496, y: 288} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("6d5b7f58-dd0d-4377-8af0-ab11e38d3a78-Modulo1_DateCuenta-Copy.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "f15ab419-7384-4d16-ace9-670b970ad269", x: 11856, y: 288} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("cc932072-d409-4ed4-b8af-8545490d3b85-Modulo1_DejaDeLlamarme-Copy.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "4d56e2e9-af59-4486-881a-2ab00c167323", x: 12192, y: 288} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("97fc11e7-5e8c-44a4-8e74-94aeed76ca4d-Modulo1_Ewww-Copy.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "326b43ab-49c2-470a-b610-95c01011449a", x: 12528, y: 288} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("901a5db7-89b8-4482-abf3-e821813d7de6-Modulo1_Limites-Copy.webp")
  text("")
  then(Message_18)
end

```

<!-- { section: "6d41319b-9a78-416d-a34a-fa5bc07a7f90", x: 1320, y: 0} -->

```stack
card Branch_ffa09f, "Branch_ffa09f",
  version: "1",
  uuid: "392044d7-4960-5bf9-afcf-8cde20f21837",
  code_generator: "CONDITIONALS" do
  then(Message5 when event.message.type == "audio")
  then(Message5 when event.message.type == "text")
  then(Text_245dd4)
end

```

<!-- { section: "6b0ff0d2-e920-49c5-a032-eed67d64a216", x: 912, y: 456} -->

```stack
card Text_245dd4, "Text_245dd4",
  version: "1",
  uuid: "8c4f1b16-248f-5d1d-9118-4facdfc215ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_5)
end

```

<!-- { section: "d72da249-0aa4-4c01-8a13-1a3c933deeaa", x: 13536, y: 288} -->

```stack
card Branch_3aa2b4, "Branch_3aa2b4",
  version: "1",
  uuid: "b2bad0f1-2958-5330-8267-728e401750aa",
  code_generator: "CONDITIONALS" do
  then(Message18 when event.message.type == "audio")
  then(Message18 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "80f7c31f-b142-403d-b6fd-896a9cdfda60", x: 12984, y: 648} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_18)
end

```

<!-- { section: "a56bd1be-c032-4437-ad06-9e2e783feb3b", x: 15720, y: 312} -->

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

<!-- { section: "68ea2150-612b-420d-9289-fedcfa5c47d7", x: 16152, y: 312} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text("• Línea MAAD: lineamaad@uniandes.edu.co

• Ombudsperson: ombudsperson@uniandes.edu.co

• Decanatura de Estudiantes: centrodeapoyo@uniandes.edu.co

• Consejerxs MAAD: ombudsperson.uniandes.edu.co/maqd1/consejerxs-maad")
  then(Message_20)
end

```

<!-- { section: "d6a20efd-d3e3-42ac-bce3-5b5fb47149be", x: -2232, y: 384} -->

```stack
card RunStack_b303a2_1, "RunStack_b303a2_1",
  version: "1",
  uuid: "e23f4b7d-a163-4cc5-97f0-d1fb66cee3d8",
  code_generator: "RUN_STACK" do
  run_stack("bf54c800-5e51-495e-945c-44b0621988f3")
end

```

<!-- { section: "c586cc10-50e2-4c28-a02a-1c31deb6d35c", x: -2232, y: 528} -->

```stack
card RunStack_c74805_1, "RunStack_c74805_1",
  version: "1",
  uuid: "95262ea5-8b2f-48b4-99b2-3021bbbeb39f",
  code_generator: "RUN_STACK" do
  run_stack("c9305344-217c-47a2-9cce-0f1f59ef8c65")
end

```

<!-- { section: "37e05f6c-ccd2-4e34-98e2-c9c3fc0d0463", x: -2232, y: 672} -->

```stack
card RunStack_e4ca89_1, "RunStack_e4ca89_1",
  version: "1",
  uuid: "cf5c4c5d-c1a0-43b8-8738-4a835f8d3c62",
  code_generator: "RUN_STACK" do
  run_stack("8797ac14-3047-40b4-be6c-5fcbfde38e1b")
end

```

<!-- { section: "2c36c2b3-5b88-4167-840d-7e9648e1ca63", x: -3336, y: -192} -->

Content Master sheet is here:

https://docs.google.com/spreadsheets/d/14JAmTFuQ8fX4kSq18ETyNOZ3jzjjCykP/edit?usp=sharing&ouid=112722710667683232518&rtpof=true&sd=true

<!-- { section: "fc7f4ffe-11d6-4b4e-b165-60459fd3f07b", x: 1704, y: 0} -->

```stack
card Message5 do
  log("Saving message 5 response")
  write_result("module1_boundaries", "@ref_message_5")
  then(Message_6)
end

```

<!-- { section: "ae5e6e21-9029-4473-90bf-61204b58a5c3", x: 13968, y: 288} -->

```stack
card Message18 do
  write_result("module1_learnings", "@ref_message_18")
  then(Message_19)
end

```

<!-- { section: "662a3f4f-e39b-4347-b9c6-d1165396cbf2", x: 18216, y: 312} -->

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

<!-- { section: "1cc142ae-3305-43a2-ba94-3021e0fafa0f", x: -1152, y: 0} -->

```stack
card Message1 do
  write_result("module1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "b74c70e4-b0a8-498b-bf8d-ac9836750c4f", x: 3168, y: -264} -->

```stack
card Message7_1 do
  write_result("module1_beliefs", "a")
  then(Message_8)
end

```

<!-- { section: "2b7fcac3-8c8f-4248-9885-eee5b8e41ef2", x: 3168, y: 72} -->

```stack
card Message7_2 do
  write_result("module1_beliefs", "b")
  then(Message_8)
end

```

<!-- { section: "122a3c62-2a53-457e-94b5-cd88ed40fa03", x: 3168, y: 384} -->

```stack
card Message7_3 do
  write_result("module1_beliefs", "c")
  then(Message_8)
end

```

<!-- { section: "0190917d-aec1-4de6-9a11-2d23cdfcda05", x: 5112, y: -144} -->

```stack
card Message9_1 do
  write_result("module1_attitudes", "a")
  then(Message_10)
end

```

<!-- { section: "2e52a41b-1335-4e66-97a6-1570bfac513c", x: 5112, y: 168} -->

```stack
card Message9_2 do
  write_result("module1_attitudes", "b")
  then(Message_10)
end

```

<!-- { section: "121b408e-099b-420b-a319-717455aab102", x: 5112, y: 480} -->

```stack
card Message9_3 do
  write_result("module1_attitudes", "c")
  then(Message_10)
end

```

<!-- { section: "f6cbbc25-7cef-4da1-a312-e98904c19802", x: 7968, y: -96} -->

```stack
card Message13_1 do
  write_result("module1_social_norms", "a")
  then(Message_14_1)
end

```

<!-- { section: "52ecf497-8a7a-4b2c-b0d6-f9687dd992a9", x: 7968, y: 336} -->

```stack
card Message13_2 do
  write_result("module1_social_norms", "b")
  then(Message_14_2)
end

```

<!-- { section: "25a25efa-1d2f-4b36-8f95-7b67d213eba0", x: 7968, y: 792} -->

```stack
card Message13_3 do
  write_result("module1_social_norms", "c")
  then(Message_14_3)
end

```

<!-- { section: "e8084333-eb71-4bca-8e9a-30a4e4e57fff", x: 15072, y: 0} -->

```stack
card Message19_1 do
  write_result("module1_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "a090c76d-f2d6-4775-9628-c8d56fbc2141", x: 15072, y: 408} -->

```stack
card Message19_2 do
  write_result("module1_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "9ef5c175-b809-46fe-8ffc-9ffaa12edae3", x: 15072, y: 816} -->

```stack
card Message19_3 do
  write_result("module1_behavioral_activation", "c")
  then(Safe_Guarding_1)
end

```

<!-- { section: "5a486567-ca15-4fbf-ae56-d3aea927a7d7", x: -3288, y: 48} -->

```stack
card RESERVED_TRIGGER, "RESERVED_TRIGGER", code_generator: "RESERVED_TRIGGER" do
  # placeholder_trigger
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
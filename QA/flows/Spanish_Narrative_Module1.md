<!-- { section: "6b151134-1b99-4541-b010-8d2aea223e53", x: -2304, y: 144} -->

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

<!-- { section: "2b2ef48b-c615-455a-94c7-cb5ddf6fd95b", x: -1752, y: -72} -->

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

<!-- { section: "d98e6106-3c51-432d-a38d-6e748815ab36", x: -1704, y: -672} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_1)
end

```

<!-- { section: "62e7f46d-3731-4f3d-a1f7-e8f5a202b8ff", x: -24, y: 24} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "MEDIA_AUDIO" do
  audio("21594b45-b101-4267-a7c2-1435aa7d9c63-M1_P1_A1.mp3")
  then(Message_4)
end

```

<!-- { section: "660dbdc1-7610-49e9-9863-adc423241229", x: 408, y: -24} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_5 when ref_Message_4 == "Ya escuché el audio!")
  then(Catch_all_2)
end

```

<!-- { section: "0e95448b-925b-40f3-be60-b9f5a159aeee", x: 480, y: -528} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_4)
end

```

<!-- { section: "3a193799-c074-4069-aa3d-2b0f20e143dc", x: 912, y: 72} -->

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

<!-- { section: "47a7cc1c-6276-4944-a48c-515df801993a", x: 2448, y: -648} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_7)
end

```

<!-- { section: "a955c338-9327-44e0-878a-4cd0bbf29530", x: 2232, y: 48} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "TEXT_MESSAGE" do
  text("Gracias por tu respuesta ✨")
  then(Message_7)
end

```

<!-- { section: "23fb2ae2-57b1-4224-aa4c-f2282a279933", x: 2640, y: 24} -->

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

<!-- { section: "88e88d06-9888-4b70-9b98-5c9681c4512f", x: 4104, y: 96} -->

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

  then(Message_9 when ref_Message_8 == "Siguiente pregunta")
  then(Catch_all_24)
end

```

<!-- { section: "9130242c-d6e2-43cd-baf9-28bcac0600f4", x: 4632, y: 96} -->

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

<!-- { section: "515d9d2d-ac70-441c-b46c-090031e7be7d", x: 6072, y: -552} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
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

  then(Message_13 when ref_Message_12_ == "Ya escuché el audio")
  then(Catch_all_6)
end

```

<!-- { section: "654093aa-5467-40be-8965-024cb1452885", x: 6744, y: -600} -->

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
        "¿Qué pensarían *tus amigas* si el chico con el que sales es el más papacito del colegio y, a la vez, te pide que digas dónde estás todo el tiempo porque, si no, se enoja?"
      )
    end

  then(Message13_1 when ref_Message_13 == "Dile, se afana🌹")
  then(Message13_2 when ref_Message_13 == "Mala señal 🚨")
  then(Message13_3 when ref_Message_13 == "No estoy segura🤔")
  then(Catch_all_7)
end

```

<!-- { section: "60d7ec08-5492-4e4f-ae51-1e1a34f2403c", x: 7344, y: -600} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_13)
end

```

<!-- { section: "32671c7d-8c5f-4de5-b55d-beb09122be65", x: 8760, y: -72} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Que sea el más papacito del colegio no justifica que debas estar con él. Si alguien te pide que le informes todo el tiempo dónde estás y se enoja si no lo haces, podría ser una señal de control. Piensa en cómo te hace sentir y si es realmente lo que quieres en una relación. Si oyes algo así, recuérdale a tus amigas que una pareja debe confiar en ti, no vigilarte"
  )

  then(Message_15)
end

```

<!-- { section: "cbd6b9c4-603a-4d2a-a65d-2c042c6ba9ed", x: 8712, y: -792} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
end

```

<!-- { section: "30a3b124-fb7b-4c2e-9c81-60919e7c07f8", x: 8736, y: 672} -->

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

<!-- { section: "1c0d1871-c59a-4f69-9a1b-8d60014f0c67", x: 8712, y: 1608} -->

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

<!-- { section: "ffbf63a6-9382-4afe-88fb-362bb8b8146d", x: 7896, y: 1104} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "fe99366e-34ec-4db3-9885-1a39ef4315ad", x: 8256, y: 2280} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
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

<!-- { section: "c498aaba-c09c-47fe-a71d-77cd8b6dc9fc", x: 10440, y: -720} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_16_1)
end

```

<!-- { section: "49e2a5f0-46b4-4d0d-a8a1-7683f3ebd6cc", x: 10800, y: -720} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
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

  then(Message_17_sticker_1 when ref_Message_16_1 == "¡Quiero stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "1560bed6-634c-4e07-85fc-87e9b745a933", x: 11616, y: -744} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
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

<!-- { section: "a4ccc7ee-dc8d-4ce2-97d6-bbeaaa9fb262", x: 14472, y: 144} -->

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

<!-- { section: "96f963b7-ee88-4f4c-98aa-e353218f5592", x: 14592, y: -504} -->

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

  then(Message_21 when ref_Message_20 == "¡Quiero saberlo!🧐")
  then(Catch_all_23)
end

```

<!-- { section: "1a00645d-7998-486d-a1a2-a28fad172690", x: 16776, y: -984} -->

```stack
card Catch_all_23, "Catch_all_23",
  version: "1",
  uuid: "83142d06-58d1-5ed3-a212-b36817b976a4",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_20)
end

```

<!-- { section: "2fd44b51-23ba-4e44-9c64-559334a1d13f", x: 17232, y: 360} -->

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

<!-- { section: "a1c0bb42-90e3-4ab4-a6eb-b345ee4d2269", x: 13128, y: 264} -->

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

<!-- { section: "0f79fa9d-d1a4-4118-9d3a-535d3bbbc312", x: 17768, y: 360} -->

```stack
card Profile_c9a342, "Profile_c9a342",
  version: "1",
  uuid: "73c3d4c5-7cf1-592f-a09b-5abd7f4cb6bf",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_1")
  then(ModuleCompleted)
end

```

<!-- { section: "638dabf4-4e47-4020-a934-685bd2372480", x: 11472, y: 312} -->

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

<!-- { section: "402f3dfe-1fa5-41a3-be26-91da8d42e0c6", x: 12264, y: 288} -->

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

<!-- { section: "ed17344f-65f8-426b-84fa-2e91e9606d5a", x: 12648, y: 288} -->

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

<!-- { section: "ede2c9f5-122d-4271-b79a-7a69010c3ce2", x: 1320, y: 72} -->

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

<!-- { section: "e9e2f4fb-2c4e-4c80-812f-5c46a9473b13", x: 1008, y: 648} -->

```stack
card Text_245dd4, "Text_245dd4",
  version: "1",
  uuid: "8c4f1b16-248f-5d1d-9118-4facdfc215ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_5)
end

```

<!-- { section: "554491c1-c446-41e6-80d3-b0b70be41eeb", x: 13544, y: 192} -->

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

<!-- { section: "4fcb72a3-ebf2-479f-b4dd-5c8802947a88", x: 13392, y: 648} -->

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
  text(
    "1. Línea Púrpura (WhatsApp): +57 300 7551846 o *Visita aquí* https://www.sdmujer.gov.co/nuestros-servicios/servicios-para-las-mujeres/linea-purpura  
2. Línea 141 (ICBF) – Atención 24/7
3. Reporte en Línea: *Te Protejo* https://teprotejocolombia.org/"
  )

  then(Message_20)
end

```

<!-- { section: "435a6a8c-d6b1-4f38-965b-35f4c2771046", x: -1776, y: 384} -->

```stack
card RunStack_b303a2_1, "RunStack_b303a2_1",
  version: "1",
  uuid: "e23f4b7d-a163-4cc5-97f0-d1fb66cee3d8",
  code_generator: "RUN_STACK" do
  run_stack("bf54c800-5e51-495e-945c-44b0621988f3")
end

```

<!-- { section: "edd5743d-43d6-4226-99c1-b675f77e1202", x: -1776, y: 528} -->

```stack
card RunStack_c74805_1, "RunStack_c74805_1",
  version: "1",
  uuid: "95262ea5-8b2f-48b4-99b2-3021bbbeb39f",
  code_generator: "RUN_STACK" do
  run_stack("c9305344-217c-47a2-9cce-0f1f59ef8c65")
end

```

<!-- { section: "d9404747-093c-4099-81e9-d6b00f5c151b", x: -1776, y: 672} -->

```stack
card RunStack_e4ca89_1, "RunStack_e4ca89_1",
  version: "1",
  uuid: "cf5c4c5d-c1a0-43b8-8738-4a835f8d3c62",
  code_generator: "RUN_STACK" do
  run_stack("8797ac14-3047-40b4-be6c-5fcbfde38e1b")
end

```

<!-- { section: "1bab17e8-6697-4f30-b15f-48d1fc70282f", x: 1704, y: 48} -->

```stack
card Message5 do
  log("Saving message 5 response")
  write_result("module1_boundaries", "@ref_message_5")
  then(Message_6)
end

```

<!-- { section: "ba2bb9a6-89db-4dc9-8c4e-0129ca81b9b0", x: 13968, y: 120} -->

```stack
card Message18 do
  write_result("module1_learnings", "@ref_message_18")
  then(Message_19)
end

```

<!-- { section: "c5309665-9699-4276-9ed1-5b206bb6357c", x: 18216, y: 288} -->

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

<!-- { section: "aa4f23dc-f3e0-4d4e-b7b6-7ff2d78b0d47", x: 7968, y: 288} -->

```stack
card Message13_2 do
  write_result("module1_social_norms", "b")
  then(Message_14_2)
end

```

<!-- { section: "5f698f7d-07e0-428c-a9e9-c437e996703d", x: 7968, y: 624} -->

```stack
card Message13_3 do
  write_result("module1_social_norms", "c")
  then(Message_14_3)
end

```

<!-- { section: "c980a29a-d554-4883-821a-0fc53b8ec00f", x: 15120, y: 0} -->

```stack
card Message19_1 do
  write_result("module1_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "8ad04aaf-6bb4-4987-9703-0f8c756fcfc3", x: 15096, y: 408} -->

```stack
card Message19_2 do
  write_result("module1_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "a396415c-dca1-42a4-97ac-62a6b612a912", x: 15072, y: 744} -->

```stack
card Message19_3 do
  write_result("module1_behavioral_activation", "c")
  then(Safe_Guarding_1)
end

```

<!-- { section: "92405471-8c13-4441-8ebe-3320e79f5562", x: -2808, y: -168} -->

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
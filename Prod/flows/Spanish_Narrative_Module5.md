<!-- { section: "4fbcbcae-d80d-4219-aeb8-09b809dbc39a", x: -1608, y: 144} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_n5")

trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_4" and contact.onboarding_complete == true and
       contact.arm == "NARRATIVE"

```

<!-- { section: "694cd9b1-8d60-43f6-bd4b-13916b331945", x: -1128, y: 144} -->

```stack
card Insight_2, "Insight_2",
  version: "1",
  uuid: "7ab75811-dcd1-4330-aeb0-3010acfb94d0",
  code_generator: "WRITE_RESULTS" do
  write_result("module5_started", "yes")
  then(Template_1)
end

```

<!-- { section: "80f8d722-1a60-43e1-a0d6-34530d5c64b6", x: 1128, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "Súper bien 👍"]) do
      text(
        "El reto de ayer era pensar en una vez que tu superpoder fue importante para ti ¿Cómo te fue con el reto de ayer?"
      )
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "Súper bien 👍")
  then(Catch_all_1)
end

```

<!-- { section: "0fed580a-fd8b-4627-a44c-6bf07de4f7ee", x: 1200, y: -936} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "3bf15a54-348e-4b7e-b21f-3a1075d11c4d", x: 2328, y: -264} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "No te preocupes, ¡busca tiempo hoy para hacerlo! Pensar en lo que valoras y en lo que eres increíble te da confianza y energía 💫"
  )

  then(Message_4)
end

```

<!-- { section: "9006532a-136d-4f96-9d55-5c5d79612e05", x: 2304, y: 336} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Increíble, pensar en lo que valoras y en lo que eres increíble te da confianza y energía. ¡Sigue haciéndolo! 🫶"
  )

  then(Message_4)
end

```

<!-- { section: "e27b6a2e-d09d-47ec-9c86-9d29f026a0dd", x: 2928, y: 120} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este episodio, sabremos qué plan harán Pilar y Laura para enfrentar a Camilo. ¡Acompáñame a saber qué hicieron!"
  )

  then(Message_5)
end

```

<!-- { section: "d54c2686-5e60-469c-a606-79ab91096bc3", x: 3528, y: -960} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_5)
end

```

<!-- { section: "224ff3bf-1d98-4f69-9b45-974e4edd2c86", x: 3384, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Ok 👌"]) do
      text(
        "Recuerda que si algo te hace sentir incómoda, puedes parar y volver te sientas lista. ¡Lo más importante es que te sientas bien!"
      )
    end

  write_result("message_5", ref_Message_5)
  then(Message_6 when ref_Message_5 == "Ok 👌")
  then(Catch_all_2)
end

```

<!-- { section: "86a9e438-c9e8-4123-8486-83250f03d881", x: 3864, y: 120} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "MEDIA_AUDIO" do
  audio("ff37c8af-fb01-4426-be0e-ec3a037dc114-M5_P1_A1.mp3")
  then(Message_7)
end

```

<!-- { section: "f37231ac-ffdd-4d8f-a5d3-55d83b0cf7d7", x: 4776, y: -888} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "57ba6f06-9d49-4757-ba1b-f7c96dae85bb", x: 4344, y: 120} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_7", ref_Message_7)
  then(Message_8 when ref_Message_7 == "Ya escuché el audio")
  then(Catch_all_3)
end

```

<!-- { section: "c613a9c3-c7d7-4c01-a8fd-5fd832c794d4", x: 4968, y: 120} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "QUESTION" do
  ref_Message_8 =
    ask(
      "En el episodio escuchamos que Pilar le dice a sus amigas que lo que le pasó fue quizás porque no supo cómo poner límites con Camilo, ya que ella no sabía muy bien lo que quería en su relación. ¡Es importante saber lo que una quiere!

¿Alguna vez le has puesto límites a tu relación? 🛑  Sin importar si lo has hecho o no, dime 3 límites que tu crees que son importantes para ti."
    )

  then(Branch_c6cd99)
end

```

<!-- { section: "8071bc95-9da4-4be0-b260-ccdc55c64f20", x: 6552, y: 144} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Que bueno que tengas claros cuáles son tus límites! Recuerda que es importante que siempre te sientas cómoda y está bien que le puedas decir a otros qué te incomoda🙌"
  )

  then(Message_10)
end

```

<!-- { section: "79f8996e-2cfa-4040-8161-57ab7b316c36", x: 13392, y: 1056} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14_2)
end

```

<!-- { section: "d21a8d58-f3e3-4c2e-b29b-d91e9b940f9c", x: 7176, y: 144} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["¡Pelear duro! 😡", "Calmarse y hablar 🕒", "Mejor dejar así 👍"]) do
      text(
        "En el episodio, escuchamos que Laura le aconseja a Pilar llamar a Camilo para que ella pueda sacarse la espina, para que pueda cantárselas como se debe y decirle lo tóxico que es 😡😡
¿Qué crees tú que debería hacer Pili en esta situación? 🤔"
      )
    end

  then(Message10_1 when ref_Message_10 == "¡Pelear duro! 😡")
  then(Message10_2 when ref_Message_10 == "Calmarse y hablar 🕒")
  then(Message10_3 when ref_Message_10 == "Mejor dejar así 👍")
  then(Catch_all_21)
end

```

<!-- { section: "9fdd3a94-2354-4492-9a84-a917f0214a3e", x: 9264, y: 384} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11 =
    buttons(["Siguiente audio"]) do
      text(
        "Las conversaciones son de 2. Expresar lo que sentimos es importante, pero hacerlo desde el enojo o el deseo de venganza puede no ser efectivo. Lo mejor es que Pilar pueda hacerlo desde la comunicación asertiva, donde pueda decir lo que siente con firmeza sin necesidad de caer en la venganza. 

Recuerda que la comunicación también incluye la escucha y el propósito debe ser constructivo."
      )
    end

  write_result("message_11", ref_Message_11)
  then(Message_12_1 when ref_Message_11 == "Siguiente audio")
  then(Catch_all_6)
end

```

<!-- { section: "0b265fb1-b0d5-45d5-9fd7-4d049612f84c", x: 9360, y: -912} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11)
end

```

<!-- { section: "50e7fdc8-4a76-49fe-ba8a-a017e9e6b7c2", x: 10704, y: 504} -->

```stack
card Message_12_2, "Message_12_2",
  version: "1",
  uuid: "19e8e572-ef79-5524-bebc-52b7c1aa75ab",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_2 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_12", ref_Message_12_2)
  then(Message_13 when ref_Message_12_2 == "Ya escuché el audio!")
  then(Catch_all_9)
end

```

<!-- { section: "bfedccce-9899-4422-8098-17818526e49b", x: 11712, y: 528} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Igual, lo funo 😡", "No hago nada🤫", "Hablo con un adulto"]) do
      text(
        "En el episodio, Pilar consideró \"funar\" a Camilo en redes sociales porque pensó que él había compartido su foto. Si estuvieras en la situación de Pilar, ¿cómo manejarías tus sentimientos y qué límites establecerías? 🤔 Recuerda que ser asertiva es importante, pero es fundamental hacerlo de manera productiva, sin apresurarte a juzgar o actuar sin conocer toda la verdad."
      )
    end

  then(Message13_1 when ref_Message_13 == "Igual, lo funo 😡")
  then(Message13_2 when ref_Message_13 == "No hago nada🤫")
  then(Message13_3 when ref_Message_13 == "Hablo con un adulto")
  then(Catch_all_10)
end

```

<!-- { section: "fd9b25ba-d8c0-4ae3-bce2-7cbb8fee2b63", x: 10752, y: -96} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12_2)
end

```

<!-- { section: "3d8bbd16-e56e-418d-af53-b9823abdcc5e", x: 11688, y: -504} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13)
end

```

<!-- { section: "9d185be4-6022-4e8f-b41f-9de02a8a79f1", x: 13824, y: 240} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_1 =
    buttons(["Siguiente parte"]) do
      text(
        "Aunque es una situación molesta donde quisieras hacer justicia, recuerda que \"funar\" a alguien puede tener consecuencias graves. La comunicación asertiva es la habilidad de expresar tus pensamientos y sentimientos de manera honesta y respetuosa🫰

En lugar de actuar desde la rabia, considera averiguar primero qué fue lo que pasó y hablar con una persona adulta de confianza. Esto puede ayudarte a tomar mejores decisiones 💛"
      )
    end

  write_result("message_14", ref_Message_14_1)
  then(Message_15 when ref_Message_14_1 == "Siguiente parte")
  then(Catch_all_11)
end

```

<!-- { section: "113189d5-7c1a-4ca1-b537-38b1f3a797c9", x: 13776, y: 1704} -->

```stack
card Message_14_3, "Message_14_3",
  version: "1",
  uuid: "1b0aa090-eaab-531e-b1a8-6e733cb2cb59",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_3 =
    buttons(["Siguiente parte"]) do
      text(
        "Hablar con una persona adulta en quien confíes *es una excelente opción*. Ellos pueden ofrecerte una perspectiva diferente y ayudarte a comunicarte asertivamente, para que puedas defender tus derechos y expresar tus emociones de manera directa y respetuosa💪

Contar con la experiencia de alguien de confianza puede guiarte para abordar el problema de manera efectiva y constructiva, sin escalar la situación innecesariamente 💛"
      )
    end

  write_result("message_14", ref_Message_14_3)
  then(Message_15 when ref_Message_14_3 == "Siguiente parte")
  then(Catch_all_12)
end

```

<!-- { section: "c63a8a01-7780-4452-b766-e9122b908dd8", x: 13560, y: -456} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14_1)
end

```

<!-- { section: "5eb96af7-4f01-422e-ae92-00c7b88754e7", x: 12792, y: 2040} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14_3)
end

```

<!-- { section: "e85de88d-3dbb-4b43-8786-373671e42ed7", x: 14712, y: 960} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Muy bien! Has escuchado el episodio 5 de la historia de Pilar 🥳

Son temas complejos, por ello para ayudarte a navegarlos, te dejo unos stickers buenísimos sobre este tema y que puedes usar para responder si llegas a vivir algo similar"
      )
    end

  write_result("message_15", ref_Message_15)
  then(Message_16_sticker_1 when ref_Message_15 == "¡Manda mis stickers!")
  then(Catch_all_13)
end

```

<!-- { section: "513482eb-f5fa-4bdf-82ed-38811f76b126", x: 14736, y: 96} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "e1d6cadc-0c0d-448d-aef5-a8323890730f", x: 15408, y: 1032} -->

```stack
card Message_16_sticker_1, "Message_16_sticker_1",
  version: "1",
  uuid: "27e75053-f1f8-5ea6-bcd8-89a20844c146",
  code_generator: "MEDIA_IMAGE" do
  image("16544410-4000-4956-ae82-e162cfb14fb0-Módulo5_Escudo.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "0646c03b-96ec-4e47-aa65-900044c2ceed", x: 20592, y: 1152} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Poner límites", "Decir kesi y keno!", "Pelear sanamente"]) do
      text(
        "Ahora, te voy a dejar este reto: Para mañana, charla con alguien sobre este tema. Piensa en una pareja romántica o de amigas famosas, que sea ejemplo de lo que hablamos hoy ¿En qué te quieres enfocar?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Poner límites")
  then(Message18_2 when ref_Message_18 == "Decir kesi y keno!")
  then(Message18_3 when ref_Message_18 == "Pelear sanamente")
  then(Catch_all_19)
end

```

<!-- { section: "f63ab93d-b999-46ab-8c3d-1cb0f05f73c7", x: 20568, y: 384} -->

```stack
card Catch_all_19, "Catch_all_19",
  version: "1",
  uuid: "aa2b872e-9152-5c35-9ece-d9c72a2f6ea0",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18)
end

```

<!-- { section: "e1ad23af-6bac-47b8-ac85-6cf3363358ec", x: 23640, y: 1320} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["¡Quiero saberlo!🧐"]) do
      text(
        "Ok, amiga, esto fue todo por hoy. ¡Prepárate porque este último episodio va a estar increíble! ¿Qué pasará entre Pilar y Mari? ¿Crees que seguirán siendo amigas?"
      )
    end

  write_result("message_19", ref_Message_19)
  then(Profile_6cade8 when ref_Message_19 == "¡Quiero saberlo!🧐")
  then(Catch_all_20)
end

```

<!-- { section: "f43d5948-3cea-448d-a4b1-cca0f0fa05d3", x: 24600, y: 1320} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(ModuleCompleted)
end

```

<!-- { section: "5193724e-0266-4437-8b0d-c30f42d269e2", x: 23640, y: 1080} -->

```stack
card Catch_all_20, "Catch_all_20",
  version: "1",
  uuid: "33422d10-445d-5f76-96c9-e793d4011333",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_19)
end

```

<!-- { section: "00bb7b5c-0166-40f5-94e4-044c0c4eb6b1", x: 7248, y: -816} -->

```stack
card Catch_all_21, "Catch_all_21",
  version: "1",
  uuid: "317ddc77-c862-5558-91a3-6d411d930f0a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "d7dffdb0-c5b4-404a-8842-e89bdb79a63b", x: 24168, y: 1320} -->

```stack
card Profile_6cade8, "Profile_6cade8",
  version: "1",
  uuid: "37e92b60-50d0-5540-8c1f-a3f0e3924bde",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_5")
  then(Message_20)
end

```

<!-- { section: "3cbe243d-34c4-431e-84dc-decd4e78d323", x: 10032, y: 504} -->

```stack
card Message_12_1, "Message_12_1",
  version: "1",
  uuid: "b3faf013-4802-5596-99ea-9df4b6c14c5b",
  code_generator: "MEDIA_AUDIO" do
  audio("f3954594-dfd5-419b-bcd7-d9964f7dd595-M5_P2_A1.mp3")
  then(Message_12_2)
end

```

<!-- { section: "f1cc64d9-2520-4bc3-8281-76144944d038", x: 13848, y: 888} -->

```stack
card Message_14_2, "Message_14_2",
  version: "1",
  uuid: "13ae0f9a-19f2-570a-ae71-2231bf17343a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_2 =
    buttons(["Siguiente parte"]) do
      text(
        "A veces, no hacer nada puede parecer la opción más tranquila, pero tu voz también debe ser escuchada. La comunicación asertiva implica expresar tus sentimientos y necesidades de forma clara, sin dejarte llevar por la ira 🫰

Investigar la situación y hablar con un adulto de confianza puede ofrecerte claridad sobre lo que realmente ocurrió y cómo proceder de la mejor manera 💛"
      )
    end

  write_result("message_14", ref_Message_14_2)
  then(Message_15 when ref_Message_14_2 == "Siguiente parte")
  then(Catch_all_5)
end

```

<!-- { section: "ca015651-a1b8-4d6f-9110-b4df0d6d00d1", x: 18624, y: 1032} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "QUESTION" do
  ref_Message_17 =
    ask(
      "¡Es hora de practicar! ¿Cómo le dirías a un(a) amigo(a) o novio(a) que no quieres hacer algo?"
    )

  then(Branch_51e71a)
end

```

<!-- { section: "01cf5937-3d97-4a44-a076-04f911f8facd", x: 16128, y: 1032} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("d7b2ea5d-d873-45ac-8011-d8e12ff23d15-Módulo5_EstoyIncomoda.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "5233a2da-1e26-4643-bd4f-8dec37eb7252", x: 16848, y: 1056} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("2e97846d-3849-4abf-8ef5-1f5adab5635f-Módulo5_Ganamos.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "5fd3b1cc-9601-45c0-b6af-d5678b2ab40e", x: 17448, y: 1056} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("715f492c-0ccd-4349-af03-d22577a759cb-Modulo5_Llamame-Copy.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "2be243eb-b595-4b1a-a12d-a8961c8b1820", x: 17976, y: 1032} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("88bbf0b5-e436-408e-b9c6-8ffa25fc8430-Modulo5_Yallegue-Copy.webp")
  text("")
  then(Message_17)
end

```

<!-- { section: "561417e3-30af-4670-9060-583fa8e1db9f", x: 22680, y: 1320} -->

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

<!-- { section: "dbd5bb10-595b-45c5-b254-337684fe50b7", x: 23136, y: 1320} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text("• Línea MAAD: lineamaad@uniandes.edu.co

• Ombudsperson: ombudsperson@uniandes.edu.co

• Decanatura de Estudiantes: centrodeapoyo@uniandes.edu.co

• Consejerxs MAAD: ombudsperson.uniandes.edu.co/maqd1/consejerxs-maad")
  then(Message_19)
end

```

<!-- { section: "882c38f1-c883-4cc9-b5bd-6abf34921fe4", x: 5456, y: 120} -->

```stack
card Branch_c6cd99, "Branch_c6cd99",
  version: "1",
  uuid: "af005834-e3d7-523e-8c3c-2a269855cb10",
  code_generator: "CONDITIONALS" do
  then(Message8 when event.message.type == "audio")
  then(Message8 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "b605774d-0202-45a3-94c9-a4d2a82db3a3", x: 5304, y: 792} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_8)
end

```

<!-- { section: "ff3f28f0-dba1-43ce-aa32-c814ba5f31db", x: 19112, y: 1032} -->

```stack
card Branch_51e71a, "Branch_51e71a",
  version: "1",
  uuid: "8eddf2a0-9914-55c5-b123-5039ec5f5e4c",
  code_generator: "CONDITIONALS" do
  then(Message17 when event.message.type == "audio")
  then(Message17 when event.message.type == "text")
  then(Catch_all_2_2)
end

```

<!-- { section: "833083cb-5c8e-4b72-9c08-40091bbb8ef1", x: 18720, y: 1536} -->

```stack
card Catch_all_2_2, "Catch_all_2_2",
  version: "1",
  uuid: "86031531-4763-5dde-ab3c-b02fc964194a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_17)
end

```

<!-- { section: "08aaf359-ee08-4239-9b90-14ee7b6ddf94", x: -48, y: -240} -->

```stack
card Catch_all_22, "Catch_all_22",
  version: "1",
  uuid: "4deecd97-aa84-450d-bda2-c34d08908ab6",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "7074982f-aefb-4706-835e-a5a6790fe6f5", x: 240, y: 72} -->

```stack
card Insight_1, "Insight_1",
  version: "1",
  uuid: "5c6dc271-ec0b-42c5-9632-0cf13fcbac1e",
  code_generator: "WRITE_RESULTS" do
  write_result("template_1", "¡Cuéntame más!")
  then(Message_2)
end

```

<!-- { section: "be849975-c7fa-4ec0-9adb-427a693530a8", x: -624, y: 144} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "0abb9d4a-54c2-4d72-bb0a-415d46c7365b",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_narrative_mod5", "es", [], buttons: ["¡Cuéntame más!"])

  then(Insight_1 when ref_Template_1.index == 0)
  then(Catch_all_22)
end

```

<!-- { section: "99dd46da-2b76-4ddc-8bc8-9aa8dc31210f", x: 2376, y: 552} -->

Emoji does not show up

<!-- { section: "98d1afbc-fa51-4ad7-8de3-9743fc914223", x: 25056, y: 2016} -->

**@Buhle**

Schedule Quiz Post Module 5 to start next day (6pm ,\
Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "24d9e28c-b7fa-441a-b249-420c310319b4", x: 1296, y: 432} -->

**@Buhle**

Please save these variables here

<!-- { section: "aecffaf1-7bee-49be-9e09-7a668c407e7a", x: 5880, y: 432} -->

**@Buhle**

Save user response here

This is a DS field, not sure which you need so you have both

**DS note:** Flow result: module5_boundaries {user input}

<!-- { section: "715de481-b4e4-452b-a761-1cf20b1a334e", x: 7200, y: 624} -->

**@Buhle**

Please save variables here

<!-- { section: "e393ddca-5c9f-4849-a10c-aed9e4e1499d", x: 11808, y: 1128} -->

**@Buhle**

Please save the insights here

<!-- { section: "cba37cb4-81e2-4eb8-bf49-89bd9ee3a5a4", x: 19608, y: 1560} -->

**@Buhle**\
Please save the insights here

its a DS thing so added in the code block just in case**

DS note:** Flow result: module5_boundaries2 {user input}

<!-- { section: "35acb938-b530-4369-b489-948f6d12244b", x: 20640, y: 1680} -->

**@Buhle**

Please save insights here

<!-- { section: "54bf1544-821b-472e-945e-86282429d6a9", x: 25056, y: 1800} -->

**@Buhle**

**DS note:** Flow result: module5_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "01911bc0-6d52-4ad3-937d-f13a4a69e6f6", x: 10032, y: 696} -->

add audio file here

<!-- { section: "d9845b41-5ef9-4490-b381-4b7f47dee2b3", x: 25032, y: 1320} -->

```stack
card ModuleCompleted do
  log("Module 5 Complete")
  write_result("module5_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "3fcc41ef-5ac4-4991-9c73-0e0a99e9fe0f", x: 5880, y: 72} -->

```stack
card Message8 do
  write_result("module5_boundaries", "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "2429bb07-a8f1-4f77-8cbb-e68b301d6943", x: 19656, y: 1032} -->

```stack
card Message17 do
  write_result("module5_boundaries2", "@ref_message_17")
  then(Message_18)
end

```

<!-- { section: "09d04459-b249-4fe0-9772-0465e13cbfcd", x: 1680, y: -312} -->

```stack
card Message2_1 do
  write_result("module5_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "13e90381-fe4b-4fa0-a9a8-15a459447dee", x: 1680, y: 240} -->

```stack
card Message2_2 do
  write_result("module5_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "6cbc510c-0116-42d4-b5b0-8a50fbfbd141", x: 7896, y: -216} -->

```stack
card Message10_1 do
  write_result("module5_beliefs", "a")
  then(Message_11)
end

```

<!-- { section: "70788e35-a89c-4a6d-b9fc-9d53de33d971", x: 7920, y: 168} -->

```stack
card Message10_2 do
  write_result("module5_beliefs", "b")
  then(Message_11)
end

```

<!-- { section: "ee2936f8-7630-4749-914e-bba1d00f3e6e", x: 7944, y: 528} -->

```stack
card Message10_3 do
  write_result("module5_beliefs", "c")
  then(Message_11)
end

```

<!-- { section: "9c4530b3-60cf-424f-9401-e3b08bcdc433", x: 12456, y: 192} -->

```stack
card Message13_1 do
  write_result("module5_attitudes", "a")
  then(Message_14_1)
end

```

<!-- { section: "f07522e4-b252-4a8a-b920-552df1d27957", x: 12456, y: 576} -->

```stack
card Message13_2 do
  write_result("module5_attitudes", "b")
  then(Message_14_2)
end

```

<!-- { section: "1276f622-c48b-481b-ade2-98f3bcee34d3", x: 12480, y: 912} -->

```stack
card Message13_3 do
  write_result("module5_attitudes   ", "c")
  then(Message_14_3)
end

```

<!-- { section: "ee0b31ab-6385-4a49-afd0-b7a49bed069c", x: 21528, y: 816} -->

```stack
card Message18_1 do
  write_result("module5_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "ed6399e5-d166-4d34-b9fc-2e3c364ed781", x: 21528, y: 1320} -->

```stack
card Message18_2 do
  write_result("module5_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "d575f0b6-8d05-4806-8722-ddc219dac291", x: 21504, y: 1728} -->

```stack
card Message18_3 do
  write_result("module5_behavioral_activation", "c")
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
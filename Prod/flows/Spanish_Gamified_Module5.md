<!-- { section: "1b06a583-547a-44ce-918c-bd8b571e4b39", x: -552, y: 72} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_g5")

trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_4" and contact.arm == "GAMIFIED" and
       contact.onboarding_complete == true

```

<!-- { section: "48210efc-91bb-45d3-ad14-bbfc5e36d85e", x: -24, y: -24} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "14754edd-bfde-491f-9b5a-0ebe120080c6",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_gamified_mod5", "es", [], buttons: ["¡Cuentame más!"])

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_22)
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

<!-- { section: "5835f5cf-0f0d-4b51-912c-08e3bc88bfe1", x: 2280, y: -72} -->

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

<!-- { section: "65e55505-713e-4f14-9114-8edf8ec8bce0", x: 2904, y: 120} -->

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

<!-- { section: "d3ca8166-fb3c-45f0-8fea-9a5de2810ad6", x: 2928, y: -960} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "50445eaf-7ffd-49e2-8062-7ef2067c9be6", x: 3768, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este episodio, Pilar y Mari hablarán sobre la comunicación y los límites en las relaciones de pareja o amistad 💛"
  )

  then(Message_6)
end

```

<!-- { section: "1a452289-579c-48d8-9656-aa82991b673f", x: 4488, y: 120} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Recuerda que si algo te hace sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Lo más importante es que te sientas bien! 🫰"
      )
    end

  then(Message_7 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "ed01f869-d35e-4358-a671-f2883ca13f5f", x: 4488, y: -888} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6)
end

```

<!-- { section: "ab210c9e-dc09-4eea-9c0b-f049c4037fd3", x: 5016, y: 120} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "MEDIA_AUDIO" do
  audio("a4e45fcb-dc11-44dc-b122-8a0eb8bfcd29-G_M5_P1.mp3")
  then(Message_8)
end

```

<!-- { section: "6bd996f1-9e9f-46df-9150-a8e7e8bcaee5", x: 5424, y: 120} -->

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

<!-- { section: "47233944-5dbc-4a16-b50c-b0448c72a843", x: 5496, y: -840} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_8)
end

```

<!-- { section: "54883052-0884-452c-bc1b-5d589f37c9db", x: 5904, y: 120} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "¿Alguna vez le has puesto límites a tu relación? 🛑  Sin importar si lo has hecho o no, dime 3 límites que tu crees que son importantes para ti"
    )

  then(Branch_07ff2a)
end

```

<!-- { section: "7ba16cc2-4daa-4515-ba79-878fe437779c", x: 7272, y: 144} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Que bueno que tengas claros cuáles son tus límites! Recuerda que es importante que siempre te sientas cómoda y está bien que le puedas decir a otros qué te incomoda 🙌"
  )

  then(Message_11_1)
end

```

<!-- { section: "856fe0a6-8f4e-4408-b5f2-1c22954300cc", x: 8184, y: 144} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_12 when ref_Message_11 == "Ya escuché el audio!")
  then(Catch_all_5)
end

```

<!-- { section: "685446c7-4d6c-4f50-a9f3-121fdb2bd734", x: 7920, y: -912} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11)
end

```

<!-- { section: "23752748-0cbe-4e90-8092-529634f1bcb4", x: 8640, y: 120} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Pelear más duro 😡", "Poner límites 🕒", "La verdad, no sé 🤔"]) do
      text(
        "Volvamos a la pregunta, imaginemos que Pilar y su pareja tienen un desacuerdo y por esto empiezan a discutir de manera fuerte y enojada 😡😡 ¿Qué crees tú que debería hacer Pilar en esta situación? 🤔"
      )
    end

  then(Message12_1 when ref_Message_12 == "Pelear más duro 😡")
  then(Message12_2 when ref_Message_12 == "Poner límites 🕒")
  then(Message12_3 when ref_Message_12 == "La verdad, no sé 🤔")
  then(Catch_all_21)
end

```

<!-- { section: "b19a7c4a-9aa6-4125-a1df-030dc423aa6b", x: 10488, y: -168} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "MEDIA_AUDIO" do
  audio("18a660b2-0c66-4bbd-bc41-c429cd81b00c-G_M5_P2_R1.mp3")
  then(Message_13)
end

```

<!-- { section: "3105d24d-a3df-493c-8fd9-a56b7ac6a4e3", x: 10488, y: 456} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "MEDIA_AUDIO" do
  audio("496aa1e6-877f-494d-9c47-bf494048264a-G_M5_P2_R2.mp3")
  then(Message_13)
end

```

<!-- { section: "9a57ac8b-5d2c-4ea3-a3fb-f1941df08a1b", x: 10464, y: 960} -->

```stack
card Message_13_3, "Message_13_3",
  version: "1",
  uuid: "d0b53090-c491-560e-9fdb-e2ba5b1436df",
  code_generator: "MEDIA_AUDIO" do
  audio("7f5386c9-57fc-43b2-8113-f8898aa58f7f-G_M5_P2_R3.mp3")
  then(Message_13)
end

```

<!-- { section: "098e5e3a-6bfa-45e8-a45b-290eb904e141", x: 16392, y: -360} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_17)
end

```

<!-- { section: "a5672e43-14ad-42d2-a54b-a0a0cd03c3fc", x: 11280, y: 24} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13)
end

```

<!-- { section: "6e8745e5-567c-456f-96b7-7cb0a9db3fbc", x: 12312, y: 528} -->

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
  then(Catch_all_9)
end

```

<!-- { section: "5e781652-95d4-4901-b550-53f37da314b1", x: 13056, y: 552} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Muy empoderada ✅", "Muy intensa", "No estoy segura 🤷"]) do
      text(
        "Entonces, Pilar y su pareja iban a hacer pizza pero cuando el llegó y vio que estaban solos, le dijo a Pilar que mejor podrían tener relaciones sexuales. 

Pilar no quiere así que le respondió *\"me estás poniendo incómoda, ya te dije que yo quiero ir más lento. Si quieres nos podemos abrazar y pasar un rato juntos, pero hasta ahí.\"*

¿Qué piensas de su respuesta?🤔"
      )
    end

  then(Message15_1 when ref_Message_15 == "Muy empoderada ✅")
  then(Message15_2 when ref_Message_15 == "Muy intensa")
  then(Message15_3 when ref_Message_15 == "No estoy segura 🤷")
  then(Catch_all_10)
end

```

<!-- { section: "47ffbb35-edf8-49a6-83a4-1fc946e062b0", x: 12432, y: -168} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "a1d00546-b597-4652-a8d2-2e2519ff75b4", x: 13128, y: -552} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "9e1ed313-5587-4135-8335-9f8ef9e20782", x: 15264, y: 552} -->

```stack
card Message_16_1, "Message_16_1",
  version: "1",
  uuid: "79d2db01-2ced-5381-8796-6f1fb81d9335",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_1 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Poner límites y ser asertivas nunca es intensidad, ¡es nuestra oportunidad de respetarnos a nosotras mismas! Además, nunca tenemos que sentir presión por hacer algo que no queremos, así lo hayamos hecho antes. ¡El amor es chévere cuando las dos personas están listas! 🤗"
      )
    end

  then(Message_17 when ref_Message_16_1 == "Siguiente pregunta")
  then(Catch_all_11)
end

```

<!-- { section: "3626f015-bf41-491b-9bc3-a9a6c48c9ba0", x: 15192, y: 1512} -->

```stack
card Message_16_2, "Message_16_2",
  version: "1",
  uuid: "4736c50d-9290-5ad0-8477-a21bde650bf8",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_2 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Si no te resultaría fácil responder como Pilar, trata de practicar cómo lo harías para mejorar tu confianza💪 Tus necesidades son importantes y deben ser escuchadas y respetadas. Hablar con tus amigas sobre esto puede ser un buen paso para apoyarse mutuamente 💛"
      )
    end

  then(Message_17 when ref_Message_16_2 == "Siguiente pregunta")
  then(Catch_all_12)
end

```

<!-- { section: "58be1280-fde6-4db0-992e-a0ef7c89ba71", x: 15168, y: -264} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16_1)
end

```

<!-- { section: "8f94504f-3d8d-4a28-99c7-087b90792aa5", x: 14880, y: 1200} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16_2)
end

```

<!-- { section: "be8e6db9-94b9-4e77-aded-24a64fd9545a", x: 16440, y: 984} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["Igual, lo funo 😡", "No hago nada🤫", "Hablo con un adulto"]) do
      text(
        "Imagínate que alguien comparte una foto de una amiga y ella considera \"funarlo\". Si estuvieras en el lugar de tu amiga, ¿cómo manejarías tus sentimientos y qué límites establecerías? 🤔 Recuerda que ser asertiva es importante, pero es fundamental hacerlo de manera productiva, sin apresurarte a juzgar o actuar sin conocer toda la verdad."
      )
    end

  then(Message17_1 when ref_Message_17 == "Igual, lo funo 😡")
  then(Message17_2 when ref_Message_17 == "No hago nada🤫")
  then(Message17_3 when ref_Message_17 == "Hablo con un adulto")
  then(Catch_all_6)
end

```

<!-- { section: "43f64f95-849f-430c-aaa5-9494964132d8", x: 18360, y: 264} -->

```stack
card Message_18_1, "Message_18_1",
  version: "1",
  uuid: "8a733211-d7eb-5c2b-9a03-0e4bea4cba0b",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18_1 =
    buttons(["Sigue el podcast"]) do
      text(
        "Aunque es una situación molesta donde quisieras hacer justicia, recuerda que \"funar\" a alguien puede tener consecuencias graves. La comunicación asertiva es la habilidad de expresar tus pensamientos y sentimientos de manera honesta y respetuosa🫰

En lugar de actuar desde la rabia, considera averiguar primero qué fue lo que pasó y hablar con una persona adulta de confianza. Esto puede ayudarte a tomar mejores decisiones 💛"
      )
    end

  then(Message_19_1 when ref_Message_18_1 == "Sigue el podcast")
  then(Catch_all_13)
end

```

<!-- { section: "7f407db8-1333-4a1b-8920-c0aaeeeda141", x: 18408, y: 1176} -->

```stack
card Message_18_2, "Message_18_2",
  version: "1",
  uuid: "f991fbc5-7712-5518-a753-a5e3f160f9ef",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18_2 =
    buttons(["Sigue el podcast"]) do
      text(
        "A veces, no hacer nada puede parecer la opción más tranquila, pero tu voz también debe ser escuchada. La comunicación asertiva implica expresar tus sentimientos y necesidades de forma clara, sin dejarte llevar por la ira 🫰

Investigar la situación y hablar con un adulto de confianza puede ofrecerte claridad sobre lo que realmente ocurrió y cómo proceder de la mejor manera 💛"
      )
    end

  then(Message_19_1 when ref_Message_18_2 == "Sigue el podcast")
  then(Catch_all_14)
end

```

<!-- { section: "8182c099-1a32-4534-863e-b10ab2ce77b3", x: 18240, y: 2232} -->

```stack
card Message_18_3, "Message_18_3",
  version: "1",
  uuid: "8bf10063-4658-5846-a34e-3c68b1167484",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18_3 =
    buttons(["Sigue el podcast"]) do
      text(
        "Hablar con una persona adulta en quien confíes *es una excelente opción*. Ellos pueden ofrecerte una perspectiva diferente y ayudarte a comunicarte asertivamente, para que puedas defender tus derechos y expresar tus emociones de manera directa y respetuosa💪

Contar con la experiencia de alguien de confianza puede guiarte para abordar el problema de manera efectiva y constructiva, sin escalar la situación innecesariamente 💛"
      )
    end

  then(Message_19_1 when ref_Message_18_3 == "Sigue el podcast")
  then(Catch_all_15)
end

```

<!-- { section: "88913ca9-65a3-4b72-bea9-c625d64e1cd2", x: 17904, y: -696} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18_1)
end

```

<!-- { section: "22c57be8-fc18-420f-afe2-1f3f0bc2c87a", x: 18048, y: 912} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "29fd27f6-47f0-5aec-8054-b4d312e8fcca",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18_2)
end

```

<!-- { section: "6329500f-3f34-4cc0-b7e3-708546635b14", x: 18216, y: 1896} -->

```stack
card Catch_all_15, "Catch_all_15",
  version: "1",
  uuid: "4bee0862-bdcd-5844-8df1-4816d420e326",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18_3)
end

```

<!-- { section: "f13ecfb2-38b0-4c1d-8eef-4dedaae1d453", x: 19608, y: 1032} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_20 when ref_Message_19 == "Ya escuché el audio!")
  then(Catch_all_16)
end

```

<!-- { section: "4f35b60f-49e4-40ac-971e-0c7604ce70b6", x: 19512, y: 288} -->

```stack
card Catch_all_16, "Catch_all_16",
  version: "1",
  uuid: "d4296a10-0d55-5756-9088-6b503693c13b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_19)
end

```

<!-- { section: "8fdbbf65-f00c-4778-8eb0-b68d5da9ebd7", x: 20040, y: 864} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "QUESTION" do
  ref_Message_20 =
    ask(
      "¡Es hora de practicar! ¿Cómo le dirías a un(a) amigo(a) o novio(a) que no quieres hacer algo?

Recuerda que puedes *responder con texto o nota de voz*"
    )

  then(Branch_b1534d)
end

```

<!-- { section: "b11f0cf6-03f2-4391-8998-1df6e44473de", x: 21624, y: 1008} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! Acuérdate que, entre más practiquemos como comunicarnos, va a ser más fácil hacerlo en momentos complicados💪 ¡Sigue así!"
  )

  then(Messge_22)
end

```

<!-- { section: "fef27856-bfc6-432a-b68f-8708aab35313", x: 22104, y: 1008} -->

```stack
card Messge_22, "Messge_22",
  version: "1",
  uuid: "ee8efdce-615b-50fa-83b7-6a75e8e473fd",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Messge_22 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Completaste el episodio 5 de nuestro podcast! 🥳 Hoy tengo más stickers para que los puedas usar y te ayuden si algún día te enfrentas a una situación como esta."
      )
    end

  then(Message_23_sticker_1 when ref_Messge_22 == "¡Manda mis stickers!")
  then(Catch_all_17)
end

```

<!-- { section: "64728a0a-2739-4878-9a8e-f7631c8f0db7", x: 21936, y: 384} -->

```stack
card Catch_all_17, "Catch_all_17",
  version: "1",
  uuid: "209ee976-ac39-5434-95b8-eaa8c2de1f85",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Messge_22)
end

```

<!-- { section: "51fabf47-afc5-48e5-bd5e-aa73032d69e8", x: 22800, y: 528} -->

```stack
card Message_23_sticker_1, "Message_23_sticker_1",
  version: "1",
  uuid: "d95ef041-20e2-5f86-8caa-291e871c10b9",
  code_generator: "MEDIA_IMAGE" do
  image("03905b47-66c0-4deb-b8f6-13f9ce5c699e-Módulo5_Escudo.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "5da50a78-1076-4f0a-b368-23413f08f843", x: 23688, y: 984} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["¡Entendido!  🫡"]) do
      text(
        "¡Van 5 de 6 días de racha en el reto del podcast! No olvides escucharnos mañana, solo falta 1 día 💥"
      )
    end

  then(Message_25 when ref_Message_24 == "¡Entendido!  🫡")
  then(Catch_all_18)
end

```

<!-- { section: "b1932f3f-3bea-4c3f-9372-2d50e67a96a8", x: 23184, y: 360} -->

```stack
card Catch_all_18, "Catch_all_18",
  version: "1",
  uuid: "e1b87782-5fd0-51c8-b25e-fa1a45e4e585",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_24)
end

```

<!-- { section: "a4ad70da-de76-439c-b829-649dc22294aa", x: 24288, y: 984} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Poner límites", "Decir kesi y keno!", "Pelear sanamente"]) do
      text(
        "Ahora, te voy a dejar este reto: Para mañana, charla con alguien sobre una pareja que conozcas o famosa que sea un ejemplo de buena comunicación 🤘

¿En qué elemento específico de la comunicación te quieres enfocar?"
      )
    end

  then(Message27_1 when ref_Message_25 == "Poner límites")
  then(Message27_2 when ref_Message_25 == "Decir kesi y keno!")
  then(Message27_3 when ref_Message_25 == "Pelear sanamente")
  then(Catch_all_19)
end

```

<!-- { section: "2bc3134b-3b5a-4a4c-b838-2206bc083aad", x: 23904, y: 384} -->

```stack
card Catch_all_19, "Catch_all_19",
  version: "1",
  uuid: "aa2b872e-9152-5c35-9ece-d9c72a2f6ea0",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_25)
end

```

<!-- { section: "52727d6d-e1e0-48b2-a2cd-d32336138c72", x: 27048, y: 984} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["Entendido 🌸"]) do
      text(
        "Ok, amiga, esto fue todo por hoy. ¡Prepárate porque en el episodio de mañana (el último 😭) hablaremos sobre cómo podemos crear un plan seguro para situaciones de riesgo!⚠️"
      )
    end

  then(Message_27 when ref_Message_26 == "Entendido 🌸")
  then(Catch_all_20)
end

```

<!-- { section: "55ac2351-bfd0-42d7-89bb-d50d8691bfdb", x: 27576, y: 1056} -->

```stack
card Message_27, "Message_27",
  version: "1",
  uuid: "58095b08-ea56-5e0f-9bba-0cdfec59e6c4",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_6cade8)
end

```

<!-- { section: "f1f6ba8d-e847-4a54-a683-2d58e5408644", x: 27048, y: 288} -->

```stack
card Catch_all_20, "Catch_all_20",
  version: "1",
  uuid: "33422d10-445d-5f76-96c9-e793d4011333",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_26)
end

```

<!-- { section: "ad7c1e57-4e21-47ec-bacf-78a4738823de", x: 8592, y: -888} -->

```stack
card Catch_all_21, "Catch_all_21",
  version: "1",
  uuid: "317ddc77-c862-5558-91a3-6d411d930f0a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "2e8b870a-e517-4d9e-8311-ce0d253dc080", x: 27960, y: 1056} -->

```stack
card Profile_6cade8, "Profile_6cade8",
  version: "1",
  uuid: "37e92b60-50d0-5540-8c1f-a3f0e3924bde",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_5")
  then(ModuleCompleted)
end

```

<!-- { section: "bb7cf986-b5b0-4e4b-b96a-c55a126d1aa3", x: 7752, y: 144} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "MEDIA_AUDIO" do
  audio("39992d33-0e78-4fcf-9048-d36dcf7468b8-G_M5_P2.mp3")
  then(Message_11)
end

```

<!-- { section: "0bd43b6c-bacb-4afb-92d0-ed19315a1125", x: 11088, y: 528} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Siguiente pregunta"]) do
      text("Cuando finalice el audio, presione el botón de siguiente pregunta.")
    end

  then(Message_14_1 when ref_Message_13 == "Siguiente pregunta")
  then(Catch_all_7)
end

```

<!-- { section: "c20cf8b2-2b2c-4eab-8449-a66e3ff87e4f", x: 11688, y: 552} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "MEDIA_AUDIO" do
  audio("269d0b17-6231-4bd1-811f-255570192388-G_M5_P3.mp3")
  then(Message_14)
end

```

<!-- { section: "4c1653b3-810d-4cb3-ab60-c6a004ebb2b8", x: 19128, y: 1056} -->

```stack
card Message_19_1, "Message_19_1",
  version: "1",
  uuid: "32b8a8c4-0a85-5c14-80e4-2924274ecd66",
  code_generator: "MEDIA_AUDIO" do
  audio("c5f02e52-26f6-49e4-823a-24427bb1f151-G_M5_P4.mp3")
  then(Message_19)
end

```

<!-- { section: "06109207-d4e5-4e26-8413-1e096f771c62", x: 22776, y: 984} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("07db833e-f369-4b57-ac4a-9d63e648f196-Módulo5_EstoyIncomoda.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "2985b032-5b50-499b-887c-14fbe56619c6", x: 22752, y: 1488} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("fb445f9b-4ee4-4e4d-afb6-8be1853c1288-Módulo5_Ganamos.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "43908efc-afe7-4297-afa4-ead0ffdef06a", x: 22776, y: 2088} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("43b6cf71-c682-467a-b551-e91a2ca6a345-Modulo5_Llamame-Copy.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "1f86aff5-6383-432b-8f1f-1eedde527e66", x: 23304, y: 1992} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("02197ce9-1234-4e49-9680-047685028aa0-Modulo5_Yallegue-Copy.webp")
  text("")
  then(Message_24)
end

```

<!-- { section: "890bb6d1-fb6f-43c3-b11b-8bbf9d3af42a", x: 20528, y: 744} -->

```stack
card Branch_b1534d, "Branch_b1534d",
  version: "1",
  uuid: "b1da7970-8020-5cf8-94b8-ef8dd12475c6",
  code_generator: "CONDITIONALS" do
  then(Message20 when event.message.type == "audio")
  then(Message20 when event.message.type == "text")
  then(Text_c844df)
end

```

<!-- { section: "83bb09e1-a6b6-45a9-87c6-cbca78d6ab41", x: 20352, y: 1200} -->

```stack
card Text_c844df, "Text_c844df",
  version: "1",
  uuid: "6946770c-1b6e-58b3-9275-da8a59af48e3",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_20)
end

```

<!-- { section: "7b197135-15fa-4ad9-891a-69b6d37136dc", x: 6312, y: 96} -->

```stack
card Branch_07ff2a, "Branch_07ff2a",
  version: "1",
  uuid: "fc712edc-abdf-5ffb-b0a8-1266b9fb035e",
  code_generator: "CONDITIONALS" do
  then(Message9 when event.message.type == "audio")
  then(Message9 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "16eabbed-c386-4956-8768-2c8bd29b7a8c", x: 6192, y: 576} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_9)
end

```

<!-- { section: "b7774a80-e2da-40f1-b275-6b4f4ce09841", x: 26064, y: 1080} -->

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

<!-- { section: "8014016a-7806-40e5-84bb-6b4a6734f724", x: 26520, y: 1104} -->

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

  then(Message_26)
end

```

<!-- { section: "2692eed9-91b6-4a81-a03c-c0286f93cbce", x: -24, y: -408} -->

```stack
card Catch_all_22, "Catch_all_22",
  version: "1",
  uuid: "ce6d04d6-dd42-42b0-9c8d-b42c75cef330",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "b707dae4-7ac9-4614-af2f-a67939fe2156", x: 9024, y: 1032} -->

save users response here need a variable /insight name

We cannot have audio as button messages, will need extra copy here

<!-- { section: "a650a181-50ba-49a9-b4cf-7b3c54b4b504", x: 17256, y: 1944} -->

save users response here need a variable /insight name

<!-- { section: "296c283a-87da-45a1-b416-c270b373bd11", x: 23664, y: 1320} -->

emoji does not show up

<!-- { section: "68d902c0-4bf4-4e0f-8cca-b57c4415ec1e", x: 28464, y: 1608} -->

**@Buhle**

Schedule Quiz Post Module 5 to start next day (6pm ,
Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "3c4fae1e-40b9-4021-9dcf-6edc046b0aae", x: 528, y: 432} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module5_started (yes)

<!-- { section: "260a9b54-964b-4520-8d5b-33c25660eb18", x: 6792, y: 408} -->

**@Buhle**

Save user response here

This is a DS field, not sure which you need so you have both

**DS note:** Flow result: module5_boundaries {user input}

<!-- { section: "231e55b4-e402-4d83-bf20-efdf33acbc53", x: 16680, y: 1560} -->

**@Buhle**

Please save the insights here

<!-- { section: "040d65fb-b09a-472c-b4f2-3023cf398f2f", x: 20760, y: 1368} -->

**@Buhle**
Please save the insights here

its a DS thing so added in the code block just in case

**DS note:** Flow result: module5_boundaries2 {user input}

<!-- { section: "427250ac-6b79-4470-b5e0-a4473c5ab1ac", x: 24192, y: 1560} -->

**@Buhle**

Please save insights here

<!-- { section: "28409272-d414-4a09-92e7-8982da34a1fa", x: 27936, y: 1344} -->

**@Buhle**

**DS note:** Flow result: module5_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "37e5f80e-a894-4847-93e3-2a525cc9eedd", x: 27912, y: 1248} -->

Update contact field, contact module = Module 5 ✅

<!-- { section: "d85bf8a1-c343-4afa-bab9-590c0239035b", x: 14352, y: 1608} -->

**16.3 is missing here**

<!-- { section: "bc528b9c-e408-46a4-9c65-6c22efb10b64", x: 28464, y: 1056} -->

```stack
card ModuleCompleted do
  log("Module 6 Complete")
  write_result("module6_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "93e1a921-a953-41df-b7a2-c2f0a50cd4ee", x: 600, y: -24} -->

```stack
card Message1 do
  write_result("module5_started", "yes")
  then(Message_2)
end

```

<!-- { section: "9e5a37aa-008f-45b9-b84d-5538b776a262", x: 21048, y: 960} -->

```stack
card Message20 do
  write_result("module5_boundaries2", "@ref_message_20")
  then(Message_21)
end

```

<!-- { section: "d4eab0d1-c755-4f43-a53d-9d99f1b8702c", x: 1704, y: -168} -->

```stack
card Message2_1 do
  write_result("module5_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "55766e53-fad2-4fd0-9a56-93f611c12da8", x: 1704, y: 216} -->

```stack
card Message2_2 do
  write_result("module5_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "cf8b4f73-7c46-47e6-a5aa-41ba9fad6e89", x: 6792, y: 48} -->

```stack
card Message9 do
  write_result("module5_boundaries", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "fef6d0d8-adad-446b-afe7-265084f20d5f", x: 9240, y: -216} -->

```stack
card Message12_1 do
  write_result("module5_beliefs", "a")
  then(Message_13_1)
end

```

<!-- { section: "73adb7f6-d35c-4c57-97b2-ca26ac7618aa", x: 9312, y: 168} -->

```stack
card Message12_2 do
  write_result("module5_beliefs", "b")
  then(Message_13_2)
end

```

<!-- { section: "8205daed-4044-46f5-a2a5-917c4ffafee5", x: 9240, y: 528} -->

```stack
card Message12_3 do
  write_result("module5_beliefs", "c")
  then(Message_13_3)
end

```

<!-- { section: "9b7847fb-79bb-4d18-84d5-b64823130338", x: 13872, y: 456} -->

```stack
card Message15_1 do
  write_result("module5_attitudes", "a")
  then(Message_16_1)
end

```

<!-- { section: "10cfe1f5-ce26-4507-9ff6-a9dd03f069e2", x: 13848, y: 840} -->

```stack
card Message15_2 do
  write_result("module5_attitudes", "b")
  then(Message_16_1)
end

```

<!-- { section: "b724da04-9e27-4e82-baa0-2bd65356a145", x: 13872, y: 1224} -->

```stack
card Message15_3 do
  write_result("module5_attitudes", "c")
  then(Message_16_2)
end

```

<!-- { section: "94e299b0-19ff-4bd8-baf0-a68ade14064a", x: 17160, y: 720} -->

```stack
card Message17_1 do
  write_result("module5_attitudes2", "a")
  then(Message_18_1)
end

```

<!-- { section: "101a00db-65f9-4df2-b2ea-a9551ee63601", x: 17160, y: 1104} -->

```stack
card Message17_2 do
  write_result("module5_attitudes2", "b")
  then(Message_18_2)
end

```

<!-- { section: "e15444c0-fc29-4bb0-a806-abde413ac777", x: 17232, y: 1512} -->

```stack
card Message17_3 do
  write_result("module5_attitudes2", "c")
  then(Message_18_3)
end

```

<!-- { section: "ea0a273c-db1e-4ae3-b587-41a06a2036d2", x: 24936, y: 744} -->

```stack
card Message27_1 do
  write_result("module5_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "17e18b06-0176-4790-9e69-263090bd7642", x: 24912, y: 1152} -->

```stack
card Message27_2 do
  write_result("module5_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "e2fb205f-2c5c-4c0f-aa4e-9476ea66510f", x: 24960, y: 1632} -->

```stack
card Message27_3 do
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
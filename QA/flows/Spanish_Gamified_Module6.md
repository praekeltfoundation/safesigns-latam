<!-- { section: "876e2ebc-4129-4d45-9560-3ebfe5276c3e", x: -2712, y: -72} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_only_phrase(event.message.text.body, "test_g6_2") or
       (contact.arm == "GAMIFIED" and contact.contact_module == "MODULE_5" and
          contact.quiz_post_module5 == true)

```

<!-- { section: "a564dda9-a0ec-4e50-914b-e0e537706318", x: -1032, y: 0} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¿Estás lista para el último episodio del podcast de Pilar y Mari? ¡Qué rápido ha pasado el tiempo!  🗓️"
  )

  then(Message1)
end

```

<!-- { section: "e8b287c4-9d6e-4290-8750-18c22c8a9d2c", x: 432, y: -48} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "¡Súper! 👍"]) do
      text(
        "El reto de ayer era pensar en una pareja famosa (o no) que fuera un ejemplo buena comunicación en uno de los 3 temas que tocamos: límites, decir que no y discusiones sanas ¿Cómo te fue?"
      )
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "¡Súper! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "00643c20-0d30-4a48-b89d-095b6c78918e", x: 576, y: -1176} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "0d8777b5-9f3c-44fd-a669-be41e517d0c6", x: 1488, y: -216} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text("¡No te preocupes, hoy podrás de ponerte al día!")
  then(Message_4)
end

```

<!-- { section: "485e0b89-2715-4014-b1f5-43a8ffab3b59", x: 1488, y: 360} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Increíble! Hay ejemplos de buena y mala comunicación en todos lados. Ahora los sabes identificar y poner tus límites 👏"
  )

  then(Message_4)
end

```

<!-- { section: "48abe042-7e24-48e5-8e31-f7e8dc5b4c0f", x: 2040, y: 192} -->

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

<!-- { section: "4b963c4e-afa1-4751-ac03-bb647403ed31", x: 1992, y: -864} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "c3481353-d084-4998-882d-c33a1025e1ea", x: 2496, y: 168} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este sexto episodio, Pilar y Mari hablarán sobre cómo podemos crear un plan para situaciones de riesgo⚠️"
  )

  then(Message_6)
end

```

<!-- { section: "9cba54fb-0066-402c-88b3-e848263aee61", x: 2928, y: 168} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Como siempre, si hay algo que te hace sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!"
      )
    end

  then(Message_7 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "5c36c906-8501-4e5d-beb7-4bbf452bc29f", x: 3336, y: -960} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6)
end

```

<!-- { section: "5d85f18d-63fe-487f-95da-99e8b442a7d1", x: 3360, y: 240} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "MEDIA_AUDIO" do
  audio("56001b26-13fd-48e5-9e51-dab43881d223-G_M6_P1.mp3")
  then(Message_8)
end

```

<!-- { section: "10883f85-d46f-4126-a07d-7204782afcf8", x: 3792, y: 216} -->

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

<!-- { section: "49bffbf2-2ff5-49ef-b113-ccc93c0d7081", x: 3888, y: -960} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_8)
end

```

<!-- { section: "628a89f5-9dc7-48a4-b593-b290fedd7abb", x: 4224, y: 192} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "Volvamos a la pregunta. Imagina que el novio de una amiga tuya le pidió que le envíe una foto íntima de ella como prueba de amor.

Ella se la envió pero, ahora, la foto anda circulando por todo el salón.

*¿Que harían en tu grupo de amigas si le llega a pasar esto a una de ustedes?* 🤔"
    )

  then(Branch_266808)
end

```

<!-- { section: "d6566de1-ae49-4816-9d5d-e5f7080e134d", x: 5568, y: 168} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "TEXT_MESSAGE" do
  text("¡Gracias por contarnos! Ahora, escuchemos que harían Pilar y Mari en esta situación")
  then(Message_11_1)
end

```

<!-- { section: "487481bf-0e91-49b6-8087-418a08aae417", x: 6336, y: 168} -->

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

<!-- { section: "63525c30-ff85-4fda-a22d-c3575a9834dc", x: 6120, y: -912} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11)
end

```

<!-- { section: "043aabca-00f4-46be-a619-4295ebcd5e3a", x: 6792, y: 72} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Sigue el podcast 🎧"]) do
      text(
        "Para que las tengas presentes, te vuelvo a dejar los *5 pasos* que te recomendaron Mari y Pilar:

*1)* Piensa en cómo te sientes y busca apoyo 🔍
*2)* Guarda pruebas y habla con un adulto o experto para obtener ayuda 📄
*3)* Revisa si la red social en que circula la foto tiene un canal para apoyarte a bajar la foto  📸
*4)* Ajusta la privacidad de tus pefiles en redes sociales  👩🏻‍💻
*5)* Puedes reportar el incidente si quieres, ya que compartir tu foto es ilegal 🚫

Si pasamos por situaciones como estas, es importante saber que no estamos solas y que hay maneras de solucionar esto 🫶"
      )
    end

  then(Message_13_1 when ref_Message_12 == "Sigue el podcast 🎧")
  then(Catch_all_6)
end

```

<!-- { section: "262b203f-9141-453b-8628-6bdd9cde23f0", x: 6816, y: -792} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "c5fc70d1-8afe-47a2-b4c8-64fabd6ad132", x: 7632, y: 144} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_14 when ref_Message_13 == "Ya escuché el audio")
  then(Catch_all_7)
end

```

<!-- { section: "dc5e5cf1-5eea-4b42-9746-4d48e5a32c2e", x: 7392, y: -792} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13)
end

```

<!-- { section: "4d6fb6d7-1689-490e-a1d9-cfa595b755c9", x: 8064, y: 192} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Me voy👋", "No sé qué haría🤷‍♀️", "Trato de soportar 🤔"]) do
      text(
        "Imagínate que una de tus amigas y su pareja se fueron a una fiesta. Todo estaba bien hasta que ella se dio cuenta que su novio estaba consumiendo drogas con unos amigos. 

Ella se siente incómoda y no quiere seguir en la fiesta. Pero también siente que todos estan muy raros y le da miedo que la lleven a su casa😰 Su novio le dice que si se va, no lo llame más.

*Si fuera tu caso, ¿que harías?*🤔"
      )
    end

  then(Message14_1 when ref_Message_14 == "Me voy👋")
  then(Message14_2 when ref_Message_14 == "No sé qué haría🤷‍♀️")
  then(Message14_3 when ref_Message_14 == "Trato de soportar 🤔")
  then(Catch_all_8)
end

```

<!-- { section: "e0013919-ca90-4c03-8911-9ca146b5ed00", x: 8088, y: -720} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "1fe73950-b2d0-41cf-b09b-708b443d9963", x: 9744, y: 24} -->

```stack
card Message_15_1, "Message_15_1",
  version: "1",
  uuid: "a8652dd1-cfc0-5448-aa2b-55632cd871b6",
  code_generator: "MEDIA_AUDIO" do
  audio("1647053e-85c8-49f6-881f-1d6f1436f8b4-G_M6_P3_R1.mp3")
  then(Message_15_4)
end

```

<!-- { section: "048367af-7486-4f7d-afaa-97cd1cedb764", x: 9696, y: 720} -->

```stack
card Message_15_2, "Message_15_2",
  version: "1",
  uuid: "e9ad095a-9559-5705-8bf6-1447e3afc74d",
  code_generator: "MEDIA_AUDIO" do
  audio("25ee9d6f-94ed-4812-bb9c-27936aee258f-G_M6_P3_R2.mp3")
  then(Message_15_4)
end

```

<!-- { section: "7df200fb-595d-4b32-ac44-76c8c820ba57", x: 9696, y: 1488} -->

```stack
card Message_15_3, "Message_15_3",
  version: "1",
  uuid: "aa68a0f1-b4b8-5185-93d0-f7be5fe5b3d3",
  code_generator: "MEDIA_AUDIO" do
  audio("309e82c7-65c5-4f8d-acae-24bed6e5fccd-G_M6_P3_R3.mp3")
  then(Message_15_4)
end

```

<!-- { section: "db23d7ae-f635-4df2-9124-faf6155fdfd5", x: 10488, y: 288} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15_4)
end

```

<!-- { section: "e1dafc25-305a-48c5-86b6-dcf63c823349", x: 10416, y: 816} -->

```stack
card Message_15_4, "Message_15_4",
  version: "1",
  uuid: "002b44dd-ff8e-57e8-ae14-fff5229aaf7a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_4 =
    buttons(["Siguiente pregunta ❓"]) do
      text("Cuando finalice el audio, presione el botón de siguiente pregunta.")
    end

  then(Message_16 when ref_Message_15_4 == "Siguiente pregunta ❓")
  then(Catch_all_10)
end

```

<!-- { section: "1bb02b9c-0bcb-47e1-8751-64643059da8d", x: 11136, y: 816} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["¡Genial! 💸", "Tiene sus riesgos ⚠️", "¡Jamás! ❌"]) do
      text(
        "Ahora imagina que estás con tus amigas y una les cuenta que su novio le ha propuesto que ambos envíen fotos íntimas para OnlyFans. ¡Ella les dice que el pago es MUY bueno! ¿Qué crees que pensarían *tus amigas* al respecto?"
      )
    end

  then(Message16_1 when ref_Message_16 == "¡Genial! 💸")
  then(Message16_2 when ref_Message_16 == "Tiene sus riesgos ⚠️")
  then(Message16_3 when ref_Message_16 == "¡Jamás! ❌")
  then(Catch_all_12)
end

```

<!-- { section: "48ecac59-09a9-4e78-ba51-219d2bf6169d", x: 11352, y: 72} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16)
end

```

<!-- { section: "1e84c612-ad87-4704-a920-40bc3ad8a0e9", x: 13008, y: 312} -->

```stack
card Message_17_1, "Message_17_1",
  version: "1",
  uuid: "5277b1d8-b73e-5457-b6fc-a3e93bef9c08",
  code_generator: "MEDIA_AUDIO" do
  audio("7c0544e7-42c7-4ea6-88ab-a5cd046527b5-G_M6_P3_R4.mp3")
  then(Message_18)
end

```

<!-- { section: "0d823549-f063-4ada-bfe5-371627ba30ae", x: 13008, y: 840} -->

```stack
card Message_17_2, "Message_17_2",
  version: "1",
  uuid: "983efb4d-903a-5096-8c7a-e5384646d97a",
  code_generator: "MEDIA_AUDIO" do
  audio("41a8e1ff-bdec-49b6-9d33-964c021b5d01-G_M6_P3_R5.mp3")
  then(Message_18)
end

```

<!-- { section: "d3bd1a63-3db7-44af-9f37-a91bb522dd90", x: 12984, y: 1368} -->

```stack
card Message_17_3, "Message_17_3",
  version: "1",
  uuid: "ec2f9663-7fe1-516c-b8cd-1d916cb61c04",
  code_generator: "MEDIA_AUDIO" do
  audio("eaf3f2c0-e39f-4356-bb59-fe2dbf6fec5e-G_M6_P3_R6.mp3")
  then(Message_18)
end

```

<!-- { section: "9022051d-fa83-4d75-8326-ba22989eccbd", x: 13968, y: 840} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Fotos íntimas📸🔞", "Celos excesivos😠👁️", "Responder rápido⚡📱"]) do
      text(
        "Es buen hábito tener un Plan B para toda situación. Piensa en un plan que podrías hacer si tu pareja u otra persona te pide algo que tú no quieres hacer ¿En qué te quieres enfocar?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Fotos íntimas📸🔞")
  then(Message18_2 when ref_Message_18 == "Celos excesivos😠👁️")
  then(Message18_3 when ref_Message_18 == "Responder rápido⚡📱")
  then(Catch_all_13)
end

```

<!-- { section: "e7e38417-b6bc-4256-8381-26ba7684fbfc", x: 13968, y: -168} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18)
end

```

<!-- { section: "b579957e-2c6e-4ddd-b02b-55e63dd4acc5", x: 15144, y: 912} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "QUESTION" do
  ref_Message_19 =
    ask(
      "Antes de irnos, ¡Es hora de pensar en tu plan! Si estás en una situación incómoda, ¿sabes que plan B puedes activar para llegar a casa a salvo? Piensa en todo lo que necesitas tener para llamar a alguien o encontrar tu camino...📋 Puedes responder *en texto o nota de voz*"
    )

  then(Branch_ba5547)
end

```

<!-- { section: "5dac3fa3-8ddc-4a79-822c-0e2410c0783d", x: 16944, y: 936} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_21 when ref_Message_20 == "Ya escuché el audio")
  then(Catch_all_14)
end

```

<!-- { section: "60d82f45-6031-4cb5-8560-d2003a2c919b", x: 16440, y: 72} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "29fd27f6-47f0-5aec-8054-b4d312e8fcca",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_20)
end

```

<!-- { section: "198c2a92-525a-4e94-89b2-82cdb025b769", x: 17544, y: 960} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_21 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Completaste el episodio 6 de nuestro podcast! 🥳 Hoy tengo más stickers para que los puedas usar y te ayuden si algún día te enfrentas a una situación como esta."
      )
    end

  then(Message_22_sticker_1 when ref_Message_21 == "¡Manda mis stickers!")
  then(Catch_all_15)
end

```

<!-- { section: "f65519eb-2263-4a8e-8242-70f334d009c7", x: 17544, y: 48} -->

```stack
card Catch_all_15, "Catch_all_15",
  version: "1",
  uuid: "4bee0862-bdcd-5844-8df1-4816d420e326",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_21)
end

```

<!-- { section: "ad1c6e6d-eaa1-470d-aab5-6bc20f1d4e56", x: 18360, y: 312} -->

```stack
card Message_22_sticker_1, "Message_22_sticker_1",
  version: "1",
  uuid: "cf7a0513-124a-59f5-b530-a41a3e9be238",
  code_generator: "MEDIA_IMAGE" do
  image("1de3bacb-ea2d-477b-b578-4628646f0b33-Módulo6_Abrilosojos.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "19c47e49-fa94-4b3c-adab-a56afb8e0a22", x: 19152, y: 936} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["¡Entendido!  🫡"]) do
      text("¡Van 6 de 6 días de racha en el reto del podcast! Ya lo terminaste, ¡MUY BIEN! 🥳")
    end

  then(Mesage_24 when ref_Message_23 == "¡Entendido!  🫡")
  then(Catch_all_16)
end

```

<!-- { section: "103957c2-9c77-408d-909b-818a02af81a8", x: 19104, y: 216} -->

```stack
card Catch_all_16, "Catch_all_16",
  version: "1",
  uuid: "d4296a10-0d55-5756-9088-6b503693c13b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_23)
end

```

<!-- { section: "d2a221dd-9b81-4a1e-b496-21a8d8375625", x: 19824, y: 912} -->

```stack
card Mesage_24, "Mesage_24",
  version: "1",
  uuid: "b1a0c4ba-6886-5a82-a198-1ecedaf6182e",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Mesage_24 =
    buttons(["Meditación🧘‍♀️", "Hablar con alguien👥", "Escribir o respirar"]) do
      text(
        "Hoy es nuestro último día 😢. Pero no me puedo ir sin dejarte un reto que quiero que hagas todos los dias: *¡Cuidarte mucho a ti misma!* Quiero que pienses qué harás cuando no te sientas bien. ¿En qué te quieres enfocar?"
      )
    end

  then(Message24_1 when ref_Mesage_24 == "Meditación🧘‍♀️")
  then(Message24_2 when ref_Mesage_24 == "Hablar con alguien👥")
  then(Message24_3 when ref_Mesage_24 == "Escribir o respirar")
  then(Catch_all_17)
end

```

<!-- { section: "4ccf14c8-d546-4a16-8ef3-6d22a7b90278", x: 19848, y: 72} -->

```stack
card Catch_all_17, "Catch_all_17",
  version: "1",
  uuid: "209ee976-ac39-5434-95b8-eaa8c2de1f85",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Mesage_24)
end

```

<!-- { section: "44224ced-5a95-4bdb-9ec8-4a1c4dc8f332", x: 21024, y: 864} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Me parece genial, piensa en cuando y cómo puedes hacer esta actividad como parte de tu rutina diaria para que no se te olvide."
  )

  then(Safe_Guarding_1)
end

```

<!-- { section: "7f08d185-2353-4887-ac3d-12c3d9f7dbdb", x: 22344, y: 864} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["¡Chao LiA! 🌸"]) do
      text(
        "Ok amiga, ¡me gustó mucho conocerte y haber interactuado contigo todos estos días! Espero que te haya servido mucho todo lo que aprendiste y que no olvides lo poderosa que eres💪"
      )
    end

  then(Message_27 when ref_Message_26 == "¡Chao LiA! 🌸")
  then(Catch_all_18)
end

```

<!-- { section: "87e4ee97-48df-4bf1-ba86-cfeb0af4fd70", x: 22992, y: 960} -->

```stack
card Message_27, "Message_27",
  version: "1",
  uuid: "58095b08-ea56-5e0f-9bba-0cdfec59e6c4",
  code_generator: "TEXT_MESSAGE" do
  text("¡Chao, amiga!  👋🌟")
  then(Profile_cbf172)
end

```

<!-- { section: "f40cc272-d181-4b1d-aec4-a97226f80492", x: 22032, y: 72} -->

```stack
card Catch_all_18, "Catch_all_18",
  version: "1",
  uuid: "e1b87782-5fd0-51c8-b25e-fa1a45e4e585",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_26)
end

```

<!-- { section: "8c1c5260-4b46-4125-a030-531c2fba4298", x: 23424, y: 936} -->

```stack
card Profile_cbf172, "Profile_cbf172",
  version: "1",
  uuid: "1acd4948-bace-5c4c-8e4e-0398e15c8bd5",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_6")
  then(ModuleCompleted)
end

```

<!-- { section: "9bd65e93-dfba-4a4a-ae4b-10db16a0abe8", x: 5952, y: 168} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "MEDIA_AUDIO" do
  audio("d047847a-127a-41e6-a81c-d52488996fce-G_M6_P2.mp3")
  then(Message_11)
end

```

<!-- { section: "4596b1b1-967a-41a1-a095-ece7ac32d5f6", x: 7200, y: 144} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "MEDIA_AUDIO" do
  audio("d0155c48-bc14-49a3-ab46-b9bd2ddffa7d-G_M6_P3.mp3")
  then(Message_13)
end

```

<!-- { section: "3f7c3001-cd0b-47ac-8e3f-4f4f903e3bfe", x: 16512, y: 1008} -->

```stack
card Message_20_1, "Message_20_1",
  version: "1",
  uuid: "3c0640c4-ff8d-5995-9bf2-1f14c9dd3e9a",
  code_generator: "MEDIA_AUDIO" do
  audio("f69fba19-ef2b-47e6-9604-b490ed9ecae4-G_M6_P4.mp3")
  then(Message_20)
end

```

<!-- { section: "ff8e5640-5186-4c52-a7c7-0f20d21db7e5", x: 18312, y: 792} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("0ed6bc20-4ebe-4e96-b1f8-8e1b202f2561-Módulo6_Auxilio.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "444ee784-837e-49d6-a374-6a05368c87c8", x: 18288, y: 1296} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("36e387d9-28dc-494c-879f-ebbb47307a66-Modulo6_Fortalesa-Copy.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "693075e9-63a7-487c-acbd-110efa41e663", x: 18288, y: 1800} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("e53af77b-67a0-470e-a0ed-e9a6187df769-Modulo6_Noestassola-Copy.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "437d7e2f-6716-4fc1-9b69-a0a198652396", x: 18768, y: 1728} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("a654a995-9ad5-444a-b609-540080fd21cc-Modulo6_Selfcare-Copy.webp")
  text("")
  then(Message_23)
end

```

<!-- { section: "8b35fc33-3c38-4e68-b13b-9cd6ceb667ea", x: 15576, y: 936} -->

```stack
card Branch_ba5547, "Branch_ba5547",
  version: "1",
  uuid: "469ed1a4-4b66-55b4-8664-7d816c4a4d94",
  code_generator: "CONDITIONALS" do
  then(Message19 when event.message.type == "audio")
  then(Message19 when event.message.type == "text")
  then(Text_5ff7ca)
end

```

<!-- { section: "80eddb5d-a57e-4b20-8f36-f59979b26399", x: 15408, y: 1416} -->

```stack
card Text_5ff7ca, "Text_5ff7ca",
  version: "1",
  uuid: "86eec7f7-0ef4-56bd-b4db-79296a4a20b7",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_19)
end

```

<!-- { section: "319cf96c-7c60-489d-9586-671414880f1d", x: 21456, y: 864} -->

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

<!-- { section: "73a529d3-5b60-410b-ad2d-5d27409b82a9", x: 21888, y: 864} -->

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

<!-- { section: "636393bc-5cc1-4a56-9fe4-23d331f9c3f0", x: 4632, y: 192} -->

```stack
card Branch_266808, "Branch_266808",
  version: "1",
  uuid: "c9669b4e-f247-5b04-9f9c-6cc8f8b7a64c",
  code_generator: "CONDITIONALS" do
  then(Message9 when event.message.type == "audio")
  then(Message9 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "fd4f08fc-8424-436c-8a7a-cd389633f216", x: 4440, y: 792} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_9)
end

```

<!-- { section: "067e913e-4f61-47d0-b14a-d747d6d787f8", x: 22776, y: 1272} -->

We cannot have audio as button messages, will need extra copy here

if we switch message 7 & 8 we can solve the problem

We cannot have audio as button messages, will need extra copy here

emoji does not show up

We cannot have audio as button messages, will need extra copy here

We cannot have audio as button messages, will need extra copy here

**@Buhle**

Please save insights here

We cannot have audio as button messages, will need extra copy here

emoji does not show up

**@Buhle**

Please add in the other thingies here ^

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module6_started (yes)

**@Buhle**

Please save the insights here

**@Buhle**

Please save this for DS, I added a code block just in case that would be easier
**DS note:** Flow result: module6_beliefs {user input}

**@Buhle**

Please save insights here

**@Buhle**

Please save insights here

**@Buhle**

Please save the user response here, its a DS thing so I added a code block below for you incase that is what you need.

**DS note:** Flow result: module6_action_planning {user input}

**@buhle**

Send stickers named Module 6 here, I have popped the code here and put a message block in its place for now.

Once you have added the stickers/gotten that sorted we can use the code block here

**@buhle**

Please save insights here

update contact field, contact module = module 6 ✅

**@Buhle**

DS note: Flow result: module6_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "06ee4729-d011-4850-90a1-a616cb448bf0", x: -240, y: -48} -->

```stack
card Message1 do
  write_result("module6_started", "yes")
  then(Message_2)
end

```

<!-- { section: "c78b6986-9f33-43cd-9c65-ea1a8618b58d", x: 5112, y: 120} -->

```stack
card Message9 do
  write_result("module6_beliefs", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "4dbcbde4-de0a-4b38-9bc8-6a46b45d2a69", x: 16056, y: 912} -->

```stack
card Message19 do
  write_result("module6_action_planning", "@ref_message_19")
  then(Message_20_1)
end

```

<!-- { section: "50e2a973-59d5-4a6a-b75c-82bd8ea99901", x: 23856, y: 912} -->

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

<!-- { section: "16188c65-ba1c-4285-85fd-6ec15c9f80f8", x: 936, y: -216} -->

```stack
card Message2_1 do
  write_result("module6_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "3ad86802-b442-4774-8962-eca26f97bc76", x: 936, y: 240} -->

```stack
card Message2_2 do
  write_result("module6_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "085de736-fc8e-45fd-be7a-989eb74fcfcb", x: 8832, y: -72} -->

```stack
card Message14_1 do
  write_result("module6_attitudes", "a")
  then(Message_15_1)
end

```

<!-- { section: "2754c315-a147-4c59-a412-7d52a5b75d6c", x: 8832, y: 408} -->

```stack
card Message14_2 do
  write_result("module6_attitudes", "b")
  then(Message_15_2)
end

```

<!-- { section: "0f9959b7-db10-4370-a9b0-d40cf3f9cf59", x: 8856, y: 840} -->

```stack
card Message14_3 do
  write_result("module6_attitudes", "c")
  then(Message_15_3)
end

```

<!-- { section: "906f9eec-0999-4444-a9c4-002299f07bd1", x: 12024, y: 432} -->

```stack
card Message16_1 do
  write_result("module6_social_norms", "a")
  then(Message_17_1)
end

```

<!-- { section: "6e97d925-08f2-4091-b1a3-23dad37dcc87", x: 12072, y: 840} -->

```stack
card Message16_2 do
  write_result("module6_social_norms", "b")
  then(Message_17_2)
end

```

<!-- { section: "cfa41635-b5fe-4e1c-a160-0b05218adee3", x: 12072, y: 1248} -->

```stack
card Message16_3 do
  write_result("module6_social_norms", "c")
  then(Message_17_3)
end

```

<!-- { section: "8a975b69-292c-489c-93a1-08138f2c306c", x: 14616, y: 432} -->

```stack
card Message18_1 do
  write_result("module6_behavioral_activation", "a")
  then(Message_19)
end

```

<!-- { section: "fb25dafc-72ad-4d00-bf73-18b11d0c5600", x: 14640, y: 888} -->

```stack
card Message18_2 do
  write_result("module6_behavioral_activation", "b")
  then(Message_19)
end

```

<!-- { section: "d31d8dc4-5225-4bd1-a47b-6552edf81418", x: 14616, y: 1248} -->

```stack
card Message18_3 do
  write_result("module6_behavioral_activation", "c")
  then(Message_19)
end

```

<!-- { section: "9b206af6-196a-4c80-ac1e-f1905ddb6c54", x: 20352, y: 720} -->

```stack
card Message24_1 do
  write_result("module6_behavioral_activation2", "a")
  then(Message_25)
end

```

<!-- { section: "ebff418d-afdc-4589-abc8-fbf6d0f89131", x: 20424, y: 1056} -->

```stack
card Message24_2 do
  write_result("module6_behavioral_activation2", "b")
  then(Message_25)
end

```

<!-- { section: "781533f3-00a9-4ef5-94d7-1031cfd94e1f", x: 20424, y: 1416} -->

```stack
card Message24_3 do
  write_result("module6_behavioral_activation2", "c")
  then(Message_25)
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
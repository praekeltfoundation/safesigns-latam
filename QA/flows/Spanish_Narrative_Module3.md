<!-- { section: "5eb7a64c-ffd3-4992-bc02-c0d5afba708d", x: -1608, y: -48} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_n3")

trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_2" and contact.onboarding_complete == true and
       contact.arm == "NARRATIVE"

```

<!-- { section: "", x: -1108, y: -48} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "89659706-c5c0-4322-9e85-b17b65f83f7f",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_narrative_mod3", "es", [], buttons: ["¡Cuéntame más!"])

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_25)
end

```

<!-- { section: "e658c981-0436-4779-9a02-3bc23d6fe3f4", x: 456, y: 24} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "Buenísimo 👍"]) do
      text(
        "El reto de ayer era aplicar una estrategia para sentirte mejor en algún momento del día 🧘🎵 ✍️ ¿Cómo te fue?"
      )
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "Buenísimo 👍")
  then(Catch_all_1)
end

```

<!-- { section: "5de6ce9e-772c-432c-bb3c-62205495c528", x: 384, y: -864} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "8073b52c-3823-421e-a887-368db8e0e2ae", x: 1512, y: -192} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text("No te preocupes, ¡Hoy podrás ponerte al día!")
  then(Message_4)
end

```

<!-- { section: "5f943557-0cb1-44a9-8d23-8376b5b2fcc6", x: 1512, y: 312} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text("Increíble, ¡Apuesto que se va a notar en tus respuestas de hoy!")
  then(Message_4)
end

```

<!-- { section: "b5fbdacd-3275-4427-bf1c-662130974d7c", x: 1944, y: 96} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¿Crees que en este tercer episodio descubriremos si finalmente Pilar ya apareció? 😲 ¡Ya lo veremos!"
  )

  then(Message_5)
end

```

<!-- { section: "ec54fe37-21b2-4e1b-8f4c-52c7ff85e134", x: 2304, y: -696} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
end

```

<!-- { section: "b642436b-7381-4d66-8f4d-864cddc8df77", x: 2328, y: 96} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Recuerda que si hay algo de la historia de Pilar o alguna pregunta te hace sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!"
  )

  then(Messge_6)
end

```

<!-- { section: "f3811d37-218d-405e-ba5d-a858d7ae6948", x: 2736, y: 96} -->

```stack
card Messge_6, "Messge_6",
  version: "1",
  uuid: "e7629ef9-bb28-53c5-870d-24bf828ea340",
  code_generator: "QUESTION" do
  ref_Messge_6 =
    ask(
      "Antes de escuchar el tercer episodio, quisiera saber algo. Tener a alguien en quien confiar es increíble. ¿Qué características crees debe tener alguien para que lo consideres como un(a) buen(a) amigo(a)? Escribe o manda por nota de voz al menos *dos* características"
    )

  then(Branch_d63adb)
end

```

<!-- { section: "dd4129da-0ce3-4752-bd40-ba9f142964c6", x: 4752, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_8_1)
end

```

<!-- { section: "b89954f7-c600-4e61-86ac-a1a031f17ae3", x: 3936, y: 96} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "TEXT_MESSAGE" do
  text("¡Gracias por tu respuesta! Ahora sí, escuchemos el audio.")
  then(Message_8)
end

```

<!-- { section: "5cad06c5-bc41-436e-b9a2-208389172960", x: 4320, y: 96} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "MEDIA_AUDIO" do
  audio("9a23ce90-fc83-447d-a181-1230bc00cb03-M3_P1_A1.mp3")
  then(Message_8_1)
end

```

<!-- { section: "e34945d5-ca52-4425-b6b3-425fdc2ea048", x: 5184, y: 96} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["No ayudan en nada ❌", "Tienen algo de razón", "Son muy duros 😕"]) do
      text(
        "En el episodio escuchamos cómo \"la amiga\" reacciona cuando Pilar le cuenta todo lo que pasó. Ella le dice frases como: \"Cuántas veces te dije que él no era para ti... Yo te lo advertí… Mira cómo estás llorando, eso te pasa por boba.\"
¿Qué piensas de este tipo de comentarios?"
      )
    end

  then(Message9_1 when ref_Message_9 == "No ayudan en nada ❌")
  then(Message9_2 when ref_Message_9 == "Tienen algo de razón")
  then(Message9_3 when ref_Message_9 == "Son muy duros 😕")
  then(Catch_all_4)
end

```

<!-- { section: "b7c3737a-88df-4f02-9f55-2ed8a2d63f87", x: 6408, y: -408} -->

```stack
card Message_10_1, "Message_10_1",
  version: "1",
  uuid: "58278096-b795-5536-b01b-0189dc2a87c9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_1 =
    buttons(["Siguiente audio"]) do
      text(
        "Tienes razón, esos comentarios no ayudan. En lugar de señalarle lo que hizo mal, su amiga podría decirle frases como: \"Entiendo que te sientes mal, estoy aquí para ti. ¿Cómo te puedo ayudar? No estás sola, podemos encontrar una solución juntas\". Mostrarle apoyo sin juzgarla es una mejor manera de brindar ayuda, pues hará que se sienta comprendida y con la confianza de hablar con su amiga."
      )
    end

  then(Message_11 when ref_Message_10_1 == "Siguiente audio")
  then(Catch_all_22)
end

```

<!-- { section: "c231bc3f-7b87-4026-bf1f-448d113673eb", x: 7056, y: 504} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "MEDIA_AUDIO" do
  audio("1b5c4b0a-5963-4133-b9a9-4841aefcbf4d-M3_P2_A1.mp3")
  then(Message_11_1)
end

```

<!-- { section: "47a179f5-0f5f-42b1-873c-64bddabb1214", x: 7488, y: 480} -->

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

<!-- { section: "e4ba43d4-22ac-4ba3-bdae-f7bd603095b8", x: 5304, y: -648} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_9)
end

```

<!-- { section: "e698e1fb-f07a-4a97-8889-1db86a52eca3", x: 7752, y: -648} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11_1)
end

```

<!-- { section: "f705cb5c-4875-42e7-8344-a96a234bbd22", x: 9504, y: 432} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por compartir qué piensas! Ahora te contaré una situación a la que se podría enfrentar Pilar en el futuro"
  )

  then(Message_14)
end

```

<!-- { section: "b258f194-197a-4484-bd75-5ed9025f963d", x: 8016, y: 456} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "QUESTION" do
  ref_Message_12 =
    ask(
      "La vecina ha comentado que a veces las niñas son muy exageradas y por cualquier problema chiquito se desaparecen.

¿Qué piensas de esto? ¿Crees que es cierto?"
    )

  then(Branch_15bdad)
end

```

<!-- { section: "f46ca44e-879f-4f3d-8dc4-9d290242a2f7", x: 11088, y: 1512} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15_3)
end

```

<!-- { section: "16a42563-ec26-4c78-9ade-b28db5192631", x: 11232, y: 432} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15_2)
end

```

<!-- { section: "a91d8e5c-8198-4c72-9b8e-7b49ddeb82a2", x: 9936, y: 432} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Busquemos ayuda🗣️", "¿Qué? No te creo 😲", "Eso te pasa por boba"]) do
      text(
        "Imagina que, un día, Pilar entra a su salón y ve a su amiga Mari que está llorando. Mari le cuenta en secreto que el novio la está chantajeando con que va a compartir fotos íntimas si ella le termina. 
Si Pilar es una buena amiga, ¿Cómo crees que reaccionaría?"
      )
    end

  then(Message14_1 when ref_Message_14 == "Busquemos ayuda🗣️")
  then(Message14_2 when ref_Message_14 == "¿Qué? No te creo 😲")
  then(Message14_3 when ref_Message_14 == "Eso te pasa por boba")
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

<!-- { section: "97965a8f-c76c-44d5-bba6-4269690129a5", x: 11424, y: -144} -->

```stack
card Message_15_1, "Message_15_1",
  version: "1",
  uuid: "a8652dd1-cfc0-5448-aa2b-55632cd871b6",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_1 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Ofrecer buscar ayuda es un gran primer paso. Asegúrate de buscar personas de confianza o profesionales que puedan ayudar. Puedes también acompañarla para encontrar recursos y mostrarle que estás ahí para apoyarla."
      )
    end

  then(Message_16 when ref_Message_15_1 == "Siguiente pregunta")
  then(Catch_all_10)
end

```

<!-- { section: "48f938ef-7f6b-4a53-ac95-e4b0b93bf2a1", x: 11400, y: -840} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15_1)
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

<!-- { section: "44010249-c410-488c-8e3c-756240354b81", x: 12168, y: 696} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["Las peleas 🥊", "El chisme 🗣️", "El apoyo 🤝"]) do
      text("En tu *grupo de amigas,* ¿qué es lo más común que se presente?")
    end

  then(Message16_1 when ref_Message_16 == "Las peleas 🥊")
  then(Message16_2 when ref_Message_16 == "El chisme 🗣️")
  then(Message16_3 when ref_Message_16 == "El apoyo 🤝")
  then(Catch_all_16)
end

```

<!-- { section: "da22c4c6-befe-40e5-9be0-07ca6d3ee558", x: 12168, y: -360} -->

```stack
card Catch_all_16, "Catch_all_16",
  version: "1",
  uuid: "d4296a10-0d55-5756-9088-6b503693c13b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16)
end

```

<!-- { section: "ecb52810-5930-4097-8564-3c63c04af5e4", x: 13488, y: 840} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Cada grupo de amigas tiene su propia dinámica, y es útil reflexionar sobre qué aspectos predominan. Si las peleas o el chisme son comunes, considera cómo podrían abordarse para mejorar la relación. Si el apoyo es lo más frecuente, ¡es un gran signo de un grupo fuerte y solidario!"
  )

  then(Message_18)
end

```

<!-- { section: "2fdd8deb-02fc-4d65-9344-41a61b1b80d0", x: 18672, y: -792} -->

```stack
card Catch_all_17, "Catch_all_17",
  version: "1",
  uuid: "209ee976-ac39-5434-95b8-eaa8c2de1f85",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "e95a720d-28d7-448c-bd98-3b5aad894f73", x: 13920, y: 768} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "¡Muy bien! Has escuchado el episodio 3 de la historia de Pilar 🥳

Son temas complejos, por ello para ayudarte a navegarlos, te dejo unos stickers buenísimos sobre este tema y que puedes usar para responder si llegas a vivir algo similar"
      )
    end

  then(Message_19_sticker_1 when ref_Message_18 == "¡Manda mis stickers!")
  then(Catch_all_18)
end

```

<!-- { section: "178128f3-e108-4907-a86d-b9f5cd5c2dca", x: 13872, y: -72} -->

```stack
card Catch_all_18, "Catch_all_18",
  version: "1",
  uuid: "e1b87782-5fd0-51c8-b25e-fa1a45e4e585",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18)
end

```

<!-- { section: "e832384b-19e6-4d59-83ce-01e34bcfba86", x: 14472, y: 960} -->

```stack
card Message_19_sticker_1, "Message_19_sticker_1",
  version: "1",
  uuid: "ee12c79b-555b-52c8-89c7-c462eaf62ab1",
  code_generator: "MEDIA_IMAGE" do
  image("f5481953-120d-4df4-8b53-cf40fe55dcea-Módulo3_Ayvv.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "3d0ee0f9-614d-434d-b40b-f446d9654962", x: 16512, y: 888} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "QUESTION" do
  ref_Message_20 =
    ask(
      "Hoy, escuchamos algunos tips que podemos usar para ayudar a alguien a sentirse mejor ¿Qué frases se te ocurren que podrías decirle a una amiga que está pasando por un mal momento?"
    )

  then(Branch_660543)
end

```

<!-- { section: "6f417ddc-25be-4107-8a05-54a505b17679", x: 18288, y: 888} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["Amigas 👯‍♀️", "Mamá o papá 👩‍👧", "Familiar 👩🧑"]) do
      text(
        "Ahora, te voy a dejar este reto: Para mañana, reflexiona acerca de quien sería para ti la persona que te pueda ofrecer un espacio seguro para contarle tus cosas y ayudarte. ¿Quién es esa persona para ti?"
      )
    end

  then(Message22_1 when ref_Message_22 == "Amigas 👯‍♀️")
  then(Message22_2 when ref_Message_22 == "Mamá o papá 👩‍👧")
  then(Message22_3 when ref_Message_22 == "Familiar 👩🧑")
  then(Catch_all_20)
end

```

<!-- { section: "b389cf49-bbcd-4aa2-abf8-d0aeee91e92c", x: 18288, y: 120} -->

```stack
card Catch_all_20, "Catch_all_20",
  version: "1",
  uuid: "33422d10-445d-5f76-96c9-e793d4011333",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_22)
end

```

<!-- { section: "a0d65991-a6a0-4793-a95d-4d8fa714442d", x: 20592, y: 1152} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["¡Quiero saberlo!🧐"]) do
      text(
        "Ok, amiga, esto fue todo por hoy. ¡Prepárate! Porque el episodio de mañana va a estar increíble! ¿Será que al fin descubriremos qué fue lo que le pasó a Pilar para desaparecer?"
      )
    end

  then(Message_24 when ref_Message_23 == "¡Quiero saberlo!🧐")
  then(Catch_all_21)
end

```

<!-- { section: "f3065b9c-b9ee-4b53-8685-149a0cc9297b", x: 21192, y: 1200} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(Profile_fa3d29)
end

```

<!-- { section: "72d8df6c-f043-4eef-b4f2-d153f18945a7", x: 20520, y: 336} -->

```stack
card Catch_all_21, "Catch_all_21",
  version: "1",
  uuid: "317ddc77-c862-5558-91a3-6d411d930f0a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_23)
end

```

<!-- { section: "35d600c3-48b9-445a-a35d-eb0135b2824f", x: 4704, y: 96} -->

```stack
card Message_8_1, "Message_8_1",
  version: "1",
  uuid: "4fa17f97-59bc-50b4-aaa7-bfc5081c1410",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8_1 =
    buttons(["Ya escuché el audio"]) do
      text("¿Lista? Cuando termine el audio, pulsa el botón *Ya escuché el audio!*")
    end

  then(Message_9 when ref_Message_8_1 == "Ya escuché el audio")
  then(Catch_all_3)
end

```

<!-- { section: "a8988fb3-e7fd-44c6-b97d-6d34ed353b24", x: 6384, y: 504} -->

```stack
card Message_10_2, "Message_10_2",
  version: "1",
  uuid: "865b0227-b4c1-57c3-bd90-9fbc7795d51a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_2 =
    buttons(["Siguiente audio"]) do
      text(
        "Es natural querer advertir a una amiga, pero en lugar de señalarle lo que hizo mal, podría decirle frases como: \"Entiendo que te sientes mal, estoy aquí para ti. ¿Cómo te puedo ayudar? No estás sola, podemos encontrar una solución juntas\". Mostrarle apoyo sin juzgarla es una mejor manera de brindar ayuda, pues hará que se sienta comprendida y con la confianza de hablar con su amiga."
      )
    end

  then(Message_11 when ref_Message_10_2 == "Siguiente audio")
  then(Catch_all_23)
end

```

<!-- { section: "fafa660b-6b5f-40c0-b836-e04f5ccf4114", x: 6336, y: 1344} -->

```stack
card Message_10_3, "Message_10_3",
  version: "1",
  uuid: "0bd10111-e7b6-5dc6-b7ee-9ba7fb06a788",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_3 =
    buttons(["Siguiente audio"]) do
      text(
        "Exacto, esos comentarios pueden ser muy duros. En lugar de señalarle lo que hizo mal, su amiga podría decirle frases como: \"Entiendo que te sientes mal, estoy aquí para ti. ¿Cómo te puedo ayudar? No estás sola, podemos encontrar una solución juntas\". Mostrarle apoyo sin juzgarla es una mejor manera de brindar ayuda, pues hará que se sienta comprendida y con la confianza de hablar con su amiga."
      )
    end

  then(Message_11 when ref_Message_10_3 == "Siguiente audio")
  then(Catch_all_24)
end

```

<!-- { section: "9dfe668e-930a-4209-8735-69134a94f0f1", x: 6384, y: -1056} -->

```stack
card Catch_all_22, "Catch_all_22",
  version: "1",
  uuid: "d726a2f0-f36b-5c79-a2fc-f33706cb5037",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10_1)
end

```

<!-- { section: "20d47de8-bea5-42f1-b7a4-a9ef16b4f75b", x: 6456, y: 192} -->

```stack
card Catch_all_23, "Catch_all_23",
  version: "1",
  uuid: "83142d06-58d1-5ed3-a212-b36817b976a4",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10_2)
end

```

<!-- { section: "fb813787-a453-4535-bb2d-028945680ed8", x: 6336, y: 1104} -->

```stack
card Catch_all_24, "Catch_all_24",
  version: "1",
  uuid: "6ebc3da7-1ca1-505a-8e92-68d3144096bc",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10_3)
end

```

<!-- { section: "f845c745-cf1a-4b84-a715-9a1fd6900de9", x: 11088, y: 744} -->

```stack
card Message_15_2, "Message_15_2",
  version: "1",
  uuid: "e9ad095a-9559-5705-8bf6-1447e3afc74d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_2 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Algunas frases comunes como \"¡No te creo!\" pueden hacer que la persona se sienta cuestionada. Es importante tomar en serio las emociones y experiencias de tu amiga. Considera apoyarla en la búsqueda de ayuda profesional y ser un oído atento para que se sienta respaldada."
      )
    end

  then(Message_16 when ref_Message_15_2 == "Siguiente pregunta")
  then(Catch_all_8)
end

```

<!-- { section: "239f23b8-319b-4128-b89e-5865e8c92a81", x: 11064, y: 1920} -->

```stack
card Message_15_3, "Message_15_3",
  version: "1",
  uuid: "aa68a0f1-b4b8-5185-93d0-f7be5fe5b3d3",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_3 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Es importante evitar comentarios que puedan hacer sentir aun peor a tu amiga. En su lugar, ofrécele apoyo y guía para buscar ayuda profesional. La empatía y la comprensión son clave para ayudar en situaciones difíciles."
      )
    end

  then(Message_16 when ref_Message_15_3 == "Siguiente pregunta")
  then(Catch_all_6)
end

```

<!-- { section: "f3381921-d160-49c4-bee7-ac4040a66484", x: 17808, y: 888} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "TEXT_MESSAGE" do
  text("¡Que bueno que ya estás pensando en cómo apoyar mejor a una amiga!")
  then(Message_22)
end

```

<!-- { section: "11912ba0-e8fd-49a0-9ad1-7f6e6662de49", x: 21648, y: 1176} -->

```stack
card Profile_fa3d29, "Profile_fa3d29",
  version: "1",
  uuid: "de644b0d-1436-5890-b5e2-93a199e09d02",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_3")
  then(ModuleCompleted)
end

```

<!-- { section: "c1adc74e-d308-45ee-bab2-7beb8bc6a596", x: 14856, y: 456} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("d59dcc18-f3af-449e-b141-1f94ad9b72c9-Módulo3_Hablemos.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "82a852f0-87bd-4f4d-8d62-e480f841ff20", x: 15264, y: 960} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("3d2599e7-7895-4a97-ac5e-d578a8edc4f8-Módulo3_LasChicas.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "9ae53d64-68b7-409e-9fca-ee6a4ba8b7be", x: 15624, y: 360} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("57375f26-adf2-4ea4-8c7c-166708cd9845-Módulo3_Rapido.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "f3e9dea0-a4fd-4883-8498-f5e4acd1539b", x: 15984, y: 960} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("042a9481-d412-40ee-9a7a-3b5d7f973bc3-Modulo3_Siempre-Copy.webp")
  text("")
  then(Message_20)
end

```

<!-- { section: "5a003645-e120-425f-b5f2-ee63fdbad246", x: 3120, y: 96} -->

```stack
card Branch_d63adb, "Branch_d63adb",
  version: "1",
  uuid: "8d6bb38c-4e30-5062-b58b-5766be051f92",
  code_generator: "CONDITIONALS" do
  then(Message6 when event.message.type == "audio")
  then(Message6 when event.message.type == "text")
  then(Text_daa618)
end

```

<!-- { section: "124400ee-b74a-4875-8c6a-89a224d39aef", x: 2976, y: 648} -->

```stack
card Text_daa618, "Text_daa618",
  version: "1",
  uuid: "fa9d3512-c540-5e27-a876-3f0d06949e61",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Messge_6)
end

```

<!-- { section: "6dac2867-6dc9-4322-8fb7-62fe029b0468", x: 19584, y: 1176} -->

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

<!-- { section: "1c753bea-b781-4c49-ad3a-b7992da0bf74", x: 20064, y: 1176} -->

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

  then(Message_23)
end

```

<!-- { section: "33c3a3c3-e1c4-4147-937e-f366a79501e0", x: 8496, y: 456} -->

```stack
card Branch_15bdad, "Branch_15bdad",
  version: "1",
  uuid: "74a1cc44-08aa-5e3d-9fa2-a8201a2ec5b5",
  code_generator: "CONDITIONALS" do
  then(Message12 when event.message.type == "audio")
  then(Message12 when event.message.type == "text")
  then(Catch_all_2_2)
end

```

<!-- { section: "f7fe9ca1-c20c-496d-a291-7200672f7962", x: 8136, y: 1056} -->

```stack
card Catch_all_2_2, "Catch_all_2_2",
  version: "1",
  uuid: "86031531-4763-5dde-ab3c-b02fc964194a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_12)
end

```

<!-- { section: "c9ba98ae-5fa2-4a14-98dc-dffa93f66eef", x: 16920, y: 888} -->

```stack
card Branch_660543, "Branch_660543",
  version: "1",
  uuid: "cb943d44-db98-549c-99b8-4a9a7353ccf4",
  code_generator: "CONDITIONALS" do
  then(Message20 when event.message.type == "audio")
  then(Message20 when event.message.type == "text")
  then(Catch_all_2_3)
end

```

<!-- { section: "13b79ace-2767-4042-b938-86b2cd495f34", x: 16416, y: 1392} -->

```stack
card Catch_all_2_3, "Catch_all_2_3",
  version: "1",
  uuid: "0b841c95-e1de-581e-a397-ec7143038543",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_20)
end

```

<!-- { section: "28478ad3-644a-4094-a4b0-a32cbc75db70", x: -624, y: -264} -->

```stack
card Catch_all_25, "Catch_all_25",
  version: "1",
  uuid: "f8b554d0-0a0c-4ad2-bb1b-6e32e8e07561",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "7565dad1-ac40-4ceb-87db-365444511924", x: 10032, y: 1032} -->

**@Buhle**

save variable/insights here

<!-- { section: "4f4424f8-616b-4efd-8f13-64ab50e52714", x: 1104, y: 600} -->

**@Buhle**

Please save the variable here

<!-- { section: "e54056f6-e64f-4ab6-aa99-78c62096f52b", x: 3552, y: 504} -->

**@Buhle**

save users response here

<!-- { section: "624d7309-09ce-4244-9cf1-97c3ea910c61", x: 5280, y: 720} -->

**@Buhle**

save insight here

<!-- { section: "6c5de93e-77da-491f-b38d-d3959b8e9ad0", x: 9024, y: 816} -->

**@Buhle**

Save users response here

<!-- { section: "bb495e5b-3b89-4513-8af0-4ca0286bf787", x: 12432, y: 1200} -->

**@Buhle**

please save insights here

<!-- { section: "af274619-69b1-47ad-961d-3167a26a6562", x: 17424, y: 1248} -->

**@Buhle**

Please save user response here,

DS note: Flow result: module3_social_support2 {user input}

<!-- { section: "2adb0f35-f635-40d8-b675-d97a2e1e2b78", x: 72, y: 408} -->

**@buhle**

Please save the DS note here,

DS note: Flow result: module3_started (yes)

<!-- { section: "29e0c747-2c91-42b8-84d8-b17bade02eb2", x: 21336, y: 1536} -->

Update contact field, contact module = Module 3✅

<!-- { section: "d99575b0-3185-499d-bad3-e814610f1b45", x: 21336, y: 1704} -->

**@Buhle**

DS note: Flow result: module3_completed (yes)
I added in a code block for you above, please dlt the one you arent using

<!-- { section: "1de1ca29-291b-48df-88f6-67c91acd073c", x: 21984, y: 1584} -->

**@Buhle**

Schedule Quiz Post Module 3 to start next day (6pm , Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "5490266f-2f05-4ae2-b9dd-e06be9bbd464", x: 18720, y: 1704} -->

**@Buhle**

Please save insights here

<!-- { section: "d84ed524-3f4b-426d-b25c-4d067d3c6cca", x: 17328, y: 816} -->

```stack
card Message20 do
  write_result("module3_social_support2", "@ref_message_20")
  then(Message_21)
end

```

<!-- { section: "43b3574e-b537-40ff-96fd-2a5805790fa1", x: -96, y: 0} -->

```stack
card Message1 do
  write_result("module3_started", "yes")
  then(Message_2)
end

```

<!-- { section: "474a23b7-67a3-47d0-8a2a-d1da593c8c88", x: 22104, y: 1128} -->

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

<!-- { section: "323f3a9f-bd97-4d67-845a-00809b755d84", x: 1008, y: -384} -->

```stack
card Message2_1 do
  write_result("module3_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "76f6b741-3e9f-41d5-abad-c74aaba3cdb1", x: 984, y: 264} -->

```stack
card Message2_2 do
  write_result("module3_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "645e6784-da3f-4d86-a4ae-52d4fc757ce2", x: 3480, y: 24} -->

```stack
card Message6 do
  write_result("module3_social_support", "b")
  then(Message_7)
end

```

<!-- { section: "a06397a1-6f0e-42ab-86c6-ad4befe6f3fb", x: 5760, y: -360} -->

```stack
card Message9_1 do
  write_result("module3_beliefs", "a")
  then(Message_10_1)
end

```

<!-- { section: "e39936d1-b2e1-47e4-804b-e0903a0dd869", x: 5856, y: 144} -->

```stack
card Message9_2 do
  write_result("module3_beliefs", "b")
  then(Message_10_2)
end

```

<!-- { section: "978b823c-025b-473d-8f9f-6f17496a59e3", x: 5808, y: 744} -->

```stack
card Message9_3 do
  write_result("module3_beliefs", "c")
  then(Message_10_3)
end

```

<!-- { section: "b19721a6-6564-48e5-ac90-a745f746f620", x: 9024, y: 408} -->

```stack
card Message12 do
  write_result("module3_gender_attitudes", "@ref_message_12")
  then(Message_13)
end

```

<!-- { section: "cd23ec72-ecf3-4fd9-b568-64ba29152520", x: 10560, y: -96} -->

```stack
card Message14_1 do
  write_result("module3_attitudes", "a")
  then(Message_15_1)
end

```

<!-- { section: "31070e96-1db3-47f1-ac8a-0e1102c67af8", x: 10560, y: 696} -->

```stack
card Message14_2 do
  write_result("module3_attitudes", "b")
  then(Message_15_2)
end

```

<!-- { section: "ada5102c-fe96-4d5e-bf25-50f208d3a332", x: 10536, y: 1512} -->

```stack
card Message14_3 do
  write_result("module3_attitudes", "c")
  then(Message_15_3)
end

```

<!-- { section: "00769b65-5520-4adb-8cb1-f26b391c7dba", x: 12840, y: 336} -->

```stack
card Message16_1 do
  write_result("module3_social_norms", "a")
  then(Message_17)
end

```

<!-- { section: "dfc50551-0f44-4ff0-9cae-8f6d5ff7dad7", x: 12840, y: 696} -->

```stack
card Message16_2 do
  write_result("module3_social_norms", "b")
  then(Message_17)
end

```

<!-- { section: "9aa4ebeb-1aa1-4b20-9a59-c0d4f14a4027", x: 12840, y: 1056} -->

```stack
card Message16_3 do
  write_result("module3_social_norms", "c")
  then(Message_17)
end

```

<!-- { section: "df339600-4d51-4676-9b42-7b9f6a640bd8", x: 19008, y: 720} -->

```stack
card Message22_1 do
  write_result("module3_behavioral_activation", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "8d86013c-c182-41b6-95be-a9a41ba645ad", x: 19008, y: 1152} -->

```stack
card Message22_2 do
  write_result("module3_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "187894c1-0cd1-4efd-903f-bc0d6c1e8ba7", x: 19008, y: 1584} -->

```stack
card Message22_3 do
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
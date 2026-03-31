<!-- { section: "f90c6541-4845-4262-9d7b-29574698866f", x: -960, y: -72} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_any_exact_phrase(event.message.text.body, ["Ludificado", "Game", "Play", "Jugar"])

```

<!-- { section: "f793eaf5-43e9-4f09-9e2d-bb18a85be5a9", x: -360, y: -72} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Hola!* 👋 Soy LíA, una amiga digital con la que puedes hablar de relaciones de pareja🌟 ¡Pero ojo! No es necesario que estés o hayas estado en una relación de pareja para hablar conmigo"
  )

  then(Message1)
end

```

<!-- { section: "2b4f3b7d-a3e5-4619-8f19-afd58437e8a4", x: 792, y: -72} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Soy un robot, no tengas pena ni te preocupes por lo que me digas, ¡tus secretos quedarán guardados entre tú y yo!  🤝"
  )

  then(Message_3)
end

```

<!-- { section: "c170cfc3-a360-4d4a-906a-dfcfc3dc368a", x: 1176, y: -72} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["Entendido 🌸"]) do
      text(
        "Aunque me gustaría, no tengo el poder de responder preguntas 🥲, así que, nuestra interacción será solo por medio de tus respuestas a las opciones que te muestre cuando te hago una pregunta"
      )
    end

  write_result("message_3", ref_Message_3)
  then(Message_4 when ref_Message_3 == "Entendido 🌸")
  then(Catch_all_1)
end

```

<!-- { section: "7679760e-40bd-4b8f-bf4b-806b3707b868", x: 1176, y: -432} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_3)
end

```

<!-- { section: "e19ac4dd-c5ce-44e8-81db-2d32456319c2", x: 1680, y: -72} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Entendido 🌸"]) do
      text(
        "Pilar y Mari son mis creadoras. Ellas son chicas como tú, les gusta salir, bromear y bailar. Viven en Bogotá. Juntas, tienen un podcast en el que hablan de temas que a todas nos interesan ❤️"
      )
    end

  write_result("message_4", ref_Message_4)
  then(Message_5 when ref_Message_4 == "Entendido 🌸")
  then(Catch_all_2)
end

```

<!-- { section: "4650558f-344c-40d1-af40-cdbee0bf63ab", x: 1680, y: -432} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "84787207-98fe-49a1-9af6-db27ea17d18b", x: 2544, y: -72} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["¡Cuéntame más! 🎧"]) do
      text(
        "Durante los próximos 6 días, escucharás el podcast de Pilar y Mari. Cada día, tocarán un tema en específico en el que, a través de audios y preguntas, podremos interactuar y conocer mucho más sobre las relaciones románticas. No tardarás más de 10 minutos al día ⏱️"
      )
    end

  write_result("message_5", ref_Message_5)
  then(Message_6 when ref_Message_5 == "¡Cuéntame más! 🎧")
  then(Catch_all_3)
end

```

<!-- { section: "38c27801-7794-4073-a396-7961aaf8d66c", x: 2544, y: -432} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_5)
end

```

<!-- { section: "bdc4e8e8-71ec-48b1-acc7-2249bd19d1f4", x: 3024, y: -72} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "MEDIA_AUDIO" do
  audio("9153cdf1-7219-45a8-a90a-eba59f86167b-G_I_OP_2.mp3")
  then(Message_6_1)
end

```

<!-- { section: "36709e9d-9fbe-47dd-ba91-78dd885e99c2", x: 3504, y: -72} -->

```stack
card Message_6_1, "Message_6_1",
  version: "1",
  uuid: "6b6b9c02-132b-5be6-8e42-efa85fd5a4d4",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6_1 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_6", ref_Message_6_1)
  then(Message_7 when ref_Message_6_1 == "Ya escuché el audio!")
  then(Catch_all_4)
end

```

<!-- { section: "2e8f4df0-76dd-42ab-9114-24e9f4c70d9e", x: 4008, y: -72} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Entendido 🌸"]) do
      text(
        "Pero, antes de empezar, quiero recordarte algo…

Nuestro podcast y nuestras preguntas hablan de la vida diaria. Pero si hay algo de lo que hablan Pilar y Mari o alguna pregunta te llega a hacer sentir incómoda, puedes cerrar la conversación. ¡Para nosotras, lo más importante es que te sientas bien!

Si sientes que necesitas ayuda o quieres hablar con alguien, envía la palabra \"ayuda\" en cualquier momento."
      )
    end

  write_result("message_7", ref_Message_7)
  then(Message_8 when ref_Message_7 == "Entendido 🌸")
  then(Catch_all_5)
end

```

<!-- { section: "0585e085-889a-49c6-a840-1888562e0955", x: 3504, y: -432} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6_1)
end

```

<!-- { section: "1eec3404-e4fd-4a3c-95d9-9814689c2aff", x: 4008, y: -432} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "7ad6ac15-9102-4f8c-b37d-c01c54116322", x: 4560, y: -72} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "QUESTION" do
  ref_Message_8 = ask("¿Puedes decirme tu nombre o contarme cómo quieres que te llame? 🤩")
  update_contact(name: "@ref_Message_8")
  then(Profile_5651c6)
end

```

<!-- { section: "ab7976f0-1c93-40f5-9b4a-1b214fcd8ef5", x: 5592, y: -72} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Sí ✅", "No ❌"]) do
      text("¿Entendí bien que puedo llamarte @contact.name? 👀")
    end

  then(Insight_1 when ref_Message_9 == "Sí ✅")
  then(Message_10 when ref_Message_9 == "No ❌")
  then(Catch_all_6)
end

```

<!-- { section: "62da57d5-fc60-429b-ad0a-abe089b41a49", x: 5592, y: -336} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_9)
end

```

<!-- { section: "29f4174e-714c-4611-8db2-3f3fbfd87dd2", x: 5592, y: 432} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "QUESTION" do
  ref_Message_10 =
    ask("¡Vamos a intentarlo de nuevo! Escribe el nombre por el que quieres que te llame 🤩")

  update_contact(name: "@ref_Message_10")
  then(Profile_5259a4)
end

```

<!-- { section: "30ebc66c-9dea-47b2-bebc-1ddfc002f2e8", x: 6336, y: -696} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "QUESTION" do
  ref_Message_11 =
    ask(
      "¿Puedes escribir tu número de tarjeta de identidad? 🪪 Esta información solo la usaremos para completar tu registro."
    )

  then(IDCard)
end

```

<!-- { section: "ea821f0b-2c27-4480-9fbd-96e971909e2f", x: 7344, y: 0} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Si ✅", "No ❌"]) do
      text("¿Entendí bien que tu número de tarjeta de identidad es @contact.idcard? 🪪")
    end

  then(Message_14 when ref_Message_12 == "Si ✅")
  then(Message_13 when ref_Message_12 == "No ❌")
  then(Catch_all_7)
end

```

<!-- { section: "7df556bd-7f55-450d-a811-acbadc3fa2f1", x: 7272, y: -672} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "5f87e515-1214-4ac0-8fff-d2dfa707ddb8", x: 6792, y: 192} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "QUESTION" do
  ref_Message_13 =
    ask("¡Vamos a intentarlo de nuevo! Escribe el número de tu tarjeta de identidad 🤩")

  then(IDCard)
end

```

<!-- { section: "3c5d86ae-b7ff-4457-a49b-5ee2933b8281", x: 7992, y: 144} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "TEXT_MESSAGE" do
  text("Encantada de conocerte, @contact.name😜")
  then(Message14)
end

```

<!-- { section: "1620ef9a-ee98-42a6-932c-db283b12a858", x: 9216, y: 48} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Vamos ✅"]) do
      text(
        "¿Lista para escuchar el podcast de Pilar y Mari? Acompáñame a escucharlas durante esta semana ❤️"
      )
    end

  write_result("message_15", ref_Message_15)
  then(RunStack_65436a when ref_Message_15 == "Vamos ✅")
  then(Catch_all_8)
end

```

<!-- { section: "632aed11-78fd-4964-bb1d-dd48802008ee", x: 9888, y: 48} -->

```stack
card RunStack_65436a, "RunStack_65436a",
  version: "1",
  uuid: "d8800400-eeef-5894-ba0e-64bbe4db71b3",
  code_generator: "RUN_STACK" do
  run_stack("bf54c800-5e51-495e-945c-44b0621988f3")
end

```

<!-- { section: "21dc005d-2157-4057-818f-99c9644c0180", x: 9216, y: -168} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "bf7004a5-8588-42f2-afe1-79490424f69a", x: 4992, y: -72} -->

```stack
card Profile_5651c6, "Profile_5651c6",
  version: "1",
  uuid: "0f20c229-6876-586c-8bb0-6a159b0c15be",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "ef632cda-b423-46ee-813f-90a2e2bee2d2", x: 4992, y: 168} -->

```stack
card Profile_5259a4, "Profile_5259a4",
  version: "1",
  uuid: "dfcb7e74-f5c2-5c4e-891f-93df3e7d2c85",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_10")
  then(Message_9)
end

```

<!-- { section: "5ca4aac7-a546-4050-8757-29742adaa8ac", x: 5976, y: -72} -->

```stack
card Insight_1, "Insight_1",
  version: "1",
  uuid: "0cca68d1-d82d-4a0d-907b-2297fd59c043",
  code_generator: "WRITE_RESULTS" do
  write_result("message_9", "Sí ✅")
  then(Message_11)
end

```

<!-- { section: "86c128ba-3ec1-4343-9578-9f43468cf125", x: 6264, y: 432} -->

**@Eng we need a check here**

The LATAM ID number has 10 numbers, please set up a check here to confirm that the id they have given us is valid.

Use code block below if needed, if not please delete it

<!-- { section: "e320a447-dc2c-4430-bb35-929b8fcb1192", x: 3960, y: 552} -->

Sentence added here:

EN

If you feel you need help or want to talk to someone, send the word “help” at any time.

ES

Si sientes que necesitas ayuda o quieres hablar con alguien, envía la palabra "ayuda" en cualquier momento.

<!-- { section: "ca197936-ed75-44c2-be50-5ba8e7e9eba8", x: 3960, y: 840} -->

Content master location:

https://docs.google.com/spreadsheets/d/1YjS4_TXifbk3BUp0Kua3Lfszk2tfHS7b/edit?usp=sharing&ouid=112722710667683232518&rtpof=true&sd=true

<!-- { section: "12773617-e5b8-4725-8e66-69292704c92f", x: 192, y: -72} -->

```stack
card Message1 do
  update_contact(arm: "gamified")
  update_contact(onboarding_complete: "false")
  write_result("onboarding_started", "yes")
  then(Message_2)
end

```

<!-- { section: "10edc390-437d-4a1c-a782-c879a89673b2", x: 6696, y: -696} -->

```stack
card IDCard
     when isnumber(@ref_message_11) and
            len(@ref_message_11) == 10 and
            is_nil_or_empty(@ref_message_13) do
  log("ID updated to @ref_message_11 from message 11")
  update_contact(idcard: "@ref_message_11")
  then(Message_12)
end

card IDCard
     when isnumber(@ref_message_13) and
            len(@ref_message_13) == 10 do
  log("ID updated to @ref_message_13 from message 13")
  update_contact(idcard: "@ref_message_13")
  then(Message_12)
end

card IDCard do
  log("Incorrect ID")
  then(Message_13)
end

```

<!-- { section: "6ad60ddc-1454-4064-914d-ed080284f454", x: 8520, y: 48} -->

```stack
card Message14 do
  update_contact(onboarding_complete: "true")
  write_result("onboarding_completed", "yes")
  then(Message_15)
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
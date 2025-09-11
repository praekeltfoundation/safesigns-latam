<!-- { section: "651f2225-1379-4c1b-8ec6-76a699512844", x: -960, y: 24} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_any_exact_phrase(event.message.text.body, ["Ludificado", "Game", "Play", "Jugar"])

```

<!-- { section: "c4a05dd3-2089-4cdc-abc2-f7d0c90081f9", x: -504, y: 24} -->

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

<!-- { section: "1a54e52d-1099-409a-a765-f55abfaab46b", x: 864, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Soy un robot, así que no tengas pena ni te preocupes por lo que me digas, ¡tus secretos quedarán guardados entre tú y yo! 🤐"
  )

  then(Message_3)
end

```

<!-- { section: "c45fe259-c7ba-4861-8aa4-fb4910b10c4c", x: 1368, y: 0} -->

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

  then(Message_4 when ref_Message_3 == "Entendido 🌸")
  then(Catch_all_1)
end

```

<!-- { section: "c1d839e7-3019-4961-adbd-17b637dd07f9", x: 1464, y: -624} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_3)
end

```

<!-- { section: "b77aebaa-094e-4f12-95eb-768593154757", x: 1968, y: 0} -->

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

  then(Message_5 when ref_Message_4 == "Entendido 🌸")
  then(Catch_all_2)
end

```

<!-- { section: "90dafd4c-faf4-49b3-a292-efc8d34713ee", x: 1968, y: -648} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "bf1429a4-c16f-476c-aaed-ff595524d165", x: 2544, y: 0} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["¡Cuéntame más! 🎧"]) do
      text(
        "Durante los próximos 6 días, escucharás el podcast de Pilar y Mar. Cada día, tocarán un tema en específico en el que, a través de audios y preguntas, podremos interactuar y conocer mucho más sobre las relaciones románticas. No tardarás más de 10 minutos al día ⏱️"
      )
    end

  then(Message_6 when ref_Message_5 == "¡Cuéntame más! 🎧")
  then(Catch_all_3)
end

```

<!-- { section: "26e3948f-9137-48db-9ea4-c4ea2ddde172", x: 2568, y: -648} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_5)
end

```

<!-- { section: "a1c5bb78-db77-4790-9efb-d327b1c3953e", x: 3024, y: 72} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "MEDIA_AUDIO" do
  audio("9153cdf1-7219-45a8-a90a-eba59f86167b-G_I_OP_2.mp3")
  then(Message_6_1)
end

```

<!-- { section: "33c40b04-595e-4a14-889e-6f0679dfb15c", x: 3504, y: 72} -->

```stack
card Message_6_1, "Message_6_1",
  version: "1",
  uuid: "6b6b9c02-132b-5be6-8e42-efa85fd5a4d4",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6_1 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_7 when ref_Message_6_1 == "Ya escuché el audio!")
  then(Catch_all_4)
end

```

<!-- { section: "af2cafa7-6292-4edd-b282-f38798aaac90", x: 4008, y: 72} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Entendido 🌸"]) do
      text(
        "Pero, antes de empezar, quiero recordarte algo…

Nuestro podcast y nuestras preguntas hablan de la vida diaria. Pero si hay algo de lo que hablan Pilar y Mari o alguna pregunta te llega a hacer sentir incómoda, puedes cerrar la conversación. ¡Para nosotras, lo más importante es que te sientas bien!"
      )
    end

  then(Message_8 when ref_Message_7 == "Entendido 🌸")
  then(Catch_all_5)
end

```

<!-- { section: "755c76ca-bf0d-4cbb-92e6-2d4d5807dff8", x: 3336, y: -672} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6_1)
end

```

<!-- { section: "7e933b59-e095-4c85-acbc-37cef69fff9a", x: 4008, y: -696} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "9a940804-78f2-45d6-a3c6-0222b2f9df2c", x: 4560, y: 0} -->

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

<!-- { section: "896109c4-4988-4cfa-9ab2-5942cde2d105", x: 5592, y: 24} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Sí ✅", "No ❌"]) do
      text("¿Entendí bien que puedo llamarte @contact.name? 👀")
    end

  then(Message_11 when ref_Message_9 == "Sí ✅")
  then(Message_10 when ref_Message_9 == "No ❌")
  then(Catch_all_6)
end

```

<!-- { section: "925af20c-02fe-4380-a7cd-83a913b6922e", x: 5640, y: -768} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_9)
end

```

<!-- { section: "20dbf338-ba8d-4d9b-a6f3-e61cb253cb1a", x: 4872, y: 600} -->

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

<!-- { section: "ac0ac527-20e4-4269-bef5-5814cb5432a5", x: 6216, y: 72} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "QUESTION" do
  ref_Message_11 = ask("¿Puedes escribir tu número de tarjeta de identidad?")
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
      text("¿Entendí bien que tu número de tarjeta de identidad es @contact.idcard? 👀")
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

<!-- { section: "16c3b765-8bb8-4976-b338-e22fea03bffc", x: 6960, y: 576} -->

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

<!-- { section: "9a7f3b95-d5ae-4d00-8885-c636edfef0ce", x: 9216, y: 96} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Vamos ✅"]) do
      text(
        "¿Lista para escuchar el podcast de Pilar y Mar? Acompáñame a escucharlas durante esta semana ❤️"
      )
    end

  then(RunStack_65436a when ref_Message_15 == "Vamos ✅")
  then(Catch_all_8)
end

```

<!-- { section: "4d6c9cdd-86d3-4a32-974a-410ab72e08a9", x: 9888, y: 96} -->

```stack
card RunStack_65436a, "RunStack_65436a",
  version: "1",
  uuid: "d8800400-eeef-5894-ba0e-64bbe4db71b3",
  code_generator: "RUN_STACK" do
  run_stack("0d85be77-dba2-407b-b5bb-32c040a3e572")
end

```

<!-- { section: "5374b6b6-1c8d-4484-801a-9406ea2e49fb", x: 9264, y: -624} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "e5d6530c-9aea-42d8-b700-00dc6580a1a8", x: 4992, y: -24} -->

```stack
card Profile_5651c6, "Profile_5651c6",
  version: "1",
  uuid: "0f20c229-6876-586c-8bb0-6a159b0c15be",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "d0e5529b-6556-487f-966b-169f9bc41084", x: 4968, y: 168} -->

```stack
card Profile_5259a4, "Profile_5259a4",
  version: "1",
  uuid: "dfcb7e74-f5c2-5c4e-891f-93df3e7d2c85",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_10")
  then(Message_9)
end

```

<!-- { section: "aa667a47-a1bd-4484-9b62-083591d25d7e", x: 0, y: 552} -->

arm = gamified

<!-- { section: "5e5f4d5d-3d87-426a-a490-2eeba330342b", x: 0, y: 480} -->

onboarding_complete = no

<!-- { section: "92504105-750b-4af4-bb66-41672e4a7187", x: 336, y: 576} -->

**DS note:**

Contact field: arm (gamified)

Flow result: onboarding_started (yes)

<!-- { section: "4b317231-b93d-4acd-b881-0d39bbe79167", x: 672, y: 576} -->

link this in to the above flow when done & dlt this note

<!-- { section: "86c128ba-3ec1-4343-9578-9f43468cf125", x: 6264, y: 432} -->

**@Eng we need a check here**

The LATAM ID number has 10 numbers, please set up a check here to confirm that the id they have given us is valid.

Use code block below if needed, if not please delete it

<!-- { section: "6e55721a-8cc5-4d0d-801d-ed6d56817ecb", x: 8448, y: 408} -->

**@Buhle**

Update contact field:
onboarding_completed =yes**

DS note:**

~~Contact field: id_card {user input}~~

Flow result: onboarding_completed (yes)

**@Tam**

Is this different from the idcard that we are using for updating contact field after user validation? **Contact field: id_card {user input} ✅**

<!-- { section: "b3625884-adf4-4079-9011-b6a68dd406dd", x: 0, y: 336} -->

**@Buhle**

please do these, I added a code block for you here just in case

<!-- { section: "9789a6fa-9545-4419-8e34-535fa75c1be5", x: 4632, y: 408} -->

**@Buhle**

save user name / input here

<!-- { section: "476d5837-dfb8-472b-a53c-e1e80101ace2", x: 6264, y: 312} -->

**@Buhle** save user input here

(Validate 10 digits here for ID number)

<!-- { section: "12773617-e5b8-4725-8e66-69292704c92f", x: 192, y: -72} -->

```stack
card Message1 do
  update_contact(arm: "gamified")
  update_contact(onboarding_complete: "false")
  write_result("onboarding_started", "yes")
  then(Message_2)
end

```

<!-- { section: "cdceeee7-2b44-4864-98fa-4e0653966947", x: 6792, y: -72} -->

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
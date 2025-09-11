<!-- { section: "f8a695ab-7b62-499e-ba95-3426b5d40978", x: -1896, y: -192} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_any_exact_phrase(event.message.text.body, [
       "NOB",
       "Narrativo",
       "Narrative",
       "Listen",
       "escuchar"
     ])

```

<!-- { section: "ca3ae92f-72c0-40d8-a23b-4f1341d67b5a", x: -1032, y: -144} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Hola!* 👋 Soy LíA, una amiga digital con la que puedes hablar sobre relaciones de pareja🌟 ¡Pero ojo! No es necesario que estés o hayas estado en una relación de pareja para hablar conmigo."
  )

  then(Message1)
end

```

<!-- { section: "5aa51722-4a89-40f4-bba5-2800866e181a", x: 912, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Soy un robot, no tengas pena ni te preocupes por lo que me digas, ¡tus secretos quedarán guardados entre tú y yo! 🤐"
  )

  then(Message_3)
end

```

<!-- { section: "2329078f-486d-41ce-9492-d1c0e1d1e45d", x: 1464, y: 0} -->

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
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
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
    buttons(["Cuéntame"]) do
      text(
        "Por los próximos 6 días, te iré contando la inquietante historia de Pilar, una chica a la que le acaba de ocurrir algo que nunca se imaginó… Cada día, habrá un episodio que te iré contando a través de audios para aprender juntas. No te tomará más de 10 minutos al día ⏱️"
      )
    end

  then(Message_5 when ref_Message_4 == "Cuéntame")
  then(Catch_all_2)
end

```

<!-- { section: "90dafd4c-faf4-49b3-a292-efc8d34713ee", x: 1968, y: -648} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
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
    buttons(["Entendido 🌸"]) do
      text(
        "Pero antes de empezar, quiero recordarte algo…

La historia de Pilar y mis preguntas hablan de la vida diaria. Pero si hay algo de lo que hable la historia o alguna pregunta te llega a hacer sentir incómoda, puedes cerrar la conversación. ¡Para mí es muy importante que te sientas bien!"
      )
    end

  then(Message_6 when ref_Message_5 == "Entendido 🌸")
  then(Catch_all_3)
end

```

<!-- { section: "26e3948f-9137-48db-9ea4-c4ea2ddde172", x: 2568, y: -648} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_5)
end

```

<!-- { section: "a59dabc3-5f40-4477-8fc6-2c712d22cc64", x: 3240, y: 48} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "QUESTION" do
  ref_Message_6 = ask("¿Puedes decirme tu nombre o cómo quieres que te llame? 🤩")
  update_contact(name: "@ref_Message_6")
  then(Profile_a53e9f)
end

```

<!-- { section: "db1895a5-f399-4f2b-8c1c-3e1bba289442", x: 4344, y: 48} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Sí ✅", "No ❌"]) do
      text("¿Entendí bien que puedo llamarte @contact.name? 👀")
    end

  then(Message_9 when ref_Message_7 == "Sí ✅")
  then(Message_8 when ref_Message_7 == "No ❌")
  then(Catch_all_6)
end

```

<!-- { section: "b5249f1c-09f8-4bc0-8e16-64c85f84d567", x: 4224, y: -480} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_7)
end

```

<!-- { section: "ab2ac5a8-b9da-4eef-83e8-9c68e9a3797f", x: 4368, y: 528} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "QUESTION" do
  ref_Message_8 =
    ask("¡Vamos a intentarlo de nuevo! Escribe el nombre por el que quieres que te llame 🤩")

  update_contact(name: "@ref_Message_8")
  then(Profile_d89a1b)
end

```

<!-- { section: "9238d153-ecbc-4b2b-9c89-8c69393f20ce", x: 5184, y: 96} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "QUESTION" do
  ref_Message_9 = ask("¿Puedes escribir tu número de tarjeta de identidad?")
  then(IDCard)
end

```

<!-- { section: "69a83175-5d3c-42cf-a1fc-9712d0e74ba9", x: 6432, y: 96} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Sí  ✅", "No ❌"]) do
      text("¿Entendí bien que tu número de tarjeta de identidad es  @contact.idcard? 👀")
    end

  then(Message14 when ref_Message_10 == "Sí  ✅")
  then(Message_11 when ref_Message_10 == "No ❌")
  then(Catch_all_7)
end

```

<!-- { section: "dd4a8add-a9ce-4e04-9ef1-8c7d36670fb7", x: 6480, y: -456} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_10)
end

```

<!-- { section: "7faebcbf-350d-4758-8c60-0397ba50c47d", x: 5760, y: 744} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "QUESTION" do
  ref_Message_11 =
    ask("¡Vamos a intentarlo de nuevo! Escribe el número de tu tarjeta de identidad 🤩")

  then(IDCard)
end

```

<!-- { section: "4815cdc0-e2af-446b-ae4d-9d3b0262a777", x: 8040, y: 216} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "TEXT_MESSAGE" do
  text("Encantada de conocerte, @contact.name😜")
  then(Message_13)
end

```

<!-- { section: "8cea85b5-f215-43fa-84fa-cdffc7e13100", x: 8688, y: 216} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Vamos ✅"]) do
      text(
        "¿Lista para escuchar la historia de Pilar? Acompáñame a escucharla durante esta semana ❤️"
      )
    end

  then(Profile_0bf81d when ref_Message_13 == "Vamos ✅")
  then(Catch_all_8)
end

```

<!-- { section: "214ae553-f7b8-44f1-836f-321e053d4c42", x: 10008, y: 264} -->

```stack
card RunStack_65436a, "RunStack_65436a",
  version: "1",
  uuid: "d8800400-eeef-5894-ba0e-64bbe4db71b3",
  code_generator: "RUN_STACK" do
  run_stack("b13a77d8-25b7-4ead-97bf-a81202927a30")
end

```

<!-- { section: "f2331a9d-9f68-4281-9779-1f3ca13d59c6", x: 8784, y: -576} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones.")
  then(Message_13)
end

```

<!-- { section: "e5081ad4-76e9-41e9-b97d-9b5d96795444", x: 9336, y: 264} -->

```stack
card Profile_0bf81d, "Profile_0bf81d",
  version: "1",
  uuid: "0e76525e-bc05-5ef7-b8ec-917d6bdc9342",
  code_generator: "UPDATE_CONTACT" do
  update_contact(onboarding_complete: "true")
  then(RunStack_65436a)
end

```

<!-- { section: "1872889c-c40f-4f57-ab4a-954d52ebd497", x: 3728, y: 48} -->

```stack
card Profile_a53e9f, "Profile_a53e9f",
  version: "1",
  uuid: "88c61b98-d02b-59ef-afa3-ddea87eca42b",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_6")
  then(Message_7)
end

```

<!-- { section: "a5bdd0dc-9228-4fd7-82cb-3689872afa6b", x: 4392, y: 936} -->

```stack
card Profile_d89a1b, "Profile_d89a1b",
  version: "1",
  uuid: "c07439c1-562c-59c6-9d53-96b898c2563f",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_8")
  then(Message_7)
end

```

<!-- { section: "86fdecd1-eeb7-476e-96a4-43c2a698ac20", x: -312, y: 360} -->

Update contact field,

arm = narrative ✅

<!-- { section: "79a613a3-728b-4733-946f-4b97e279575d", x: 24, y: 384} -->

Update contact field,

onboarding_complete = no ✅

<!-- { section: "b7e3df42-06c2-45b5-a6bb-2e96b8ed4cd9", x: 480, y: 192} -->

**@Buhle**

Please add this in**

DS note:**

Contact field: arm (gamified)

Flow result: onboarding_started (yes)

<!-- { section: "d7e4f69f-7c86-4c5f-8955-ff75c648e879", x: 456, y: 456} -->

link this in to the above flow when done & dlt this note

<!-- { section: "095a7ed9-50f9-447e-911e-9dd066bbe38d", x: 5160, y: 504} -->

**@Eng we need a check here**

The LATAM ID number has 10 numbers, please set up a check here to confirm that the id they have given us is valid.

Use code block below if needed, if not please delete it

<!-- { section: "187f1232-1965-4a3b-bcab-c22aee80e776", x: 5160, y: 360} -->

**@Buhle**

We need to save the users input here, @Eng please double check this is correct

<!-- { section: "cd02770b-ad3f-4ec5-9c68-e10b1c30cbea", x: 6840, y: 552} -->

**@Buhle**

We have a DS thing here as well, I added bot in for you, not sure which you need
**

DS note:**

Contact field: id_card {user input}

Flow result: onboarding_completed (yes)

<!-- { section: "6cd60465-3d98-4748-9bee-f453c0e36378", x: 1512, y: 408} -->

Emoji missing here

<!-- { section: "86adb008-ef2f-4fb0-9951-b28af1c78317", x: 4008, y: 672} -->

**@Buhle,**

Please save users name/input

<!-- { section: "30e6512d-1ccc-4f2d-893f-b596f3b2560f", x: 9336, y: 480} -->

Update contact field:
onboarding_completed =yes ✅

<!-- { section: "4f4a6ba9-139e-4cd9-8d6d-6b21c908e020", x: 5784, y: 0} -->

```stack
card IDCard
     when isnumber(@ref_message_9) and
            len(@ref_message_9) == 10 and
            is_nil_or_empty(@ref_message_13) do
  log("ID updated to @ref_message_9 from message 9")
  update_contact(idcard: "@ref_message_9")
  then(Message_10)
end

card IDCard
     when isnumber(@ref_message_11) and
            len(@ref_message_11) == 10 do
  log("ID updated to @ref_message_11 from message 11")
  update_contact(idcard: "@ref_message_11")
  then(Message_10)
end

card IDCard do
  log("Incorrect ID")
  then(Message_11)
end

```

<!-- { section: "0181c192-473e-41f2-a6e2-1a94db19e6a7", x: 7200, y: 96} -->

```stack
card Message14 do
  write_result("onboarding_completed", "yes")
  then(Message_12)
end

```

<!-- { section: "4e8b25d8-9b77-41ba-b239-af964f0e57c1", x: -24, y: -144} -->

```stack
card Message1 do
  update_contact(arm: "narrative")
  update_contact(onboarding_complete: "false")
  write_result("onboarding_started", "yes")
  then(Message_2)
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
ai_auto_memory(false)

```
<!-- { section: "a7f2b862-817a-4fb5-a264-41bf445f645e", x: -1032, y: 96} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.quiz_post_module1_complete == false and contact.contact_module == "MODULE_1" and
       contact.arm == "GAMIFIED" and contact.onboarding_complete == true

trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_g2")

```

<!-- { section: "bd206fac-2d6b-4b2d-935f-241213bfaa70", x: -216, y: 144} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "7aac204b-8d9c-4530-82f6-86f3f138019e",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("test_gamified_quizpostmodule1", "spa", [],
      translated_body_params: [],
      translated_document: [],
      translated_header: [],
      translated_image: [],
      translated_url: [],
      translated_video: [],
      buttons: ["0"]
    )

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_1)
end

```

<!-- { section: "17762e7a-d6ed-4755-a227-91cf50961bc8", x: 1440, y: -24} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["🤔"]) do
      text(
        "Cuando nos enamoramos, nos encanta todo lo que hace nuestro cuento 🥰 Pero... ¿todo lo que hace es sano?"
      )
    end

  then(Message_3 when ref_Message_2 == "🤔")
  then(Catch_all_2)
end

```

<!-- { section: "cbb2b0c2-3c56-4148-b8f3-ab9a5a7205e7", x: 72, y: -312} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "0b2b8f89-82c9-4fde-a716-f133fff839f9", x: 1392, y: -672} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "6350d3c2-8946-4505-b204-8e3558a85c3d", x: 2064, y: -48} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["¡Genial!"]) do
      text(
        "Te cuento la historia de mi amiga Luisa y su novio Mario. Vamos a ayudarla a detectar cuando su cupido se pasa de la raya 🎯"
      )
    end

  then(Message_4 when ref_Message_3 == "¡Genial!")
  then(Catch_all_3)
end

```

<!-- { section: "084aab97-fd2d-454f-b12a-8c80aa934919", x: 2208, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_3)
end

```

<!-- { section: "8c31ef67-f111-4ed9-a507-4bb972d99680", x: 2760, y: -72} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Lindo, celos de 💖", "Ella se lo buscó 🫠", "Tóxico, se pasó 🚫"]) do
      text(
        "El otro día, Luisa salió toda la tarde con un amigo y se quedó sin pila del celular. Mario trató de llamarla y le escribió toda la tarde, pero nada de nada.

Él se puso furioso y le escribió a todas las amigas exigiendo que le dijeran dónde estaba Luisa, y además le dejó mensajes pasados de tono. Luisa se enojó 😡

Mario le dijo a Luisa que si ella no se desapareciera, él no se pondría tan loco, pero que él la quiere mucho, y por eso se pone celoso. 

¿Qué piensas? 🤔"
      )
    end

  then(Message4_1 when ref_Message_4 == "Lindo, celos de 💖")
  then(Message4_2 when ref_Message_4 == "Ella se lo buscó 🫠")
  then(Message4_3 when ref_Message_4 == "Tóxico, se pasó 🚫")
  then(Catch_all_4)
end

```

<!-- { section: "73f297ce-f97b-403d-a9e1-2cd8e191e119", x: 2976, y: -672} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_4)
end

```

<!-- { section: "d61839b7-418e-4bdb-bb97-f2f7def5157a", x: 4584, y: -432} -->

```stack
card Message_5_1, "Message_5_1",
  version: "1",
  uuid: "3b637dd2-8fcc-5d34-b304-507fd4c1f6e0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Puede que la situación le cause celos a Mario pero ¿Justifica que se ponga así de bravo y que, además la haga sentir culpable? Tal vez Luisa pudo comunicarse mejor, pero no es su responsabilidad el cómo Mario reaccione."
  )

  then(Message_6)
end

```

<!-- { section: "bae76967-bc24-4800-89a1-202f7d0c2d06", x: 4560, y: 144} -->

```stack
card Message_5_2, "Message_5_2",
  version: "1",
  uuid: "e373d3c9-96d3-52d8-a37f-8ed9b4c96cdc",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No se vale culpar a los demás por nuestras acciones. Tal vez, Luisa pudo comunicarse mejor, pero no es su responsabilidad el cómo Mario reaccione."
  )

  then(Message_6)
end

```

<!-- { section: "c9920261-bc9d-43d9-a9f4-eeb715e2f630", x: 4632, y: 720} -->

```stack
card Message_5_3, "Message_5_3",
  version: "1",
  uuid: "615750a6-fca0-521e-b480-0c72ff9052ee",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡De acuerdo! no se vale culpar a los demás por nuestras acciones. Tal vez, Luisa pudo comunicarse mejor, pero no es su responsabilidad el cómo Mario reaccione."
  )

  then(Message_6)
end

```

<!-- { section: "1784167a-3b27-4155-ab4e-cd1526d77275", x: 5472, y: 120} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["La protege 💖", "No estoy segura 😕", "La controla 🚫"]) do
      text(
        "Hay un grupo de amigas de Luisa que fuman y salen hasta tarde 🪩 Mario no quiere que Luisa salga con ellas porque cree que son una mala influencia. Luisa no está segura de qué decirle..."
      )
    end

  then(Message6_1 when ref_Message_6 == "La protege 💖")
  then(Message6_2 when ref_Message_6 == "No estoy segura 😕")
  then(Message6_3 when ref_Message_6 == "La controla 🚫")
  then(Catch_all_5)
end

```

<!-- { section: "0441c207-9fbf-42fa-ba68-12026e691523", x: 6840, y: -384} -->

```stack
card Message_7_1, "Message_7_1",
  version: "1",
  uuid: "60ba3e8b-40c3-502e-8323-901c685ac179",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Esta no está facil. Por lo general, una pareja no te debería presionar por dejar a tus amigas. Solo tú puedes decidir con quien pasas tiempo. De igual modo, cuando estés con amigas, solo debes hacer cosas con las que te sientas cómoda."
  )

  then(Message_8)
end

```

<!-- { section: "1e132075-acb2-41cc-b60a-a051561425a5", x: 6840, y: 120} -->

```stack
card Message_7_2, "Message_7_2",
  version: "1",
  uuid: "2c92a70b-17f5-5ff1-9ee9-051ecf574de2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Por lo general, una pareja no te debería presionar por dejar a tus amigas. Solo tú puedes decidir con quien pasas tiempo. De igual modo, cuando estés con amigas, solo debes hacer cosas con las que te sientas cómoda."
  )

  then(Message_8)
end

```

<!-- { section: "f8e2aeff-15ec-4ed9-a8da-94a21f5a69fe", x: 6840, y: 528} -->

```stack
card Message_7_3, "Message_7_3",
  version: "1",
  uuid: "c3a37952-5259-54f5-ac08-a6ceb543fa26",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡De acuerdo! Una pareja no te debería presionar por dejar a tus amigas. Solo tú puedes decidir con quien pasas tiempo. De igual modo, cuando estés con amigas, solo debes hacer cosas sobre las que te sientas cómoda."
  )

  then(Message_8)
end

```

<!-- { section: "262408fd-b9e8-4760-84cc-8bf50311b469", x: 5424, y: -1080} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6)
end

```

<!-- { section: "0bd6b88f-d225-4982-85e8-b0127b1788d8", x: 7704, y: 144} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["Pobre Mario 💖", "No estoy segura 😕", "Manipulador 🚫"]) do
      text(
        "Mario le mandó a Luisa una foto donde él estaba sin camisa 🤳 y le pidió a Luisa que le mande una de ella. 

A Luisa le preocupó que alguien más pudiera ver esa foto😳 Mario le dijo que es una por una, y que está mal que él sí le tenga esa confianza y ella no a él."
      )
    end

  then(Message8_1 when ref_Message_8 == "Pobre Mario 💖")
  then(Message8_2 when ref_Message_8 == "No estoy segura 😕")
  then(Message8_3 when ref_Message_8 == "Manipulador 🚫")
  then(Catch_all_6)
end

```

<!-- { section: "6612728f-639c-4277-882b-a0e50ee8eb67", x: 7320, y: -1128} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_8)
end

```

<!-- { section: "e767928f-9a9b-43f8-b963-4f2337652888", x: 9096, y: -360} -->

```stack
card Message_9_1, "Message_9_1",
  version: "1",
  uuid: "c3a0f754-7f11-5ee1-8038-7f0744548590",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo con lo que no te sientas cómoda. Luisa tiene razón de estar preocupada, y no es falta de confianza; por más cuidado que Mario tenga con la foto, nunca sabe si podrían robarle el celular o hakearlo."
  )

  then(Message_10)
end

```

<!-- { section: "f87db9a0-001a-451f-9d89-a0b7be344f4e", x: 9096, y: 144} -->

```stack
card Message_9_2, "Message_9_2",
  version: "1",
  uuid: "a7a44162-d023-584e-886e-0db24185236b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo con lo que no te sientas cómoda. Luisa tiene razón de estar preocupada, y no es falta de confianza; por más cuidado que Mario tenga con la foto, nunca sabe si podrían robarle el celular o hakearlo."
  )

  then(Message_10)
end

```

<!-- { section: "c6eb1bdc-486a-43a8-b538-69461a061aa2", x: 9096, y: 600} -->

```stack
card Message_9_3, "Message_9_3",
  version: "1",
  uuid: "58f08f6d-1c0f-5772-b91b-b7163ce1a543",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡De acuerdo! Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo con lo que no te sientas cómoda. Luisa tiene razón de estar preocupada, y no es falta de confianza; por más cuidado que Mario tenga con la foto, nunca sabe si podrían robarle el celular o hakearlo."
  )

  then(Message_10)
end

```

<!-- { section: "f08dda3e-c263-4c71-9c6b-16f5fd104952", x: 10416, y: 120} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["¡Lindo! dáselas 👍", "Está complicado 🤔", "Medio controlador 🚩"]) do
      text(
        "Luisa tiene contraseñas distintas en sus redes sociales. Le dio a Mario su clave del Snapchat pero no del Insta📲 Mario se las pidió y le ofreció las suyas a cambio. ¿Qué debería hacer Luisa?"
      )
    end

  then(Message10_1 when ref_Message_10 == "¡Lindo! dáselas 👍")
  then(Message10_2 when ref_Message_10 == "Está complicado 🤔")
  then(Message10_3 when ref_Message_10 == "Medio controlador 🚩")
  then(Catch_all_7)
end

```

<!-- { section: "2da312fb-df3f-463d-bca5-c3861d4e4a3c", x: 10320, y: -1248} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "38d177c3-bc07-45bc-b7f1-082d394840f6", x: 11784, y: -168} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Tus contraseñas son parte de tu privacidad. No deberías compartirlas si no te sientes cómoda al respecto. Piénsalo como tu diario: por más confianza que pueda tener Luisa con Mario, no tiene nada de malo que quiera mantener un espacio separado."
  )

  then(Message_12)
end

```

<!-- { section: "0a06563a-05ea-431f-9540-e7ca4a56b527", x: 11760, y: 264} -->

```stack
card Message_11_2, "Message_11_2",
  version: "1",
  uuid: "0513dcce-9769-52f4-97c2-75c59b410956",
  code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Tus contraseñas son parte de tu privacidad. No deberías compartirlas si no te sientes cómoda al respecto. Piénsalo como tu diario: por más confianza que pueda tener Luisa con Mario, no tiene nada de malo que quiera mantener un espacio separado."
  )

  then(Message_12)
end

```

<!-- { section: "9cb1d1eb-cf71-43c7-ba14-edbca0429271", x: 11736, y: 672} -->

```stack
card Message_11_3, "Message_11_3",
  version: "1",
  uuid: "174333e0-c238-5792-bd3b-79c31a3aa349",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡De acuerdo! Tus contraseñas son parte de tu privacidad. No deberías compartirlas si no te sientes cómoda al respecto. Piénsalo como tu diario: por más confianza que pueda tener Luisa con Mario, no tiene nada de malo que quiera mantener un espacio separado."
  )

  then(Message_12)
end

```

<!-- { section: "ddab208a-2a97-4964-afda-96f0a9299d39", x: 12888, y: 264} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["¡Súper bien! 👍", "Puedo mejorar 🙃"]) do
      text("¿Cómo te fue en el mini test? 👀")
    end

  then(Message12_1 when ref_Message_12 == "¡Súper bien! 👍")
  then(Message12_2 when ref_Message_12 == "Puedo mejorar 🙃")
  then(Catch_all_8)
end

```

<!-- { section: "85cd598b-e147-4446-b9f9-feecccc33a41", x: 12768, y: -1104} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "70e0b134-699f-469e-8668-b5bfc07d5a13", x: 14136, y: 96} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Increíble, tienes el radar muy acertado. Ahora, asegúrate de acompañar a tus amigas para que no se pasen de la raya con ellas 💪🏼"
  )

  then(Message_14)
end

```

<!-- { section: "d678a5be-89de-49df-b333-b752eda64af4", x: 14088, y: 600} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "A veces no es fácil detectar cuando buscan controlar o proteger porque tendemos a asociar presión por amor. Vamos a seguir afinando ese radar 🫶"
  )

  then(Message_14)
end

```

<!-- { section: "3730b9a6-49d0-49c2-9a76-c4a90f681a35", x: 14904, y: 264} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "TEXT_MESSAGE" do
  text("*Aquí esta el truco*💡

Si alguien se siente presionada o incómoda, *algo no anda bien*")
  then(Message14)
end

```

<!-- { section: "75d5b624-b862-4692-b485-df7208479806", x: 15840, y: 264} -->

```stack
card RunStack_9eaf87, "RunStack_9eaf87",
  version: "1",
  uuid: "b2d3e8cb-750e-537c-a433-380aac4adcdf",
  code_generator: "RUN_STACK" do
  run_stack("54b257b6-4fb6-4156-b632-e7438073368c")
end

```

<!-- { section: "e8cbe60d-dee3-4432-a24c-346a41c7c671", x: 288, y: 600} -->

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 0

opt c = 2

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 1

opt c = 2

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 1

opt c = 2

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 1

opt c = 2

**@Buhle**

Please add in the other thingies here^

**@Buhle,**

Not sure which was right for the DS note so have both code and save insight here, dlt the one you dont need please.

DS note: Flow result: quiz_pm1_started (yes)

**@Buhle**

Save insights for DS note

Please save these insights here, its a DS note so not sure if you need a save insight or code block, so I have both here, please dlt the one you dont need

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

Update contact field, contact
module : Quiz post module 1 ✅

DS note: Flow result: quiz_pm1_completed (yes)

~~Update contact.next_engagement_time~~

<!-- { section: "3640ac66-ab8a-4351-bdb4-164afadebb4c", x: 3864, y: -120} -->

a = 0

<!-- { section: "85f9a4d8-43bc-4aab-81aa-f9a99f1f81ed", x: 3840, y: 432} -->

b = 0

<!-- { section: "b316b0e3-6a64-4355-93c8-1aa2acfc6ed8", x: 3888, y: 888} -->

c = 2

<!-- { section: "ab1e0450-bccd-4573-aeda-b8640688792a", x: 6528, y: -216} -->

a = 0

<!-- { section: "2c24a8bb-f87d-4277-931e-3928ff52ec6b", x: 6504, y: 264} -->

b = 1

<!-- { section: "12867d60-582a-4a8f-902c-5ca799b9de2c", x: 6528, y: 816} -->

c = 2

<!-- { section: "532fbd80-a32e-4740-9c85-80c452918a01", x: 8736, y: -48} -->

a = 0

<!-- { section: "b2d4c37c-7902-4aa2-8dc7-d61231767aca", x: 8880, y: 432} -->

b = 1

<!-- { section: "7c9affc9-cea5-4ad3-b489-058074ee4bf0", x: 8736, y: 864} -->

c = 2

<!-- { section: "effd72ef-2721-4979-a539-e0804dd96c21", x: 11544, y: 96} -->

a = 0

<!-- { section: "5aff5ae5-65d6-4c87-be24-b153108d3428", x: 11472, y: 456} -->

b = 1

<!-- { section: "55d89592-ab3d-426f-8ee0-2a511e0f5ce0", x: 11520, y: 888} -->

c = 2

<!-- { section: "7b3cc2b4-2c7c-4739-b467-aa12a77fb742", x: 3264, y: 1008} -->

```stack
card CodeBlock_1fee90 do
  text("some text")
end

```

<!-- { section: "0ad18861-87c6-4753-894c-6d23de046930", x: 15360, y: 216} -->

```stack
card Message14 do
  update_contact(quiz_post_module1_complete: "true")
  write_result("quiz_pm1_completed", "Yes")
  then(RunStack_9eaf87)
end

```

<!-- { section: "2f4e219b-2bdd-42b5-b6ba-41a2f62d489f", x: 888, y: -96} -->

```stack
card Message1 do
  write_result("quiz_pm1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "4e093ef6-a74a-455c-8a67-83cb5d4563c5", x: 3840, y: -504} -->

```stack
card Message4_1 do
  write_result("quiz_pm1_q1_value", "a")
  write_result("quiz_pm1_q1_score", "0")
  then(Message_5_1)
end

```

<!-- { section: "bae536be-328b-45df-b2c5-afc3bfef90ce", x: 3864, y: 48} -->

```stack
card Message4_2 do
  write_result("quiz_pm1_q1_value", "b")
  write_result("quiz_pm1_q1_score", "1")
  then(Message_5_2)
end

```

<!-- { section: "672228db-060f-4230-a704-64ab187a575c", x: 3912, y: 552} -->

```stack
card Message4_3 do
  write_result("quiz_pm1_q1_value", "c")
  write_result("quiz_pm1_q1_score", "2")
  then(Message_5_3)
end

```

<!-- { section: "3786011f-f79b-49b0-80d0-5c08810ea322", x: 6096, y: -456} -->

```stack
card Message6_1 do
  opt_a = 0
  write_result("quiz_pm1_q2_value", "a")
  write_result("quiz_pm1_q2_score", "0")
  then(Message_7_1)
end

```

<!-- { section: "8881d63e-ba9c-471b-b22f-413592cf0efc", x: 6120, y: 0} -->

```stack
card Message6_2 do
  write_result("quiz_pm1_q2_value", "b")
  write_result("quiz_pm1_q2_score", "1")
  then(Message_7_2)
end

```

<!-- { section: "4e922942-b1bd-491d-9cd4-bab3e0dfa47d", x: 6144, y: 504} -->

```stack
card Message6_3 do
  write_result("quiz_pm1_q2_value", "c")
  write_result("quiz_pm1_q2_score", "2")
  then(Message_7_3)
end

```

<!-- { section: "7a1d406c-bb96-472f-b83b-60f3e22ec000", x: 8496, y: -504} -->

```stack
card Message8_1 do
  write_result("quiz_pm1_q3_value", "a")
  write_result("quiz_pm1_q3_score", "0")
  then(Message_9_1)
end

```

<!-- { section: "d57ab59b-e7cc-4d6a-b012-f5981d7ffc1b", x: 8496, y: 72} -->

```stack
card Message8_2 do
  write_result("quiz_pm1_q3_value", "b")
  write_result("quiz_pm1_q3_score", "1")
  then(Message_9_2)
end

```

<!-- { section: "5c03ad6f-281c-41f9-ae8b-39a48e9d4f59", x: 8496, y: 480} -->

```stack
card Message8_3 do
  write_result("quiz_pm1_q3_value", "c")
  write_result("quiz_pm1_q3_score", "2")
  then(Message_9_3)
end

```

<!-- { section: "fee95c3a-133a-440a-928e-ec09865adbc7", x: 11064, y: -240} -->

```stack
card Message10_1 do
  write_result("quiz_pm1_q4_value", "a")
  write_result("quiz_pm1_q4_score", "0")
  then(Message_11_1)
end

```

<!-- { section: "94bb9fc4-de86-46df-b75d-e3b1b424ced8", x: 11088, y: 144} -->

```stack
card Message10_2 do
  write_result("quiz_pm1_q4_value", "b")
  write_result("quiz_pm1_q4_score", "1")
  then(Message_11_2)
end

```

<!-- { section: "ab177615-d86f-4ded-9a9d-2eada29d8158", x: 11088, y: 552} -->

```stack
card Message10_3 do
  write_result("quiz_pm1_q4_value", "c")
  write_result("quiz_pm1_q4_score", "2")
  then(Message_11_3)
end

```

<!-- { section: "6a4d0ad6-087d-4b95-a2a7-8aad0d5697b8", x: 13464, y: 72} -->

```stack
card Message12_1 do
  write_result("quiz_pm1_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "c32d9f17-a6b6-485d-bf5a-1d9bb8f4599a", x: 13488, y: 528} -->

```stack
card Message12_2 do
  write_result("quiz_pm1_endline", "b")
  then(Message_13_2)
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
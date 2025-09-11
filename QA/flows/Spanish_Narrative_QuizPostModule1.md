<!-- { section: "43084e90-e3ab-4978-97a2-502783cbd514", x: -480, y: -48} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_1" and contact.quiz_post_module1_complete == false and
       contact.arm == "NARRATIVE"

trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_n2")

```

<!-- { section: "de8ab352-7751-4414-a1c2-d431e00b08d7", x: 24, y: -24} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "72548ac7-357e-49f4-a10a-415c2b229155",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_narrative_quiz_postmod1", "es", [],
      buttons: ["¡Cuéntame más!"]
    )

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_1)
end

```

<!-- { section: "cba701b0-fbc0-4610-aad6-d7f000cc1c3f", x: 1392, y: 0} -->

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

<!-- { section: "d60bbdcd-1d8f-427e-b1e7-787ca3e84f8d", x: 432, y: -312} -->

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

<!-- { section: "0bd8a08d-bcbe-42d9-97c7-24b466fcc827", x: 2208, y: -24} -->

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

<!-- { section: "7b4d730e-338b-476c-aa4f-8a5d681fc043", x: 3024, y: -72} -->

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
    "❌ No se vale culpar a los demás por nuestras acciones. Tal vez Luisa pudo comunicarse mejor, pero no es su responsabilidad el cómo Mario reaccione."
  )

  then(Message_6)
end

```

<!-- { section: "055fe967-d787-4579-945f-36c759aa8684", x: 4560, y: 720} -->

```stack
card Message_5_3, "Message_5_3",
  version: "1",
  uuid: "615750a6-fca0-521e-b480-0c72ff9052ee",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡De acuerdo! no se vale culpar a los demás por nuestras acciones. Tal vez Luisa pudo comunicarse mejor, pero no es su responsabilidad el cómo Mario reaccione."
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

<!-- { section: "ffa5649e-ec34-4877-ad72-e13d24aa7f5d", x: 6792, y: -432} -->

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

<!-- { section: "aff6e403-b092-42ef-b114-9ca217955506", x: 9096, y: -432} -->

```stack
card Message_9_1, "Message_9_1",
  version: "1",
  uuid: "c3a0f754-7f11-5ee1-8038-7f0744548590",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo con lo que no te sientas cómoda. Luisa tiene razón de estar preocupada y no es falta de confianza; por más cuidado que Mario tenga con la foto, nunca sabe si podrían robarle el celular o hackearlo."
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
    "🤔 Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo con lo que no te sientas cómoda. Luisa tiene razón de estar preocupada y no es falta de confianza; por más cuidado que Mario tenga con la foto, nunca sabe si podrían robarle el celular o hackearlo."
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
    "✅ ¡De acuerdo! Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo con lo que no te sientas cómoda. Luisa tiene razón de estar preocupada y no es falta de confianza; por más cuidado que Mario tenga con la foto, nunca sabe si podrían robarle el celular o hackearlo."
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
    buttons(["Lindo! dáselas 👍", "Está complicado 🤔", "Medio controlador 🚩"]) do
      text(
        "Luisa tiene contraseñas distintas en sus redes sociales. Le dio a Mario su clave del Snapchat pero no del Insta📲 Mario se las pidió y le ofreció las suyas a cambio. ¿Qué debería hacer Luisa?"
      )
    end

  then(Message10_1 when ref_Message_10 == "Lindo! dáselas 👍")
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

<!-- { section: "76b1e363-4733-4a40-99c9-28009f847ace", x: 11784, y: -264} -->

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

<!-- { section: "1bd81b93-0ff5-4eb3-aca2-d6179defac93", x: 12624, y: 144} -->

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

<!-- { section: "48279c97-64e7-48b0-9298-f339c626273c", x: 13776, y: 120} -->

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

<!-- { section: "b24d6545-9eb7-42ec-9877-dd828e7f63b7", x: 13824, y: 456} -->

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

<!-- { section: "c8e0a643-c679-4dd7-9fa4-19eec158a260", x: 14256, y: 264} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "TEXT_MESSAGE" do
  text("*Aquí esta el truco*💡

Si alguien se siente presionada o incómoda, *algo no anda bien*")
  then(QuizComplete)
end

```

<!-- { section: "af2462ac-9d9a-440d-a2d7-511aee6aabe9", x: 15720, y: 264} -->

```stack
card RunStack_b8be21, "RunStack_b8be21",
  version: "1",
  uuid: "52e4db99-ef51-5941-9846-c4cda38fe572",
  code_generator: "RUN_STACK" do
  run_stack("30c3600a-31b5-4ee2-ad05-b0ea402dcb52")
end

```

<!-- { section: "d63459ce-649c-4885-bfc4-9f6d1b238348", x: 14928, y: 576} -->

need a variable /insight name based on the grading, see notes under each

code block is here if you need that

opt a = 0

opt b = 0

opt c = 2

need a variable /insight name based on the grading, see notes under each

code block is here if you need that

opt a = 0

opt b = 1

opt c = 2

need a variable /insight name based on the grading, see notes under each

code block is here if you need that

opt a = 0

opt b = 1

opt c = 2

need a variable /insight name based on the grading, see notes under each

code block is here if you need that

opt a = 0

opt b = 1

opt c = 2

<!-- { section: "f30a6823-384c-4e2b-a315-9b8da75169c1", x: 6144, y: 1128} -->

```stack
card CodeBlock_804d50 do
  text("some text")
end

```

<!-- { section: "eced14b3-17cc-407f-b931-6a588fdc51b7", x: 8256, y: 1200} -->

```stack
card CodeBlock_e12bc0 do
  text("some text")
end

```

<!-- { section: "f1c07217-49de-477a-9776-6ae92bd628ab", x: 10680, y: 1200} -->

```stack
card CodeBlock_6379ad do
  text("some text")
end

```

<!-- { section: "ebfc56ca-2ad6-43db-8b90-1d4a6ef5c9fc", x: 912, y: -24} -->

```stack
card Message1 do
  update_contact(quiz_post_module1_complete: "false")
  write_result("quiz_pm1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "1c260742-9ecd-4704-97f0-d8a0f6678ff1", x: 3864, y: 120} -->

```stack
card Message4_2 do
  write_result("quiz_pm1_q1_value", "b")
  write_result("quiz_pm1_q1_score", "0")
  then(Message_5_2)
end

```

<!-- { section: "b80179fb-6df2-4abc-9cda-e89f0b9c981f", x: 3864, y: -480} -->

```stack
card Message4_1 do
  write_result("quiz_pm1_q1_value", "a")
  write_result("quiz_pm1_q1_score", "0")
  then(Message_5_1)
end

```

<!-- { section: "b9fa4eca-7537-47df-b720-6193e6dc50d1", x: 3888, y: 600} -->

```stack
card Message4_3 do
  write_result("quiz_pm1_q1_value", "c")
  write_result("quiz_pm1_q1_score", "2")
  then(Message_5_3)
end

```

<!-- { section: "55a19b11-0ed2-47bd-bc7e-2e8910d643ee", x: 6192, y: -504} -->

```stack
card Message6_1 do
  write_result("quiz_pm1_q2_value", "a")
  write_result("quiz_pm1_q2_score", "0")
  then(Message_7_1)
end

```

<!-- { section: "7a861888-f16f-436e-a648-61e95b75d8bc", x: 6192, y: 0} -->

```stack
card Message6_2 do
  write_result("quiz_pm1_q2_value", "b")
  write_result("quiz_pm1_q2_score", "1")
  then(Message_7_2)
end

```

<!-- { section: "1a99e896-2538-47f6-bc46-e0cd01637068", x: 6192, y: 432} -->

```stack
card Message6_3 do
  write_result("quiz_pm1_q2_value", "c")
  write_result("quiz_pm1_q2_score", "2")
  then(Message_7_3)
end

```

<!-- { section: "2f92f679-698d-4b7c-ad70-32d0aea49ad2", x: 8472, y: -504} -->

```stack
card Message8_1 do
  write_result("quiz_pm1_q3_value", "a")
  write_result("quiz_pm1_q3_score", "0")
  then(Message_9_1)
end

```

<!-- { section: "cc1f4abd-c058-4ef1-9092-212b7457856c", x: 8520, y: -24} -->

```stack
card Message8_2 do
  write_result("quiz_pm1_q3_value", "b")
  write_result("quiz_pm1_q3_score", "1")
  then(Message_9_2)
end

```

<!-- { section: "ef8200cc-57ea-414f-a415-95064856a07f", x: 8568, y: 480} -->

```stack
card Message8_3 do
  write_result("quiz_pm1_q3_value", "c")
  write_result("quiz_pm1_q3_score", "2")
  then(Message_9_3)
end

```

<!-- { section: "c92d9086-327f-4f26-9792-d35baa97dfac", x: 11088, y: -288} -->

```stack
card Message10_1 do
  write_result("quiz_pm1_q4_value", "a")
  write_result("quiz_pm1_q4_score", "0")
  then(Message_11_1)
end

```

<!-- { section: "f9d882e6-7573-481a-b31a-6d2351f51de1", x: 11088, y: 168} -->

```stack
card Message10_2 do
  write_result("quiz_pm1_q4_value", "b")
  write_result("quiz_pm1_q4_score", "1")
  then(Message_11_2)
end

```

<!-- { section: "8a4af672-d4b6-441e-a0c8-f1f19ac3f0b8", x: 11088, y: 576} -->

```stack
card Message10_3 do
  write_result("quiz_pm1_q4_value", "c")
  write_result("quiz_pm1_q4_score", "2")
  then(Message_11_3)
end

```

<!-- { section: "a08bc838-658a-43bb-9f5f-40c5992a7747", x: 13296, y: 24} -->

```stack
card Message12_1 do
  write_result("quiz_pm1_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "71d45828-2100-4500-8a90-77512d6045c0", x: 13320, y: 384} -->

```stack
card Message12_2 do
  write_result("quiz_pm1_endline", "b")
  then(Message_13_2)
end

```

<!-- { section: "c1141239-63bb-42ae-83d8-db3e1e04e1cf", x: 15240, y: 192} -->

```stack
card QuizComplete do
  update_contact(quiz_post_module1_complete: "true")
  write_result("quiz_pm1_completed", "yes")
  then(RunStack_b8be21)
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
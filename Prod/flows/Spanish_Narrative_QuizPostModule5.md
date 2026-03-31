<!-- { section: "427ea4cc-48f1-4537-98d0-ebf304988fa7", x: -1224, y: 192} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_n6")

trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.quiz_post_module5_complete_ == false and contact.contact_module == "MODULE_5" and
       contact.arm == "NARRATIVE"

```

<!-- { section: "8bc9b2e0-cb9a-4b33-aa48-076bc9c44fb6", x: -672, y: 192} -->

```stack
card Insight_1, "Insight_1",
  version: "1",
  uuid: "2d4a8508-0118-4b16-a473-28997edc00eb",
  code_generator: "WRITE_RESULTS" do
  write_result("quiz_post_module5_started", "yes")
  then(Template_1)
end

```

<!-- { section: "2c7609f2-bc71-4ef5-b657-0c6d81df95c7", x: 1320, y: 192} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["¡Genial!"]) do
      text(
        "A veces, cuando peleamos, la conversación se pone caliente, muy caliente. Tanto así, que deja de ser productiva y se vuelve malsana. Te voy a contar tres situaciones y tu dime si el personaje logró mantener la cabeza fría 🥶  o si se nos pasó de caliente 🌶️"
      )
    end

  write_result("message_2", ref_Message_2)
  then(Message_3 when ref_Message_2 == "¡Genial!")
  then(Catch_all_2)
end

```

<!-- { section: "9ef9bc50-e9cc-4ef0-80b7-d2e63b004308", x: -120, y: -120} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "6fad3a3c-7b56-4623-93df-1a3f8de6df08", x: 1296, y: -144} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "7772082b-4e98-478b-8f1c-9755fccd87b1", x: 2400, y: 0} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["A", "B", "C"]) do
      text(
        "Me dijo que me quería tanto que quería que tengamos más intimidad. Le quiero, pero no me siento cómoda con eso 🤔 ¿Qué le respondo?

*A.* Depende de cuánto me quieras 😍
*B.* También te quiero, pero aún no me siento cómoda con eso. Sé que, si me quieres de verdad, me vas a entender 🫶
*C.* Vete al diablo 👿 "
      )
    end

  then(Message3_1 when ref_Message_3 == "A")
  then(Message3_2 when ref_Message_3 == "B")
  then(Message3_3 when ref_Message_3 == "C")
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
  then(Message_3)
end

```

<!-- { section: "d61839b7-418e-4bdb-bb97-f2f7def5157a", x: 4584, y: -432} -->

```stack
card Message_4_1, "Message_4_1",
  version: "1",
  uuid: "ff3b277f-685d-52d5-89c3-d7206c100240",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No necesitas hacer algo con lo que no te sientas cómoda por presión. Si no deseas hacer algo, díselo y, si te quiere de verdad, entenderá."
  )

  then(Message_5)
end

```

<!-- { section: "bae76967-bc24-4800-89a1-202f7d0c2d06", x: 4560, y: 144} -->

```stack
card Message_4_2, "Message_4_2",
  version: "1",
  uuid: "d252d156-2451-59de-adf5-1abbf2f6a438",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡Correcto! No necesitas hacer algo con lo que no te sientas cómoda por presión. Si no deseas hacer algo, díselo, y si te quiere de verdad, entenderá."
  )

  then(Message_5)
end

```

<!-- { section: "055fe967-d787-4579-945f-36c759aa8684", x: 4560, y: 720} -->

```stack
card Message_4_3, "Message_4_3",
  version: "1",
  uuid: "fba27f74-83e2-544a-92da-77a5664f9ec6",
  code_generator: "TEXT_MESSAGE" do
  text(
    "🧐 No necesitas hacer algo con lo que no te sientas cómoda por presión. Sin embargo, hay mejores formas de reaccionar. Basta con decir que no deseas hacer eso."
  )

  then(Message_5)
end

```

<!-- { section: "1784167a-3b27-4155-ab4e-cd1526d77275", x: 5472, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["A", "B", "C"]) do
      text(
        "Me dijo que me iba a dejar si no teníamos el mismo interés en hacer cosas sexy 😮. ¿Qué le respondo?
 
*A.* Lo haré como prueba de amor 😍
*B.* No me siento cómoda con eso. Sé que si me quieres de verdad, vas a entender 🫂
*C.* Lo siento mucho, te estoy fallando 😭"
      )
    end

  then(Message5_1 when ref_Message_5 == "A")
  then(Message5_2 when ref_Message_5 == "B")
  then(Message5_3 when ref_Message_5 == "C")
  then(Catch_all_5)
end

```

<!-- { section: "0441c207-9fbf-42fa-ba68-12026e691523", x: 6840, y: -384} -->

```stack
card Message_6_1, "Message_6_1",
  version: "1",
  uuid: "6b6b9c02-132b-5be6-8e42-efa85fd5a4d4",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Si alguien te amenaza ¡está intentando manipularte! Puedes poner límites y no deberías sentirte mal al respecto."
  )

  then(Message_7)
end

```

<!-- { section: "1e132075-acb2-41cc-b60a-a051561425a5", x: 6840, y: 120} -->

```stack
card Message_6_2, "Message_6_2",
  version: "1",
  uuid: "3f6f5c12-ab22-5e2c-91e0-ee00ca717187",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡Correcto! Si alguien te amenaza ¡está intentando manipularte! Puedes poner límites y no deberías sentirte mal al respecto."
  )

  then(Message_7)
end

```

<!-- { section: "de7c1a19-7d34-4db7-8a6b-8c3f1dbd1233", x: 6840, y: 696} -->

```stack
card Message_6_3, "Message_6_3",
  version: "1",
  uuid: "109da85f-6dfa-5cc2-8d7a-799f3f85535b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No tienes por qué disculparte. Si alguien te amenaza ¡está intentando manipularte! Puedes poner límites y no deberías sentirte mal al respecto."
  )

  then(Message_7)
end

```

<!-- { section: "262408fd-b9e8-4760-84cc-8bf50311b469", x: 5424, y: -1080} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_5)
end

```

<!-- { section: "ac9ea3d2-908f-418c-81ea-6e3ba15ae878", x: 7656, y: 0} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["A", "B", "C"]) do
      text("Estás peleando y graban un video tuyo. ¿Qué es lo que se ve en el video? 📹

*A.* Le doy una cachetada 👋
*B.* Tengo los brazos cruzados, miro para otro lado y pongo los ojos en blanco 🙄
*C.* Le miro a los ojos y hablo asertivamente 🗣️")
    end

  then(Message7_1 when ref_Message_7 == "A")
  then(Message7_2 when ref_Message_7 == "B")
  then(Message7_3 when ref_Message_7 == "C")
  then(Catch_all_6)
end

```

<!-- { section: "5aaad17b-1164-440a-917a-9392714f2c4c", x: 7680, y: -1152} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "e767928f-9a9b-43f8-b963-4f2337652888", x: 9096, y: -360} -->

```stack
card Message_8_1, "Message_8_1",
  version: "1",
  uuid: "4fa17f97-59bc-50b4-aaa7-bfc5081c1410",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No necesitan caer en gritos ni insultos para mandar vibras agresivas. Cachetear, empujar, o lenguaje corporal que diga \"no te estoy oyendo\" son señales de agresividad. ¡El termómetro se pasó de caliente!"
  )

  then(Message_9)
end

```

<!-- { section: "f87db9a0-001a-451f-9d89-a0b7be344f4e", x: 9096, y: 144} -->

```stack
card Message_8_2, "Message_8_2",
  version: "1",
  uuid: "a6f29f91-5f48-5dc4-80c4-063a12073e9e",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No necesitan caer en gritos ni insultos para mandar vibras agresivas. Si el lenguaje corporal dice \"no te estoy oyendo,\" el termómetro se pasó de caliente"
  )

  then(Message_9)
end

```

<!-- { section: "c6eb1bdc-486a-43a8-b538-69461a061aa2", x: 9096, y: 600} -->

```stack
card Message_8_3, "Message_8_3",
  version: "1",
  uuid: "0f6800cf-6cc5-5057-b513-b93cecfe9ce3",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡Correcto! No necesitan caer en gritos ni insultos para mandar vibras agresivas. Si el lenguaje corporal es calmado y las personas pueden escucharse unas a otras a pesar de las emociones, el termómetro no se ha pasado de caliente"
  )

  then(Message_9)
end

```

<!-- { section: "3333efb1-d2d3-4286-858f-c7cd11f61b49", x: 12720, y: -120} -->

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

<!-- { section: "2c1bb9cc-882b-48eb-9b1d-3612a1fc735f", x: 12744, y: -984} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "ee1ea4cc-78cc-45b6-ab28-33bfbeea3970", x: 14112, y: -240} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Eres muy buena poniendo límites y lo sabes💫 Puedes compartir tu experiencia con amigas que necesiten un empujoncito para hacerse valer  💪🏼🫣"
  )

  then(Message_14)
end

```

<!-- { section: "30e9df33-e5e8-4892-9aea-85602429733c", x: 14064, y: 336} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Tus límites a veces son de gelatina todavía 🍮 ¡Ten más confianza en ti! Esta bien decir lo que quieres y necesitas mientras lo hagas con respeto y asertividad 👀"
  )

  then(Message_14)
end

```

<!-- { section: "5e096b31-9bf0-4b34-a9e7-ce3209bf9644", x: 14784, y: -48} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Recuerda los límites sanos son puro amor, amor por ti y por los demás ✨

No puedes amar ni hacer feliz a nadie, mientras nos seas feliz tú. ¡Todo empieza desde la seguridad y el amor propio!"
  )

  then(QuizComplete)
end

```

<!-- { section: "0da0b28e-7ffc-4c25-b100-706d7c1cb5c2", x: 16704, y: -168} -->

```stack
card RunStack_b8be21, "RunStack_b8be21",
  version: "1",
  uuid: "52e4db99-ef51-5941-9846-c4cda38fe572",
  code_generator: "RUN_STACK" do
  run_stack("2177501b-25f9-4a0f-a614-d50cadaf74ec")
end

```

<!-- { section: "e23cb69e-8cae-4aa2-aa07-afc3e3b32a23", x: 9816, y: -24} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "TEXT_MESSAGE" do
  text("Tener buena comunicación es oír y decir lo que quieres de forma asertiva y concisa 👌🏼")
  then(Message_10)
end

```

<!-- { section: "03e683d8-88fb-41be-95d4-81b324ab1c7d", x: 10296, y: -24} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["A", "B", "C"]) do
      text(
        "Tu novio te manda una foto sin camisa y te pide una a ti a cambio. Le dices que no te sientes cómoda y responde \"si no tienes confianza en mí, ¡esto no va para ninguna parte!😡\" ¿Qué respondes?

*A.* No es tema de confianza, sino con lo que me gusta hacer 💁🏽‍♀️
*B.* Si eso es lo que te gusta, entonces mejor lo dejamos hasta aquí 🙅🏽‍♀️
*C.* Yo si confio en tí, aquí va la foto 🤳🏼"
      )
    end

  then(Message10_1 when ref_Message_10 == "A")
  then(Message10_2 when ref_Message_10 == "B")
  then(Message10_3 when ref_Message_10 == "C")
  then(Catch_all_7)
end

```

<!-- { section: "8caa24ee-0f90-45cd-9827-4a6ec9a6fc03", x: 11736, y: -360} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ ¡De acuerdo! Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo sobre lo que no te sientas cómoda. Tendrías razon de estar preocupada, y no es falta de confianza; por más cuidado que tu novio tenga con la foto, núnca sabe si podrían robarle el celular o hackearlo."
  )

  then(Message_12)
end

```

<!-- { section: "96320ddf-26e4-4461-a61a-04e034a8e022", x: 11712, y: 144} -->

```stack
card Message_11_2, "Message_11_2",
  version: "1",
  uuid: "0513dcce-9769-52f4-97c2-75c59b410956",
  code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo sobre lo que no te sientas cómoda. Tendrías razon de estar preocupada, y no es falta de confianza; por más cuidado que tu novio tenga con la foto, núnca sabe si podrían robarle el celular o hackearlo."
  )

  then(Message_12)
end

```

<!-- { section: "954797df-f8bb-4fa9-98c7-263543f3478e", x: 11712, y: 672} -->

```stack
card Message_11_3, "Message_11_3",
  version: "1",
  uuid: "174333e0-c238-5792-bd3b-79c31a3aa349",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Nadie - y menos alguien que dice quererte - puede obligarte a hacer algo sobre lo que no te sientas cómoda. Tendrías razon de estar preocupada, y no es falta de confianza; por más cuidado que tu novio tenga con la foto, núnca sabe si podrían robarle el celular o hackearlo."
  )

  then(Message_12)
end

```

<!-- { section: "041bab41-4f87-4a05-92e9-c8230b003287", x: 10296, y: -840} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "e2f157dc-9ccc-4717-a603-0c12b811e848", x: -120, y: 192} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "c6c6d012-b6ef-4980-948c-821ab4645549",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_narrative_quiz_postmod5", "es", [],
      buttons: ["¡Cuéntame más!"]
    )

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_1)
end

```

<!-- { section: "45d0eca7-8acc-47e0-8d2a-bca50c31cb35", x: 6216, y: 624} -->

```stack
card Message5_3 do
  write_result("quiz_pm5_q2_value", "c")
  write_result("quiz_pm5_q2_score", "0")
  then(Message_6_3)
end

```

<!-- { section: "f067afb4-feee-443e-b545-8d0817dcac64", x: 8472, y: 480} -->

```stack
card Message7_3 do
  write_result("quiz_pm5_q3_value", "c")
  write_result("quiz_pm5_q3_score", "2")
  then(Message_8_3)
end

```

<!-- { section: "239f5148-e268-4dae-93b3-9127a2385531", x: 672, y: 192} -->

```stack
card Message1 do
  update_contact(quiz_post_module5_complete_: "false")
  write_result("template1", "¡Cuéntame más!")
  then(Message_2)
end

```

<!-- { section: "6e815c89-a347-4c5d-9a78-b327cce62136", x: 15912, y: -168} -->

```stack
card QuizComplete do
  update_contact(quiz_post_module5_complete_: "true")
  write_result("quiz_pm5_completed", "yes")
  then(RunStack_b8be21)
end

```

<!-- { section: "0dd020b5-0fe4-4e8b-9064-467420a68c49", x: 3816, y: -504} -->

```stack
card Message3_1 do
  write_result("quiz_pm5_q1_value", "a")
  write_result("quiz_pm5_q1_score", "0")
  then(Message_4_1)
end

```

<!-- { section: "dd92a34f-e02b-48d1-960f-c81187bd0e52", x: 3816, y: 24} -->

```stack
card Message3_2 do
  write_result("quiz_pm5_q1_value", "b")
  write_result("quiz_pm5_q1_score", "2")
  then(Message_4_2)
end

```

<!-- { section: "37db9ecd-f304-4591-a99d-9bc7301d145e", x: 3816, y: 552} -->

```stack
card Message3_3 do
  write_result("quiz_pm5_q1_value", "c")
  write_result("quiz_pm5_q1_score", "1")
  then(Message_4_3)
end

```

<!-- { section: "9c3b26e5-3344-4755-b9fe-18724d51f905", x: 6144, y: -504} -->

```stack
card Message5_1 do
  write_result("quiz_pm5_q2_value", "a")
  write_result("quiz_pm5_q2_score", "0")
  then(Message_6_1)
end

```

<!-- { section: "1c6baede-897e-4534-838f-579c923b91e1", x: 6216, y: 24} -->

```stack
card Message5_2 do
  write_result("quiz_pm5_q2_value", "b")
  write_result("quiz_pm5_q2_score", "2")
  then(Message_6_2)
end

```

<!-- { section: "593c56c4-e635-4d37-aef1-33d7f0d0b198", x: 8520, y: 48} -->

```stack
card Message7_2 do
  write_result("quiz_pm5_q3_value", "b")
  write_result("quiz_pm5_q3_score", "0")
  then(Message_8_2)
end

```

<!-- { section: "065cb2c3-d6eb-48b2-9ee5-74aca876f59f", x: 8496, y: -552} -->

```stack
card Message7_1 do
  write_result("quiz_pm5_q3_value", "a")
  write_result("quiz_pm5_q3_score", "0")
  then(Message_8_1)
end

```

<!-- { section: "3eb59815-3dc0-4821-b8af-125bdd40894c", x: 13392, y: -384} -->

```stack
card Message12_1 do
  write_result("quiz_pm5_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "97347468-ea0b-4652-864b-4601472743a5", x: 13368, y: 72} -->

```stack
card Message12_2 do
  write_result("quiz_pm5_endline", "b")
  then(Message_13_2)
end

```

<!-- { section: "1309527a-1b15-459f-ae77-b02f2155c553", x: 11040, y: -504} -->

```stack
card Message10_1 do
  write_result("quiz_pm5_q4_value", "a")
  write_result("quiz_pm5_q4_score", "2")
  then(Message_11_1)
end

```

<!-- { section: "493075e1-7920-42cf-9d23-cd6f379123bb", x: 11064, y: 24} -->

```stack
card Message10_2 do
  write_result("quiz_pm5_q4_value", "b")
  write_result("quiz_pm5_q4_score", "2")
  then(Message_11_2)
end

```

<!-- { section: "ee3ce35e-977c-4e4a-8594-40fa9dc38605", x: 11088, y: 528} -->

```stack
card Message10_3 do
  write_result("quiz_pm5_q4_value", "c")
  write_result("quiz_pm5_q4_score", "0")
  then(Message_11_3)
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
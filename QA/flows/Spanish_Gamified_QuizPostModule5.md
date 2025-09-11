<!-- { section: "0313b5a4-3dac-4035-94f5-0ff0b8adaa64", x: -1032, y: -144} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_5" and contact.quiz_post_module5_complete_ == false and
       contact.arm == "GAMIFIED"

trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_g6")

```

<!-- { section: "0d7afedf-70c2-467c-8989-63ff975e7d47", x: -528, y: -168} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "8537af2b-0d71-4aab-9b51-bc20e8ebcabb",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_gamified_quiz_postmod5", "es", [], buttons: ["¡Cuéntame más!"])

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_1)
end

```

<!-- { section: "4fb81c87-6904-48ab-a85f-cfe8553d00cc", x: 1728, y: -72} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["¡Genial!"]) do
      text(
        "A veces, cuando peleamos, la conversación se pone caliente, muy caliente. Tanto así, que deja de ser productiva y se vuelve malsana. Te voy a contar tres situaciones y tu dime si el personaje logró mantener la cabeza fría 🥶 o si se nos pasó de caliente 🌶️"
      )
    end

  then(Message_3 when ref_Message_2 == "¡Genial!")
  then(Catch_all_2)
end

```

<!-- { section: "735c8e2f-8a69-41f4-a0cc-17d7369c8e5d", x: 168, y: -408} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "cda1f848-4d20-423e-9ef1-dcb7eba06915", x: 1704, y: -720} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "dd63f22e-abaa-49b8-b755-0feda40b608a", x: 10200, y: -1272} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10)
end

```

<!-- { section: "7b4d730e-338b-476c-aa4f-8a5d681fc043", x: 3024, y: -72} -->

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
    "❌ No necesitas hacer algo con lo que no te sientas cómoda por presión. Si no deseas hacer algo, díselo, y si te quiere de verdad, entenderá!"
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
    "✅ ¡Correcto! No necesitas hacer algo con lo que no te sientas cómoda por presión. Si no deseas hacer algo, díselo, y si te quiere de verdad, entenderá!"
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

<!-- { section: "129b721f-e5a2-486e-b572-5cb4668a3329", x: 5520, y: -168} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["A", "B", "C"]) do
      text(
        "Me dijo que me iba a dejar si no teniamos el mismo interés en hacer cosas sexy 😮. ¿Qué le respondo?
 
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
    " ✅ ¡Correcto! Si alguien te amenaza ¡está intentando manipularte! Puedes poner límites y no deberías sentirte mal al respecto."
  )

  then(Message_7)
end

```

<!-- { section: "f8e2aeff-15ec-4ed9-a8da-94a21f5a69fe", x: 6840, y: 528} -->

```stack
card Message_6_3, "Message_6_3",
  version: "1",
  uuid: "109da85f-6dfa-5cc2-8d7a-799f3f85535b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌  No tienes por qué disculparte. Si alguien te amenaza, ¡está intentando manipularte! Puedes poner límites y no deberías sentirte mal al respecto."
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

<!-- { section: "0df3f5c5-72e9-4723-a33e-50ebb2600aff", x: 7776, y: -144} -->

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

<!-- { section: "666eea30-f5ce-42f0-8ae3-760fb4f1a47e", x: 7824, y: -1128} -->

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
    "❌ No necesitan caer en gritos ni insultos para mandar vibras agresivas. Si el lenguaje corporal dice \"no te estoy oyendo,\" el termómetro se pasó de caliente."
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
    "✅ ¡Correcto! No necesitan caer en gritos ni insultos para mandar vibras agresivas. Si el lenguaje corporal es calmado y las personas pueden escucharse unas a otras a pesar de las emociones, el termómetro no se ha pasado de caliente."
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

<!-- { section: "98df179b-2983-4d6d-a593-a61af3b85f0e", x: 12744, y: -1008} -->

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
    "Tus límites a veces son de gelatina todavía 🍮 ¡Ten mas confianza en ti! Esta bien decir lo que quieres y necesitas mientras lo hagas con respeto y asertividad 👀"
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
    "Recuerda los limites sanos son puro amor, amor por ti y por los demás ✨
No puedes amar ni hacer feliz a nadie, mientras nos seas feliz tu. ¡Todo empieza desde la seguridad y el amor propio!"
  )

  then(QuizCompleted)
end

```

<!-- { section: "5026c104-8355-4769-9065-e6be4a606860", x: 16152, y: -48} -->

```stack
card RunStack_b8be21, "RunStack_b8be21",
  version: "1",
  uuid: "52e4db99-ef51-5941-9846-c4cda38fe572",
  code_generator: "RUN_STACK" do
  run_stack("a238e01b-0799-4e7a-8751-8a8e22ab15b2")
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

<!-- { section: "790fb7c3-7776-4ba2-ad6e-ce2db13aee70", x: 10272, y: -192} -->

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
  then(Catch_all_3)
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

<!-- { section: "35948745-b26a-4e89-be4b-de127dbfa3e1", x: 3168, y: 576} -->

**@Buhle**

Please save insights here

code block is here if you need that

<!-- { section: "10ddfc30-726b-4ec1-9880-b0c0f3f97b56", x: 3936, y: -144} -->

opt a = 0

<!-- { section: "f71771bc-5dff-4dd2-99ff-8ea609717ec6", x: 3936, y: 456} -->

opt b = 2

<!-- { section: "72c63982-e262-4342-926c-54f1ee6ac9b5", x: 3960, y: 960} -->

opt c = 1

<!-- { section: "e0d132f0-faa8-4578-a79d-a77253817d5e", x: 6264, y: -120} -->

opt a = 0

<!-- { section: "bf25cf1e-9525-46d1-8a4a-9d51acf21180", x: 6288, y: 384} -->

opt b = 2

<!-- { section: "e322852d-ba88-428e-ae7f-dc7796d4cfdb", x: 6264, y: 840} -->

opt c = 0

<!-- { section: "805ea77c-b877-4f21-89ac-c11bae23fae3", x: 7920, y: 720} -->

**@Buhle**

Please update the insights here

Also there is a code block is here if you need that

<!-- { section: "aca1a9d2-6883-4aeb-a243-a8a75de33ead", x: 8616, y: -120} -->

opt a = 0

<!-- { section: "16672b83-5d7c-443c-ab95-ed2bd7c8636b", x: 8592, y: 408} -->

opt b = 0

<!-- { section: "8ab3b3c3-26a5-4276-9071-dfe8b68f3f44", x: 8640, y: 816} -->

opt c = 2

<!-- { section: "08c4681d-bf90-4ecd-92b5-cea7e1f50113", x: 11088, y: -96} -->

opt a = 2

<!-- { section: "24291e3c-412b-49f8-8a6e-a9d96e6e3302", x: 10392, y: 744} -->

**@Buhle**

Please update the insights here

Also there is a code block is here if you need that

<!-- { section: "992f3ed4-a51e-419a-b918-ecc0b997edec", x: 11088, y: 432} -->

opt b = 2

<!-- { section: "9f993d2c-5e2a-459c-aaac-acdd61fbe101", x: 11088, y: 912} -->

opt c = 0

<!-- { section: "0afb2253-5fda-4cc8-9ffb-3cf5db26934d", x: 792, y: 360} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

**DS note:** Flow result: quiz_pm5_started (yes)

<!-- { section: "867c120e-ced5-4d22-a447-b22039956923", x: 15216, y: 240} -->

Update contact field, contact module = Quiz Post Module 5 ✅

<!-- { section: "107a7baa-1da9-4d29-b2f8-d65d1377105b", x: 16248, y: 192} -->

DS note: Flow result: quiz_pm5_completed (yes)

Eng note: Update contact.nextengagement_time

(Buhle this might be obsolete as we send the user to module 6 straight after)_

<!-- { section: "aeea27dd-b57f-417f-bbbc-c5dc933e518e", x: 15792, y: 192} -->

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

<!-- { section: "daf7c9f2-7728-481b-a16e-b5014b058c56", x: 11016, y: 552} -->

```stack
card Message10_3 do
  write_result("quiz_pm5_q4_value", "c")
  write_result("quiz_pm5_q4_score", "0")
  then(Message_11_3)
end

```

<!-- { section: "e4995cb1-be09-421d-923e-47a9d526799f", x: 888, y: 0} -->

```stack
card Message1 do
  write_result("quiz_pm5_started", "yes")
  then(Message_2)
end

```

<!-- { section: "0f6d0988-c0bf-4252-9686-4d0dec236fc7", x: 15432, y: -120} -->

```stack
card QuizCompleted do
  update_contact(quiz_post_module5_complete_: "true")
  write_result("quiz_pm5_completed", "yes")
  then(RunStack_b8be21)
end

```

<!-- { section: "16b87e09-8dc8-44ee-a17c-3061a4944277", x: 3816, y: -480} -->

```stack
card Message3_1 do
  write_result("quiz_pm5_q1_value", "a")
  write_result("quiz_pm5_q1_score", "0")
  then(Message_4_1)
end

```

<!-- { section: "6d734f34-36f5-43af-a1d6-646f46d324bb", x: 3840, y: 0} -->

```stack
card Message3_2 do
  write_result("quiz_pm5_q1_value", "b")
  write_result("quiz_pm5_q1_score", "2")
  then(Message_4_2)
end

```

<!-- { section: "b13e6d27-779c-4cda-a31c-3318c62aebeb", x: 3840, y: 528} -->

```stack
card Message3_3 do
  write_result("quiz_pm3_q1_value", "c")
  write_result("quiz_pm3_q1_score", "1")
  then(Message_4_3)
end

```

<!-- { section: "b3ab2cbe-8c45-48fb-9b70-d0ec5f0a53e4", x: 6168, y: -432} -->

```stack
card Message5_1 do
  write_result("quiz_pm5_q2_value", "a")
  write_result("quiz_pm5_q2_score", "0")
  then(Message_6_1)
end

```

<!-- { section: "8242be94-61e0-410b-80b2-44a87e23ff0b", x: 6168, y: 24} -->

```stack
card Message5_2 do
  write_result("quiz_pm5_q2_value", "b")
  write_result("quiz_pm5_q2_score", "2")
  then(Message_6_2)
end

```

<!-- { section: "826c2c69-0761-4c3e-8f84-e371f3f87ede", x: 6168, y: 480} -->

```stack
card Message5_3 do
  write_result("quiz_pm5_q2_value", "c")
  write_result("quiz_pm5_q2_score", "0")
  then(Message_6_3)
end

```

<!-- { section: "d113216d-5bf8-4b14-b272-f907075aa8c2", x: 8472, y: -432} -->

```stack
card Message7_1 do
  write_result("quiz_pm5_q3_value", "a")
  write_result("quiz_pm5_q3_score", "0")
  then(Message_8_1)
end

```

<!-- { section: "8bbbf15d-11bc-4791-a1c6-7ec3373ad192", x: 8544, y: 48} -->

```stack
card Message7_2 do
  write_result("quiz_pm5_q3_value", "b")
  write_result("quiz_pm5_q3_score", "0")
  then(Message_8_2)
end

```

<!-- { section: "30782275-8a99-4d72-9817-19782e325deb", x: 8472, y: 480} -->

```stack
card Message7_3 do
  write_result("quiz_pm5_q3_value", "c")
  write_result("quiz_pm5_q3_score", "2")
  then(Message_8_3)
end

```

<!-- { section: "ca27d7b9-40fa-4af6-af37-02a9aa3ec632", x: 10968, y: -432} -->

```stack
card Message10_1 do
  write_result("quiz_pm5_q4_value", "a")
  write_result("quiz_pm5_q4_score", "2")
  then(Message_11_1)
end

```

<!-- { section: "150a7494-873f-4fb1-bc7b-a3c02ce0cb1c", x: 11040, y: 24} -->

```stack
card Message10_2 do
  write_result("quiz_pm5_q4_value", "b")
  write_result("quiz_pm5_q4_score", "2")
  then(Message_11_2)
end

```

<!-- { section: "871007ce-547a-4e9b-9d19-bce17c6fb0d1", x: 13440, y: -360} -->

```stack
card Message12_1 do
  write_result("quiz_pm5_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "a43ebd19-cb06-4d0a-bcea-6e1284b26de9", x: 13416, y: 72} -->

```stack
card Message12_2 do
  write_result("quiz_pm5_endline", "b")
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
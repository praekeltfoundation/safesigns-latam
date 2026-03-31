<!-- { section: "9b655f6d-8bfa-47df-b065-6e16a0be976a", x: -1872, y: 72} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_3" and contact.quiz_post_module3_complete == false and
       contact.arm == "NARRATIVE" and contact.onboarding_complete == true

trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_n4")

```

<!-- { section: "5a8489c6-9acc-42b5-af45-adb447357f2d", x: -1296, y: 72} -->

```stack
card Insight_1, "Insight_1",
  version: "1",
  uuid: "f622ab2c-c560-4a81-971e-e4e43072c6aa",
  code_generator: "WRITE_RESULTS" do
  write_result("quiz_post_module3_started", "yes")
  then(Template_1)
end

```

<!-- { section: "cba701b0-fbc0-4610-aad6-d7f000cc1c3f", x: 1392, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["¡Genial!"]) do
      text(
        "Queremos ser las mejores amigas pero a veces los problemas de nuestras amigas están demasiado 🔥 y no sabemos bien cómo ayudar 🧯, o nos sacan de quicio 🙄.
¡Vamos a ver qué tipo de amiga eres!"
      )
    end

  write_result("message_2", ref_Message_2)
  then(Message_3 when ref_Message_2 == "¡Genial!")
  then(Catch_all_2)
end

```

<!-- { section: "9bc2b827-1ccb-41fe-8e10-df6b43c916a7", x: -792, y: -240} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Template_1)
end

```

<!-- { section: "ebff7235-1b65-45a5-a6ea-6d628f42b565", x: 1416, y: -936} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "9610d7fe-9baa-413e-932c-4b0a343187c0", x: 2616, y: -72} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["A", "B", "C"]) do
      text(
        "Una amiga te cuenta que tuvo una pelea fuerte con su novio😡 Ella está llorando muchísimo y te cuenta hasta el último detalle que, la verdad, ¡te deja sin palabras!

¿Cómo reaccionas?
*A.* Estás en shock y dices \"¿Cómo así? ¡No te creo!\"😮
*B.* La abrazas mientras piensas en algo que decir 🤗😶
*C.* Le dices \"Lo que pasó no es tu culpa\" 😔"
      )
    end

  then(Message3_1 when ref_Message_3 == "A")
  then(Message3_2 when ref_Message_3 == "B")
  then(Message3_3 when ref_Message_3 == "C")
  then(Catch_all_4)
end

```

<!-- { section: "ed3d269f-637c-48e6-9dd8-6dafdb445614", x: 2664, y: -984} -->

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
    "❌ Aunque sea una expresión común, \"no te creo\" puede hacer sentir a tu amiga cuestionada. Lo mejor es hacerle saber que tú estas ahí para ella y que le crees, pase lo que pase."
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
    "🤔 ¡Bien! Si ella se siente cómoda, agarrándole la mano o abrazándola puedes hacerla sentir que no está sola. También luego le puedes decir que no es su culpa lo que le hayan hecho."
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
    "✅ ¡Correcto! Es importante que ella sepa que no es responsable de lo que le hagan los demás. Si se siente cómoda también la puedes abrazar."
  )

  then(Message_5)
end

```

<!-- { section: "0b9f6748-76e3-4108-921d-9261a4a867c7", x: 5472, y: -144} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["A", "B", "C"]) do
      text(
        "Te metes en Telegram y ves que pasan el pack de una niña de tu salón. No son muy cercanas, pero se sientan juntas de vez en cuando y es buena gente. 

¿Cómo reaccionas?
*A.* Llamas a tu mejor amiga a comentar 📳
*B.* Comentas \"eso le pasa por boba y por andar de fácil\" 🙄
*C.* Te sientas al lado de ella al día siguiente a acompañarla, así no digas nada 🪑"
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
    "🤔 Entiendo la tentación de comentar las últimas novedades, pero hay que tener cuidado de no regar chisme. Imagínate cómo se está sintiendo esa chica y el chisme solo la va a poner peor 😦 No sabemos los detalles de la situación, tal vez confió en alguien que quería o podría ser hasta una imagen falsa."
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
    "❌ Hay que tener cuidado de no caer en chismes. Imagínate cómo se esta sintiendo esa chica y el chisme solo va a complicar las cosas😦. No sabemos los detalles de la situación, tal vez confió en alguien que quería o podría ser hasta una imágen falsa."
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
    "✅ ¡Muy bien! Es bueno que ella sepa que las amigas no van a abandonarla ni juzgarla. No sabemos los detalles de la situación, tal vez confío en alguien que quería o podría ser hasta una imágen falsa."
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

<!-- { section: "c36f68b1-21fc-4c1c-9aa0-07414c350a8d", x: 7680, y: -168} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["A", "B", "C"]) do
      text(
        "Una amiga te llama a contarte que metió la pata🫣. Estaba teniendo una videollamda sexy con el novio y él la grabo sin que ella se diera cuenta. ¡Ahora está preocupada de qué pueda hacer él con eso!

¿Qué le dices?
*A.* Vamos a buscar ayuda para que lo borre 🔍
*B.* ¡Yo siempre supe que era un raro! 😫
*C.* Quién te manda a hacer esas cosas 🫠"
      )
    end

  then(Message7_3 when ref_Message_7 == "A")
  then(Message7_2 when ref_Message_7 == "B")
  then(Message7_1 when ref_Message_7 == "C")
  then(Catch_all_6)
end

```

<!-- { section: "25338aa2-9d8e-42eb-abc9-62ca063a1b8d", x: 7656, y: -1128} -->

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
    "✅ ¡Correcto! Él rompió su confianza grabándola sin permiso. En vez de juzgarla, mejor ayudarla a buscar una solución."
  )

  then(Message_9)
end

```

<!-- { section: "1f73c164-062e-4f44-a3f2-6d4b6b23dd91", x: 9096, y: 48} -->

```stack
card Message_8_2, "Message_8_2",
  version: "1",
  uuid: "a6f29f91-5f48-5dc4-80c4-063a12073e9e",
  code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Así no te guste su novio, es mejor no juzgarla, especialmente cuando ella está sientiéndose mal. Hay mejores maneras y momentos de comunicarle tus preocupaciones acerca de su pareja. Mejor, ayudarla a buscar una solución."
  )

  then(Message_9)
end

```

<!-- { section: "0b14bf8a-0d29-41d7-8bf9-5ac563077268", x: 9096, y: 600} -->

```stack
card Message_8_3, "Message_8_3",
  version: "1",
  uuid: "0f6800cf-6cc5-5057-b513-b93cecfe9ce3",
  code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Todos tenemos diferentes gustos e, inclusive cuando cometemos errores, no vale la pena juzgar. Él rompió su confianza grabándola sin permiso, mejor ayudarla a buscar una solución."
  )

  then(Message_9)
end

```

<!-- { section: "e424813f-5bd3-4da8-994a-4d9435dbf7cf", x: 10392, y: -120} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["¡Súper bien! 👍", "Puedo mejorar 🙃"]) do
      text("¿Cómo te fue en el mini test? 👀")
    end

  then(Message9_1 when ref_Message_9 == "¡Súper bien! 👍")
  then(Message9_2 when ref_Message_9 == "Puedo mejorar 🙃")
  then(Catch_all_8)
end

```

<!-- { section: "f1253b20-2c95-468f-a185-77e84723a304", x: 10368, y: -1056} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_9)
end

```

<!-- { section: "8583814f-6a96-4d15-af59-83a1e94deffc", x: 11664, y: -264} -->

```stack
card Message_10_1, "Message_10_1",
  version: "1",
  uuid: "58278096-b795-5536-b01b-0189dc2a87c9",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Increíble, eres una súper amiga. Sigue mostrándole al mundo cómo somos más fuertes juntas 💪🏼"
  )

  then(Message_11)
end

```

<!-- { section: "cd756325-d6bb-417a-8e48-1d606be800ee", x: 11688, y: 264} -->

```stack
card Message_10_2, "Message_10_2",
  version: "1",
  uuid: "865b0227-b4c1-57c3-bd90-9fbc7795d51a",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Todavía hay un poco de trabajo por hacer para convertirte en el \"hombro donde llorar\" de tus amigas 🙌"
  )

  then(Message_11)
end

```

<!-- { section: "478f995c-d34b-47b9-8cda-b49387b3ed01", x: 12408, y: -48} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "TEXT_MESSAGE" do
  text("*Recuerda.* Cuando veas a alguien en problemas, lo importante es cumplir con los tres NO:
🚫 No juzgar ☝🏼
🚫 No cuestionar ⁉️
🚫 No chismear 🙊
")

  then(QuizComplete)
end

```

<!-- { section: "f6e0106a-15d2-4fd3-b1d5-23fad598f70c", x: 14472, y: -24} -->

```stack
card RunStack_0f3d57, "RunStack_0f3d57",
  version: "1",
  uuid: "7a995036-825f-5298-9a48-f7f6d0ec7326",
  code_generator: "RUN_STACK" do
  run_stack("ac56ce15-0e35-4f38-9325-570bca675a72")
end

```

<!-- { section: "453e603d-e17a-4510-904b-41bc1b970ee2", x: -792, y: 72} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "381570c7-d355-46f9-88ff-a8608c0f1dbc",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_narrative_quiz_postmod3", "es", [],
      buttons: ["¡Cuéntame más!"]
    )

  then(Message1 when ref_Template_1.index == 0)
  then(Catch_all_1)
end

```

<!-- { section: "4d11a993-ed03-408d-91f5-77dc65da13cf", x: 3168, y: 744} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "10ddfc30-726b-4ec1-9880-b0c0f3f97b56", x: 3936, y: -144} -->

opt a = 0

<!-- { section: "f71771bc-5dff-4dd2-99ff-8ea609717ec6", x: 3936, y: 456} -->

opt b = 1

<!-- { section: "72c63982-e262-4342-926c-54f1ee6ac9b5", x: 3960, y: 960} -->

opt c = 2

<!-- { section: "282fcbe1-7c40-4fd2-99a4-c89978ab91a5", x: 5664, y: 744} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "e0d132f0-faa8-4578-a79d-a77253817d5e", x: 6264, y: -120} -->

opt a = 1

<!-- { section: "bf25cf1e-9525-46d1-8a4a-9d51acf21180", x: 6288, y: 384} -->

opt b = 0

<!-- { section: "e322852d-ba88-428e-ae7f-dc7796d4cfdb", x: 6264, y: 840} -->

opt c = 2

<!-- { section: "e8e01be9-b923-4bf0-9812-12bea2510ea2", x: 8112, y: 792} -->

**@buhle**

This is the one where I am waiting on amounts that are missing

Please save the insights here

code block is here if you need that

<!-- { section: "aca1a9d2-6883-4aeb-a243-a8a75de33ead", x: 8616, y: -120} -->

opt a =

<!-- { section: "16672b83-5d7c-443c-ab95-ed2bd7c8636b", x: 8592, y: 408} -->

opt b =

<!-- { section: "8ab3b3c3-26a5-4276-9071-dfe8b68f3f44", x: 8640, y: 816} -->

opt c =

<!-- { section: "73797d95-1a3e-4a1d-934b-a3af283a162b", x: 10944, y: 432} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "ad56fafa-2f84-49ab-a1b2-bb656ac7126d", x: 13536, y: 312} -->

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

<!-- { section: "a0e6805e-c0de-4506-85bb-1b5c1ce250a0", x: 14064, y: 240} -->

**DS note:** Flow result: quiz_pm3_completed (yes)

**Eng note:** Update contact.next*engagement_time*

([Buhle](https://www.figma.com/files/1174087528366850825/user/1364872052852176049) this might be obsolete as we send the user to module 4 straight after)_

<!-- { section: "cc41832f-9bef-43ba-a112-6255854c4e60", x: 7704, y: 720} -->

Emojis missing here

<!-- { section: "ca075569-4258-4ff2-a2ba-95976b312d3c", x: 8112, y: 984} -->

```stack
card CodeBlock_e12bc0 do
  text("some text")
end

```

<!-- { section: "8c2fda1e-bedb-418d-8acd-252d83ebe807", x: 552, y: -72} -->

```stack
card Message1 do
  write_result("template_1", "¡Cuéntame más!")
  then(Message_2)
end

```

<!-- { section: "0647cd73-7af9-4d18-b096-1a02ee664a80", x: 13560, y: -120} -->

```stack
card QuizComplete do
  update_contact(quiz_post_module3_complete: "true")
  write_result("quiz_pm3_completed", "yes")
  then(RunStack_0f3d57)
end

```

<!-- { section: "1b347b24-5b89-4aba-9d75-5b78aeee7bb0", x: 3816, y: -552} -->

```stack
card Message3_1 do
  write_result("quiz_pm3_q1_value", "a")
  write_result("quiz_pm3_q1_score", "0")
  then(Message_4_1)
end

```

<!-- { section: "0466dab8-cbcc-4584-a576-03b702660e09", x: 3840, y: -24} -->

```stack
card Message3_2 do
  write_result("quiz_pm3_q1_value", "b")
  write_result("quiz_pm3_q1_score", "1")
  then(Message_4_2)
end

```

<!-- { section: "c049db5f-0b44-4cbd-a24a-9bb0256552d8", x: 3816, y: 552} -->

```stack
card Message3_3 do
  write_result("quiz_pm3_q1_value", "c")
  write_result("quiz_pm3_q1_score", "2")
  then(Message_4_3)
end

```

<!-- { section: "18169ffa-480d-4473-ac28-dc5a81ebf222", x: 6168, y: -480} -->

```stack
card Message5_1 do
  write_result("quiz_pm3_q2_value", "a")
  write_result("quiz_pm3_q2_score", "1")
  then(Message_6_1)
end

```

<!-- { section: "612331a2-f222-47c5-a394-bc8d61aaed8c", x: 6192, y: -24} -->

```stack
card Message5_2 do
  write_result("quiz_pm3_q2_value", "b")
  write_result("quiz_pm3_q2_score", "0")
  then(Message_6_2)
end

```

<!-- { section: "5b62106d-33e6-4f6b-b7c8-d7b37e4ae226", x: 6192, y: 480} -->

```stack
card Message5_3 do
  write_result("quiz_pm3_q2_value", "c")
  write_result("quiz_pm3_q2_score", "2")
  then(Message_6_3)
end

```

<!-- { section: "be9ec142-a92e-4799-bd7a-7115b6f3ae69", x: 8472, y: -552} -->

```stack
card Message7_3 do
  write_result("quiz_pm3_q3_value", "a")
  write_result("quiz_pm3_q3_score", "1")
  then(Message_8_1)
end

```

<!-- { section: "039f8e5a-95d8-40dd-aa80-7b97deaad5d6", x: 8472, y: 24} -->

```stack
card Message7_2 do
  write_result("quiz_pm3_q3_value", "b")
  write_result("quiz_pm3_q3_score", "1")
  then(Message_8_2)
end

```

<!-- { section: "b3869352-c45a-409b-9c62-addc440fb7b6", x: 8472, y: 504} -->

```stack
card Message7_1 do
  write_result("quiz_pm3_q3_value", "c")
  write_result("quiz_pm3_q3_score", "1")
  then(Message_8_3)
end

```

<!-- { section: "44683056-7f01-4efd-a589-61e0247a588b", x: 10968, y: -384} -->

```stack
card Message9_1 do
  write_result("quiz_pm3_endline", "a")
  then(Message_10_1)
end

```

<!-- { section: "78fac441-28ac-4159-92a3-eca2b82b6308", x: 11016, y: 72} -->

```stack
card Message9_2 do
  write_result("quiz_pm3_endline", "b")
  then(Message_10_2)
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
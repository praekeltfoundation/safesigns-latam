<!-- { section: "a526b6e4-d1ad-491a-886e-da87441aa2be", x: -1656, y: -72} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.quiz_post_module3_complete == false and contact.contact_module == "MODULE_3" and
       contact.arm == "GAMIFIED" and contact.onboarding_complete == true

trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "test_g4")

```

<!-- { section: "3208029f-a934-41d7-b737-63376d465adc", x: -1128, y: -72} -->

```stack
card Insight_1, "Insight_1",
  version: "1",
  uuid: "c561979a-a6d5-4abf-b25e-97c866eb5682",
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

<!-- { section: "2551e907-1dd6-447c-8122-6cec45a77ba9", x: -528, y: -408} -->

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

<!-- { section: "7b4d730e-338b-476c-aa4f-8a5d681fc043", x: 3024, y: -72} -->

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
    "❌ Aunque sea una expresión común, \"no te creo\" puede hacer sentir a tu amiga cuestionada. Lo mejor, es hacerle saber que tú estas ahí para ella y que le crees, pase lo que pase."
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

<!-- { section: "89e3a86d-1311-4e36-b358-6cba4d58b78f", x: 5400, y: -96} -->

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
    "🤔- Entiendo la tentación de comentar las últimas novedades, pero hay que tener cuidado de no regar chisme. Imagínate cómo se está sintiendo esa chica, y el chisme sólo la va a poner peor 😦 No sabemos los detalles de la situación, tal vez confió en alguien que quería o podría ser hasta una imagen falsa!"
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
    "❌  Hay que tener cuidado de no caer en chisme. Imagínate cómo se esta sintiendo esa chica, y el chisme sólo va a complicar las cosas😦. No sabemos los detalles de la situación, tal vez confió en alguien que quería o podría ser hasta una imágen falsa!"
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
    "✅ - ¡Muy bien! Es bueno que ella sepa que las amigas no van a abandonarla ni juzgarla. No sabemos los detalles de la situación, tal vez confío en alguien que quería o podría ser hasta una imágen falsa!"
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

<!-- { section: "0bd6b88f-d225-4982-85e8-b0127b1788d8", x: 7704, y: 144} -->

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

  then(Message7_1 when ref_Message_7 == "A")
  then(Message7_2 when ref_Message_7 == "B")
  then(Message7_3 when ref_Message_7 == "C")
  then(Catch_all_6)
end

```

<!-- { section: "bb0269f1-066d-4ff0-aaa4-81aeecb193f7", x: 7728, y: -1152} -->

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

<!-- { section: "f87db9a0-001a-451f-9d89-a0b7be344f4e", x: 9096, y: 144} -->

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

<!-- { section: "c6eb1bdc-486a-43a8-b538-69461a061aa2", x: 9096, y: 600} -->

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

<!-- { section: "022e6bf5-c43e-451c-adfd-19a50d35b3ea", x: 12408, y: -96} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "TEXT_MESSAGE" do
  text("*Recuerda.* Cuando veas a alguien en problemas, lo importante es cumplir con los tres NO:
🚫 No juzgar ☝🏼
🚫 No cuestionar ⁉️
🚫 No chismear 🙊")

  then(QuizCompleted)
end

```

<!-- { section: "813adf80-eefe-42cc-9aba-585166959996", x: 13848, y: -48} -->

```stack
card RunStack_b8be21, "RunStack_b8be21",
  version: "1",
  uuid: "52e4db99-ef51-5941-9846-c4cda38fe572",
  code_generator: "RUN_STACK" do
  run_stack("8ff13f1a-34a1-4542-800b-456756cb11e0")
end

```

<!-- { section: "c6aa2ba8-44bc-4db6-8034-91dd9d544f0f", x: -528, y: -72} -->

```stack
card Template_1, "Template_1",
  version: "1",
  uuid: "3d17d45e-8e19-4bb6-a1a4-ab7c3e16bbb7",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  ref_Template_1 =
    send_message_template("spanish_gamified_quiz_postmod3", "es", [], buttons: ["¡Cuentame más!"])

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

Please save the insights here

code block is here if you need that

<!-- { section: "aca1a9d2-6883-4aeb-a243-a8a75de33ead", x: 8616, y: -120} -->

opt a =

<!-- { section: "16672b83-5d7c-443c-ab95-ed2bd7c8636b", x: 8592, y: 408} -->

opt b =

<!-- { section: "2f45fdb5-a81f-4cb4-97b1-3b94364ecdb5", x: 8640, y: 864} -->

opt c =

<!-- { section: "07e9c2d6-2b49-4906-beb6-b66ec07bb0c9", x: 7464, y: 600} -->

emojis do not show up

<!-- { section: "f35a11c3-6201-4a86-b266-5ccef1561774", x: 456, y: 360} -->

**@Buhle,**

Not sure which was right for the DS note so have both code and save insight here, dlt the one you dont need please.

DS note: Flow result: quiz_pm3_started (yes)

<!-- { section: "73797d95-1a3e-4a1d-934b-a3af283a162b", x: 10944, y: 432} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "e9eb8a92-d329-44c3-97b9-c14f9d6f9d5a", x: 12840, y: 552} -->

~~Update contact field, contact module =~~~~~~~~~~~~~~~~~~~~~~~~~~~~\
~~~~~~~~~~~~~~~~~~~~~~~~~~~~Quiz Post module 3 ✅~~

<!-- { section: "2b2f331e-d514-435b-9f78-d7c8a7c2ce74", x: 13416, y: 528} -->

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

<!-- { section: "fe30df7e-a39c-42f1-98fe-019abb2dd2cd", x: 14040, y: 240} -->

**DS note:** Flow result: quiz_pm3_completed (yes)

**Eng note:** Update contact.next*engagement_time*

([Buhle](https://www.figma.com/files/1174087528366850825/user/1364872052852176049) this might be obsolete as we send the user to module 4 straight after)_

<!-- { section: "1dc71cf8-b3dd-4bbf-ace3-a3c524fa15ca", x: 6384, y: 408} -->

I think there is a typo here

<!-- { section: "2b19938f-6f92-42c9-ba8d-6dc6fa65da3b", x: 5640, y: 984} -->

```stack
card CodeBlock_804d50 do
  text("some text")
end

```

<!-- { section: "ca075569-4258-4ff2-a2ba-95976b312d3c", x: 8112, y: 984} -->

```stack
card CodeBlock_e12bc0 do
  text("some text")
end

```

<!-- { section: "a9428d3b-d248-424c-a71e-35bcb750b595", x: 11112, y: -288} -->

```stack
card Message9_1 do
  write_result("quiz_pm3_endline", "a")
  then(Message_10_1)
end

```

<!-- { section: "79d4cf5e-31c3-4ba7-8809-849589ee3827", x: 432, y: -96} -->

```stack
card Message1 do
  write_result("template1", "¡Cuéntame más!")
  then(Message_2)
end

```

<!-- { section: "9456d81c-dca2-4002-b195-98e4921836a1", x: 13008, y: -120} -->

```stack
card QuizCompleted do
  update_contact(quiz_post_module3_complete: "true")
  write_result("quiz_pm3_completed", "yes")
  then(RunStack_b8be21)
end

```

<!-- { section: "053d7c79-34f6-4412-a29c-a4c42f2c1115", x: 3792, y: -504} -->

```stack
card Message3_1 do
  write_result("quiz_pm3_q1_value", "a")
  write_result("quiz_pm3_q1_score", "0")
  then(Message_4_1)
end

```

<!-- { section: "ad2ff397-5b5b-417c-a676-645549a70720", x: 3816, y: 24} -->

```stack
card Message3_2 do
  write_result("quiz_pm3_q1_value", "b")
  write_result("quiz_pm3_q1_score", "1")
  then(Message_4_2)
end

```

<!-- { section: "dc869d47-d780-406b-8cd3-c200b8d25080", x: 3864, y: 600} -->

```stack
card Message3_3 do
  write_result("quiz_pm3_q1_value", "c")
  write_result("quiz_pm3_q1_score", "2")
  then(Message_4_3)
end

```

<!-- { section: "0bc76e47-cea9-4e70-88f1-7c2c1d787230", x: 6144, y: -432} -->

```stack
card Message5_1 do
  write_result("quiz_pm3_q2_value", "a")
  write_result("quiz_pm3_q2_score", "0")
  then(Message_6_1)
end

```

<!-- { section: "cad6f149-f02a-464b-ad8a-5de502c857e3", x: 6192, y: 48} -->

```stack
card Message5_2 do
  write_result("quiz_pm3_q2_value", "b")
  write_result("quiz_pm3_q2_score", "1")
  then(Message_6_2)
end

```

<!-- { section: "3d4aa9d1-958b-4216-97dd-30de75e47f8a", x: 6216, y: 528} -->

```stack
card Message5_3 do
  write_result("quiz_pm3_q2_value", "c")
  write_result("quiz_pm3_q2_score", "2")
  then(Message_6_3)
end

```

<!-- { section: "0aee106c-0333-4297-9a13-157491b5029f", x: 8496, y: -456} -->

```stack
card Message7_1 do
  write_result("quiz_pm3_q3_value", "a")
  write_result("quiz_pm3_q3_score", "0")
  then(Message_8_1)
end

```

<!-- { section: "b33fcb89-8e13-4270-8936-662c49183b11", x: 8496, y: 72} -->

```stack
card Message7_2 do
  write_result("quiz_pm3_q3_value", "b")
  write_result("quiz_pm3_q3_score", "1")
  then(Message_8_2)
end

```

<!-- { section: "d1646d9c-9b19-4fa2-9dc2-ece428e5016f", x: 8496, y: 504} -->

```stack
card Message7_3 do
  write_result("quiz_pm3_q3_value", "c")
  write_result("quiz_pm3_q3_score", "2")
  then(Message_8_3)
end

```

<!-- { section: "305408a9-392d-4750-a74c-0c09e6e8c437", x: 11112, y: 48} -->

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
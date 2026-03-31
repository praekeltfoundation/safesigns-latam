<!-- { section: "8dec8c7d-cb54-4415-bdee-0d167f91980a", x: -3648, y: 0} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_only_phrase(event.message.text.body, "test_n6_2") or
       (contact.arm == "NARRATIVE" and contact.contact_module == "MODULE_5" and
          contact.quiz_post_module5 == true and contact.onboarding_complete == true)

```

<!-- { section: "65964135-2766-4c6a-acdb-5527ec39d211", x: -2064, y: 0} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Hola!* 👋
Ahora sí, bienvenida al sexto y último episodio de la historia de Pilar. ¡Qué giro dio la historia y qué rápido ha pasado el tiempo!"
  )

  then(Insight_1)
end

```

<!-- { section: "0017fb97-29a3-4892-b59b-cc45a2f5cc8e", x: -792, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "¡Súper! 👍"]) do
      text(
        "El reto de ayer era conseguir una pareja de novios o amigos famosa que fuera buen ejemplo de los temas que conversamos ¿Cómo te fue?"
      )
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "¡Súper! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "0b994ec6-1f12-4fbe-acb3-b6ee8cb64baa", x: -792, y: -264} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "91dda502-2678-4a44-96f4-6324edfe7119", x: 576, y: 0} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text("No te preocupes, hoy podrás ponerte al día.")
  then(Message_4)
end

```

<!-- { section: "fd4259bc-de66-4530-a2df-3597cabd012d", x: 576, y: 384} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Increíble! Hay ejemplos de buena y mala comunicación en todos lados. ¡Ahora, los sabes identificar y poner tus límites, decir sí/no o discutir, pero de manera sana!"
  )

  then(Message_4)
end

```

<!-- { section: "44f21be7-054e-4a4b-93b9-0e747c55e84c", x: 1152, y: 192} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "TEXT_MESSAGE" do
  text(
    "En este episodio, nos enteraremos qué pasó, luego de que Mari confesara que había sido ella quien había compartido la foto de Pilar. ¡Acompáñame a saber qué hicieron y cómo elaboraron un plan de seguridad!"
  )

  then(Message_5)
end

```

<!-- { section: "70180cc5-2adf-4d4b-83a7-eeeaebdd8203", x: 5808, y: 744} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10_2)
end

```

<!-- { section: "592936fe-82a7-468a-ad7d-5adc48512218", x: 1656, y: 192} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Como siempre, si hay algo que te hace sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!"
  )

  then(Message_6)
end

```

<!-- { section: "2d3508ed-b949-44b9-a739-7d32ee37b2d3", x: 2064, y: 192} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "MEDIA_AUDIO" do
  audio("af2a5afd-c201-4aa4-aeda-14c19b23ed9d-M6_P1_A1.mp3")
  then(Message_7)
end

```

<!-- { section: "6bece292-2fce-4cbc-8710-2e34e4458826", x: 4512, y: -744} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_9)
end

```

<!-- { section: "f5a7cda2-d5ed-4382-9e6d-d30cbc33b3d4", x: 2520, y: 192} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Ya escuché el audio"]) do
      text(
        "Ahora sí, escuchemos el audio. ¿Lista? Cuando termine el audio, pulsa el botón *Ya escuché el audio*"
      )
    end

  write_result("message_7", ref_Message_7)
  then(Message_8 when ref_Message_7 == "Ya escuché el audio")
  then(Catch_all_4)
end

```

<!-- { section: "caefff04-75fe-498f-8d9a-b644013a2da9", x: 2520, y: -552} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_7)
end

```

<!-- { section: "b416741c-c852-47e2-8bca-245019d2b881", x: 3072, y: 168} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "QUESTION" do
  ref_Message_8 =
    ask(
      "Imagina que el novio de una amiga tuya le pidió a ella que le envíe una foto íntima como prueba de amor.

Ella se la envió pero, ahora, la foto anda circulando por todo el salón.

*¿Qué harías al respecto?* 🤔"
    )

  then(Branch_7828f1)
end

```

<!-- { section: "68d918c1-ed33-4998-a973-5fee84bb637b", x: 4488, y: 168} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Muy empoderada", "Muy intensa", "No estoy segura 🤷"]) do
      text(
        "En este episodio, escuchamos una simulación sobre cómo Pilar le hubiera podido responder a Camilo cuando él le pidió la foto.
*Camilo:* \"¿Es que no confías en mí? ¿No me quieres? Además hasta cuándo me vas a tener esperando\"
*Pilar:* \"Si te quiero y te creo, pero de verdad no me siento cómoda compartiendo fotos como estas, y si tú de verdad me quieres, tienes que respetar mi decisión\".  

¿Qué te pareció su repuesta? 🤔"
      )
    end

  then(Message9_1 when ref_Message_9 == "Muy empoderada")
  then(Message9_2 when ref_Message_9 == "Muy intensa")
  then(Message9_3 when ref_Message_9 == "No estoy segura 🤷")
  then(Catch_all_3)
end

```

<!-- { section: "21b5a501-9a57-4eb8-b862-e6de295f405a", x: 5880, y: -672} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10_1)
end

```

<!-- { section: "b442982c-09fc-4f44-9d7b-11b39526d298", x: 9624, y: -624} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_13)
end

```

<!-- { section: "a09f2105-7284-4595-8137-689b3d864b36", x: 10536, y: -576} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "275602d1-13ec-4644-9ab9-4cd39b62a75d", x: 6600, y: 192} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11 =
    buttons(["Llamar a alguien📞", "No sé qué haría🤷‍♀️", "Trato de soportar 🤔"]) do
      text(
        "Pilar nos contó que hubo fiestas en las que se sintió incómoda porque los amigos de Camilo metían drogas. Pero como él era quien la llevaba, no sabía cómo irse de esos lugares. 

¿Qué harías tú si estuvieras en la situación de Pilar? 🤔"
      )
    end

  then(Message11_1 when ref_Message_11 == "Llamar a alguien📞")
  then(Message11_2 when ref_Message_11 == "No sé qué haría🤷‍♀️")
  then(Message11_3 when ref_Message_11 == "Trato de soportar 🤔")
  then(Catch_all_8)
end

```

<!-- { section: "3a0ac982-77da-4b5a-b3eb-52dc1d067402", x: 6552, y: -648} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_11)
end

```

<!-- { section: "d3f494a1-d308-4380-baf2-2e964574e769", x: 8160, y: -168} -->

```stack
card Message_12_1, "Message_12_1",
  version: "1",
  uuid: "b3faf013-4802-5596-99ea-9df4b6c14c5b",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_1 =
    buttons(["Siguiente audio"]) do
      text(
        "Llamar a alguien de confianza para que vaya y te recoja es una excelente forma de tener un plan B en una situación incómoda. Siempre es bueno contar con un apoyo para salir de esos lugares y asegurarte de que estás a salvo."
      )
    end

  write_result("message_12", ref_Message_12_1)
  then(Message_13_1 when ref_Message_12_1 == "Siguiente audio")
  then(Catch_all_9)
end

```

<!-- { section: "39fde91c-488f-439e-9843-0ab1229adc56", x: 8136, y: 552} -->

```stack
card Message_12_2, "Message_12_2",
  version: "1",
  uuid: "19e8e572-ef79-5524-bebc-52b7c1aa75ab",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_2 =
    buttons(["Siguiente audio"]) do
      text(
        "Recuerda que siempre hay algo que puedes hacer. Lo mejor es que tengas un plan B para actuar de acuerdo con tus valores y bienestar. Considera llamar a alguien de confianza para que te recoja si necesitas ayuda para salir de la fiesta."
      )
    end

  write_result("message_12", ref_Message_12_2)
  then(Message_13_1 when ref_Message_12_2 == "Siguiente audio")
  then(Catch_all_10)
end

```

<!-- { section: "3f1f4ee9-eabd-4d91-9982-80a84d16813b", x: 8160, y: 1392} -->

```stack
card Message_12_3, "Message_12_3",
  version: "1",
  uuid: "4d13260a-8096-5d40-9e38-9980c7227752",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_3 =
    buttons(["Siguiente audio"]) do
      text(
        "No tienes que soportar una situación que te hace sentir mal. Siempre hay algo que puedes hacer. Lo mejor es que tengas un plan B para actuar de acuerdo con tus valores. Considera llamar a alguien de confianza para que te recoja si necesitas ayuda para salir de la fiesta."
      )
    end

  write_result("message_12", ref_Message_12_3)
  then(Message_13_1 when ref_Message_12_3 == "Siguiente audio")
  then(Catch_all_11)
end

```

<!-- { section: "a821aa83-b563-489f-af12-f68eef6ec12e", x: 7872, y: -672} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12_1)
end

```

<!-- { section: "634b7ac8-4707-4d8e-b229-5108b2b0162a", x: 8112, y: 240} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12_2)
end

```

<!-- { section: "d4f4f24f-1ecf-4f9c-89e3-41d994eaf315", x: 8064, y: 984} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12_3)
end

```

<!-- { section: "fcd6eab2-417f-49fe-9308-2360602fd618", x: 12168, y: 720} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["¡Genial! 💸", "Tiene sus riesgos ⚠️", "¡Jamás! ❌"]) do
      text(
        "Ahora imagina que estás con tus amigas y una les cuenta que su novio le ha propuesto que ambos envíen fotos íntimas para OnlyFans. ¡Ella les dice que el pago es MUY bueno! ¿Qué crees que pensarían *tus amigas* al respecto?"
      )
    end

  then(Message16_1 when ref_Message_16 == "¡Genial! 💸")
  then(Message16_2 when ref_Message_16 == "Tiene sus riesgos ⚠️")
  then(Message16_3 when ref_Message_16 == "¡Jamás! ❌")
  then(Catch_all_12)
end

```

<!-- { section: "06682bcf-d44a-4201-b4b7-3b80f30655a7", x: 12168, y: -216} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16)
end

```

<!-- { section: "b3df70a8-1872-4fbf-b726-a50ab87e2ba3", x: 13440, y: 288} -->

```stack
card Message_17_1, "Message_17_1",
  version: "1",
  uuid: "5277b1d8-b73e-5457-b6fc-a3e93bef9c08",
  code_generator: "TEXT_MESSAGE" do
  text(
    "El dinero puede ser tentador, pero también hay que considerar cómo puede afectar la vida a largo plazo. Si oyes algo así, recuérdale a tus amigas que, a veces, las oportunidades que parecen \"buenas\" pueden tener riesgos ocultos. Es importante mencionarles que hay que pensar bien en todas las consecuencias antes de decidir, ya que esto podría afectar su privacidad y bienestar en el futuro."
  )

  then(Message_18)
end

```

<!-- { section: "90de4689-f33e-44f4-8dbf-626fbd51d269", x: 13464, y: 864} -->

```stack
card Message_17_2, "Message_17_2",
  version: "1",
  uuid: "983efb4d-903a-5096-8c7a-e5384646d97a",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Es importante reconocer que hay riesgos y consecuencias. Si oyes algo así, recuérdale a tus amigas que, a veces, las oportunidades que parecen \"buenas\" pueden tener riesgos ocultos. Es importante mencionarles que hay que pensar bien en todas las consecuencias antes de decidir, ya que esto podría afectar su privacidad y bienestar en el futuro."
  )

  then(Message_18)
end

```

<!-- { section: "c0173ff7-fb87-4b03-a8c5-cd7be365515a", x: 13464, y: 1416} -->

```stack
card Message_17_3, "Message_17_3",
  version: "1",
  uuid: "ec2f9663-7fe1-516c-b8cd-1d916cb61c04",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Defender tu privacidad y bienestar es fundamental. Si oyes que tus amigas lo están pensando, recuérdales que, a veces, las oportunidades que parecen \"buenas\" pueden tener riesgos ocultos. Es importante mencionarles que hay que pensar bien en todas las consecuencias antes de decidir, ya que esto podría afectar su privacidad y bienestar en el futuro."
  )

  then(Message_18)
end

```

<!-- { section: "9022051d-fa83-4d75-8326-ba22989eccbd", x: 13968, y: 840} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Fotos íntimas📸🔞", "Celos excesivos😠👁️", "Responder rápido⚡📱"]) do
      text(
        "Es buen hábito tener un Plan B para toda situación. Piensa en un plan que podrías hacer si tu pareja u otra persona te pide algo que tú no quieres hacer ¿En qué te quieres enfocar?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Fotos íntimas📸🔞")
  then(Message18_2 when ref_Message_18 == "Celos excesivos😠👁️")
  then(Message18_3 when ref_Message_18 == "Responder rápido⚡📱")
  then(Catch_all_13)
end

```

<!-- { section: "e7e38417-b6bc-4256-8381-26ba7684fbfc", x: 13968, y: -168} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_18)
end

```

<!-- { section: "379fdc52-003f-4d93-ba86-b038104a696c", x: 15168, y: 960} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "QUESTION" do
  ref_Message_19 =
    ask(
      "Antes de irnos, ¡Es hora de pensar en tu plan! Si estás en una situación incómoda, ¿sabes que plan B puedes activar para llegar a casa a salvo? Piensa en todo lo que necesitas tener para llamar a alguien o encontrar tu camino...Describe los pasos que incluiría tu Plan B 📝 Puedes responder *en texto o nota de voz*"
    )

  then(Branch_6b651f)
end

```

<!-- { section: "f9384eea-4518-4953-86a3-948311600434", x: 16584, y: 960} -->

```stack
card Message_20, "Message_20",
  version: "1",
  uuid: "7265f9d6-d11c-5cf7-80f8-25520346adbd",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "\"Muy bien! Has escuchado el episodio 6 de la historia de Pilar 🥳

Son temas complejos, por ello para ayudarte a navegarlos, te dejo unos stickers buenísimos sobre este tema y que puedes usar para responder si llegas a vivir algo similar\""
      )
    end

  write_result("message_20", ref_Message_20)
  then(Message_21_sticker_1 when ref_Message_20 == "¡Manda mis stickers!")
  then(Catch_all_14)
end

```

<!-- { section: "e5dfcd65-b31b-492b-9179-e1d31f5554bf", x: 16584, y: 648} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "29fd27f6-47f0-5aec-8054-b4d312e8fcca",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_20)
end

```

<!-- { section: "520736fc-37ca-4559-8734-7e5f44ad91f1", x: 17088, y: 960} -->

```stack
card Message_21_sticker_1, "Message_21_sticker_1",
  version: "1",
  uuid: "7bcad0af-edec-5046-9d8a-298767885d4b",
  code_generator: "MEDIA_IMAGE" do
  image("d9139521-35bc-4c41-b1aa-83f0ab487d53-Módulo6_Abrilosojos.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "007dfdc2-0844-46e0-852f-0c360af47a11", x: 19392, y: 840} -->

```stack
card Mesage_22, "Mesage_22",
  version: "1",
  uuid: "8be268a4-0770-55a7-b5db-2f2ea6057497",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Mesage_22 =
    buttons(["Meditación🧘‍♀️🧘", "Hablar con alguien👥", "Escribir o respirar"]) do
      text(
        "Hoy es nuestro último día 😢. Pero no me puedo ir sin dejarte un reto que quiero que hagas todos los dias: *¡Cuidarte mucho a ti misma!* Quiero que pienses qué harás cuando no te sientas bien. ¿En qué te quieres enfocar?"
      )
    end

  then(Message22_1 when ref_Mesage_22 == "Meditación🧘‍♀️🧘")
  then(Message22_2 when ref_Mesage_22 == "Hablar con alguien👥")
  then(Message22_3 when ref_Mesage_22 == "Escribir o respirar")
  then(Catch_all_17)
end

```

<!-- { section: "4ccf14c8-d546-4a16-8ef3-6d22a7b90278", x: 19848, y: 72} -->

```stack
card Catch_all_17, "Catch_all_17",
  version: "1",
  uuid: "209ee976-ac39-5434-95b8-eaa8c2de1f85",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Mesage_22)
end

```

<!-- { section: "76b9da8c-773f-47ad-8814-761c64cb0252", x: 20976, y: 864} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Me parece genial, piensa en cuándo y cómo puedes hacer esta actividad como parte de tu rutina diaria para que no se te olvide."
  )

  then(Safe_Guarding_1)
end

```

<!-- { section: "9e7abfbb-b5b1-49e8-9544-d69659b24d8a", x: 22512, y: 864} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["¡Chao LiA! 🌸"]) do
      text(
        "Ok amiga, ¡me gustó mucho conocerte y haber interactuado contigo todos estos días! Espero que te haya servido mucho todo lo que aprendiste y que no olvides lo poderosa que eres💪"
      )
    end

  then(Profile_cbf172 when ref_Message_24 == "¡Chao LiA! 🌸")
  then(Catch_all_18)
end

```

<!-- { section: "8a3d1f6d-442e-461c-bef5-7cb0d73c5137", x: 24408, y: 864} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "TEXT_MESSAGE" do
  text("¡Chao, amiga!  👋🌟")
end

```

<!-- { section: "3650fc46-8903-4706-aa9b-c5957adaaf67", x: 22512, y: 624} -->

```stack
card Catch_all_18, "Catch_all_18",
  version: "1",
  uuid: "e1b87782-5fd0-51c8-b25e-fa1a45e4e585",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_24)
end

```

<!-- { section: "8fa6e123-3495-4ec8-8d41-3defe797116d", x: 23256, y: 864} -->

```stack
card Profile_cbf172, "Profile_cbf172",
  version: "1",
  uuid: "1acd4948-bace-5c4c-8e4e-0398e15c8bd5",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_6")
  then(QuizComplete)
end

```

<!-- { section: "8fcbc69a-526c-40fa-abd5-e7a068f18ebf", x: 5904, y: 96} -->

```stack
card Message_10_1, "Message_10_1",
  version: "1",
  uuid: "58278096-b795-5536-b01b-0189dc2a87c9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_1 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Poner límites y expresar claramente como te sientes nunca es intensidad, ¡es nuestra oportunidad de respetarnos a nosotras mismas y es parte de una relación sana. Nunca tenemos que sentir presión por hacer algo que no queremos, así lo hayamos hecho antes. ¡El amor es chévere cuando las dos personas están listas!"
      )
    end

  write_result("message_10", ref_Message_10_1)
  then(Message_11 when ref_Message_10_1 == "Siguiente pregunta")
  then(Catch_all_5)
end

```

<!-- { section: "4d7a4b10-c8e2-4e4d-bf3e-a8b5fa5ee7a6", x: 5856, y: 1224} -->

```stack
card Message_10_2, "Message_10_2",
  version: "1",
  uuid: "865b0227-b4c1-57c3-bd90-9fbc7795d51a",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_2 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Si no te resultaría fácil hacerlo a ti tampoco, trata de practicar como lo harías para mejorar tu confianza. Tus necesidades son importantes y deben ser escuchadas y respetadas. Hablar con tus amigas sobre esto puede ser un buen paso para apoyarse mutuamente."
      )
    end

  write_result("message_10", ref_Message_10_2)
  then(Message_11 when ref_Message_10_2 == "Siguiente pregunta")
  then(Catch_all_2)
end

```

<!-- { section: "dce38301-9423-4f06-8029-723777f7e39b", x: 8952, y: 720} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "MEDIA_AUDIO" do
  audio("9c5d0daf-7a3e-4457-8887-2c7894df9ad0-M6_P2_A1.mp3")
  then(Message_13)
end

```

<!-- { section: "9429dc35-0402-4719-9375-9e584e13d5d7", x: 9528, y: 720} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termine el audio, pulsa el botón *Ya escuché el audio*")
    end

  write_result("message_13", ref_Message_13)
  then(Message_14 when ref_Message_13 == "Ya escuché el audio")
  then(Catch_all_6)
end

```

<!-- { section: "818352c1-a996-4ea1-82db-42b39c69cdb7", x: 10152, y: 696} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Ni idea🤷‍♀️", "Lo tenemos clarísimo", "No lo hemos pensado"]) do
      text(
        "*En tu grupo de amigas*, ¿saben qué hacer si una situación como la de Pilar les llegase a pasar a una de ustedes?"
      )
    end

  then(Message14_1 when ref_Message_14 == "Ni idea🤷‍♀️")
  then(Message14_2 when ref_Message_14 == "Lo tenemos clarísimo")
  then(Message14_3 when ref_Message_14 == "No lo hemos pensado")
  then(Catch_all_7)
end

```

<!-- { section: "42a602ed-b463-4a2c-9a00-8d4174e20262", x: 11376, y: 720} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Es fundamental que en tu grupo de amigas hablen sobre situaciones como la de Pilar. Tener claridad sobre qué hacer puede marcar la diferencia en momentos difíciles. 

Herramientas que ofrecen las redes sociales, como borrar los mensajes en Telegram, WhatsApp o reportar la imagen en Facebook son algunas ideas. Siempre es bueno contar con un plan y apoyarse mutuamente, así todas estarán más preparadas para enfrentar cualquier situación que se presente.

Para que nos acordemos, repitamos los pasos que nos mencionó Pilar: 
*1)* Primero, piensa en cómo te sientes y busca apoyo 🔍
*2)* Luego, guarda pruebas y habla con un adulto o experto para obtener ayuda 📄
*3)* Revisa si la red social en que circula la foto tiene un canal para apoyarte a bajar la foto  📸
*4)* Ajusta la privacidad de tus pefiles en redes sociales  👩🏻‍💻
*5)* Puedes reportar el incidente si quieres, ya que compartir tu foto es ilegal 🚫"
  )

  then(Message_15_1)
end

```

<!-- { section: "f5a29d69-efa8-4bb1-bfc6-e08cda6a938d", x: 17472, y: 960} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("99fd4db3-6e0f-4626-8767-280b32ed2f8e-Módulo6_Auxilio.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "e367df12-006c-4aef-8a5f-111972607f6a", x: 17952, y: 960} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("e5321685-bdd7-48ff-983e-eaf3167ff734-Módulo6_Fortalesa.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "5615a4fc-87c0-40e9-a61c-c277c364545a", x: 18408, y: 960} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("caee544e-16b9-4f85-8071-e1ac09a88068-Módulo6_Noestassola.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "34b3899a-a4cb-4e12-85f8-604206bf368a", x: 18888, y: 960} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("fb19bc07-d250-4935-9811-53a704c7db4e-Modulo6_Selfcare-Copy.webp")
  text("")
  then(Mesage_22)
end

```

<!-- { section: "2f4b16c3-b899-44a6-b3ae-a7a18d3e2b0f", x: 11760, y: 744} -->

```stack
card Message_15_1, "Message_15_1",
  version: "1",
  uuid: "a8652dd1-cfc0-5448-aa2b-55632cd871b6",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Si pasamos por situaciones como estas, ¡es importante saber que no estamos solas y que hay maneras de solucionar esto!"
  )

  then(Message_16)
end

```

<!-- { section: "92e40317-4c98-4367-b088-4dfb1a6d57e2", x: 15528, y: 960} -->

```stack
card Branch_6b651f, "Branch_6b651f",
  version: "1",
  uuid: "be2fa627-d886-51f9-82a8-75b34bf5e373",
  code_generator: "CONDITIONALS" do
  then(Message19 when event.message.type == "audio")
  then(Message19 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "6cef6986-5177-47b4-a0b8-bcfe30f7858d", x: 15360, y: 1440} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_19)
end

```

<!-- { section: "8d8c32c8-524d-46dc-a2a1-a4fab8b7aa86", x: 21456, y: 864} -->

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

<!-- { section: "f4f4134b-4552-4f2b-bf82-45bbafdcfa9f", x: 21960, y: 864} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text("• Línea MAAD: lineamaad@uniandes.edu.co

• Ombudsperson: ombudsperson@uniandes.edu.co

• Decanatura de Estudiantes: centrodeapoyo@uniandes.edu.co

• Consejerxs MAAD: ombudsperson.uniandes.edu.co/maqd1/consejerxs-maad")
  then(Message_24)
end

```

<!-- { section: "f634f187-81aa-4b0a-987f-5140e6f9fb9d", x: 3456, y: 168} -->

```stack
card Branch_7828f1, "Branch_7828f1",
  version: "1",
  uuid: "90922781-57ec-5b9e-8530-a66905af3955",
  code_generator: "CONDITIONALS" do
  then(Message8 when event.message.type == "audio")
  then(Message8 when event.message.type == "text")
  then(Catch_all_2_2)
end

```

<!-- { section: "70219c0c-7855-4916-9815-3bf07977fb18", x: 3336, y: 744} -->

```stack
card Catch_all_2_2, "Catch_all_2_2",
  version: "1",
  uuid: "86031531-4763-5dde-ab3c-b02fc964194a",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_8)
end

```

<!-- { section: "4bc1e795-b276-45e0-9b7d-bb1eba3fad56", x: -1464, y: 0} -->

```stack
card Insight_1, "Insight_1",
  version: "1",
  uuid: "34b644b9-56e4-4770-8b48-e6b3f84a680d",
  code_generator: "WRITE_RESULTS" do
  write_result("module6_started", "yes")
  then(Message_2)
end

```

<!-- { section: "be50064b-656c-4eb9-8ea0-6c5161cc6a40", x: 12216, y: 1248} -->

**@Buhle**

Please save insights here

<!-- { section: "0fe93923-c61b-4bce-8998-cd0e0f6e70af", x: -744, y: 408} -->

**@Buhle**

Please save the insights here

<!-- { section: "a048f24b-7024-4e80-9a02-deb070afc124", x: 3888, y: 576} -->

**@Buhle**

Please save this for DS, I added a code block just in case that would be easier

**DS note:** Flow result: module6_beliefs {user input}

<!-- { section: "421404a1-21ba-4fdf-b649-28b682b0df7b", x: 6816, y: 744} -->

**@Buhle**

Please save insights here

<!-- { section: "0e7f4eb6-114e-4779-a2d9-6b80b4d50a07", x: 14208, y: 1392} -->

**@Buhle**

Please save insights here

<!-- { section: "b415cac3-66d7-40f2-b20a-9ed7fcdec07f", x: 16056, y: 1416} -->

**@Buhle**

Please save the user response here, its a DS thing so I added a code block below for you incase that is what you need.

**DS note:** Flow result: module6_action_planning {user input}

<!-- { section: "89033a98-ed7c-4746-af57-8fc29f75f7e5", x: 19344, y: 1392} -->

**@buhle**

Please save insights here

<!-- { section: "72bf5e93-2891-4fe4-8fb4-44a940cd2625", x: 23208, y: 1056} -->

update contact field, contact module = module 6 ✅

<!-- { section: "fd10d6a5-8b9a-4efd-8050-9a4c80168832", x: 23808, y: 1176} -->

**@Buhle**

DS note: Flow result: module6_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "3eddae03-9549-4f67-875c-49c99029d1a3", x: 10296, y: 1200} -->

**@Buhle**

Please save insights here

<!-- { section: "770dd67d-0c20-4578-bbc2-030d3b13f3f2", x: 3936, y: 120} -->

```stack
card Message8 do
  write_result("module6_beliefs", "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "ae7ad6a7-cc47-4c31-a454-0e779a2a4108", x: 15960, y: 936} -->

```stack
card Message19 do
  write_result("module6_action_planning", "@ref_message_19")
  then(Message_20)
end

```

<!-- { section: "56d5ad72-f0d4-49ff-9d07-68a3967f93ac", x: 14640, y: 1272} -->

```stack
card Message18_3 do
  write_result("module6_behavioral_activation", "c")
  then(Message_19)
end

```

<!-- { section: "ad1372dc-949f-44f7-84e4-f97f9d72fc34", x: 20016, y: 1512} -->

```stack
card Message22_3 do
  write_result("module6_behavioral_activation2", "c")
  then(Message_23)
end

```

<!-- { section: "ed19f859-0081-4fa8-9706-60313c35fe64", x: -120, y: 0} -->

```stack
card Message2_1 do
  write_result("module6_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "e111fe16-adc9-45e0-838a-10f2e9c49014", x: -120, y: 384} -->

```stack
card Message2_2 do
  write_result("module6_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "cf919b35-7a91-4aa0-a664-c33aef122f7a", x: 5112, y: -120} -->

```stack
card Message9_1 do
  write_result("module6_beliefs2", "a")
  then(Message_10_1)
end

```

<!-- { section: "2f70282b-ae6b-49f1-9edb-84c6cc116698", x: 5136, y: 288} -->

```stack
card Message9_2 do
  write_result("module6_beliefs2", "b")
  then(Message_10_1)
end

```

<!-- { section: "f469af6b-0993-4c8b-a0dc-0bc8e44e515e", x: 5136, y: 648} -->

```stack
card Message9_3 do
  write_result("module6_beliefs2", "c")
  then(Message_10_2)
end

```

<!-- { section: "670abce7-3196-4fc5-b2a8-3cb6b84b183f", x: 7248, y: -192} -->

```stack
card Message11_1 do
  write_result("module6_attitudes", "a")
  then(Message_12_1)
end

```

<!-- { section: "37090bf0-7866-481d-8beb-e1428e4d787e", x: 7320, y: 168} -->

```stack
card Message11_2 do
  write_result("module6_attitudes", "b")
  then(Message_12_2)
end

```

<!-- { section: "07f894b2-c903-4dc1-a88c-d20985381c42", x: 7344, y: 600} -->

```stack
card Message11_3 do
  write_result("module6_attitudes", "c")
  then(Message_12_3)
end

```

<!-- { section: "f61ce0af-674c-465d-8f5c-a20c64e04ebd", x: 10752, y: 384} -->

```stack
card Message14_1 do
  write_result("module6_knowledge", "a")
  then(Message_15)
end

```

<!-- { section: "525d7385-a2f1-4291-ba0f-1bfd991d711e", x: 10728, y: 720} -->

```stack
card Message14_2 do
  write_result("module6_knowledge", "b")
  then(Message_15)
end

```

<!-- { section: "ec2aadee-6bc1-425b-a08b-c6c94067cdb1", x: 10728, y: 1056} -->

```stack
card Message14_3 do
  write_result("module6_knowledge", "c")
  then(Message_15)
end

```

<!-- { section: "51aa90f8-79f9-415e-9a65-f2122991e818", x: 12816, y: 480} -->

```stack
card Message16_1 do
  write_result("module6_social_norms", "a")
  then(Message_17_1)
end

```

<!-- { section: "fe56c243-cb8c-45f3-afa9-7c8b8e3e8c99", x: 12816, y: 816} -->

```stack
card Message16_2 do
  write_result("module6_social_norms", "b")
  then(Message_17_2)
end

```

<!-- { section: "a83e1137-e8a1-420d-ad75-b798dd6aefec", x: 12792, y: 1200} -->

```stack
card Message16_3 do
  write_result("module6_social_norms", "c")
  then(Message_17_3)
end

```

<!-- { section: "e1dbbad9-95cd-403d-841c-c2cbe7e06446", x: 14592, y: 528} -->

```stack
card Message18_1 do
  write_result("module6_behavioral_activation", "a")
  then(Message_19)
end

```

<!-- { section: "e0f33452-4815-438c-b6d4-21f21135aa49", x: 14616, y: 936} -->

```stack
card Message18_2 do
  write_result("module6_behavioral_activation", "b")
  then(Message_19)
end

```

<!-- { section: "cbe73cb3-6937-4f75-b204-11506ea31fb6", x: 23808, y: 864} -->

```stack
card QuizComplete do
  write_result("module6_completed", "yes")
  then(Message_25)
end

```

<!-- { section: "9b42478d-2da6-42d1-8fbe-bd70dfcdd7e7", x: 20040, y: 720} -->

```stack
card Message22_1 do
  write_result("module6_behavioral_activation2", "a")
  then(Message_23)
end

```

<!-- { section: "3c00ecfc-7e7e-4cb0-a303-a52decbaeda6", x: 20040, y: 1128} -->

```stack
card Message22_2 do
  write_result("module6_behavioral_activation2", "b")
  then(Message_23)
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
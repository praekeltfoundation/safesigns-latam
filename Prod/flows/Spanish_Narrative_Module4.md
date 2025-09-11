<!-- { section: "96915e98-2439-4e17-bb3c-5bedee7b0d53", x: -1176, y: 0} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_only_phrase(event.message.text.body, "test_n4_2") or
       (contact.contact_module == "MODULE_3" and contact.arm == "NARRATIVE" and
          contact.quiz_post_module3_complete == true and contact.onboarding_complete == true)

```

<!-- { section: "1d808348-4b52-429d-bf73-0b4adaf55df8", x: 48, y: 0} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Hola!* 👋
Bienvenida al cuarto episodio de la historia de Pilar. ¡Ya pasamos la mitad! Hoy puede que descubramos qué es lo que le pasó a Pilar!"
  )

  then(Message1)
end

```

<!-- { section: "c460776a-f122-4eca-9e53-a3f8c13d9edf", x: 984, y: 0} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["No tuve tiempo 🕒", "Sí, ¡Buenísimo! 👍"]) do
      text("El reto de ayer era pensar en quién sería tu persona de confianza, ¿lo cumpliste?")
    end

  then(Message2_1 when ref_Message_2 == "No tuve tiempo 🕒")
  then(Message2_2 when ref_Message_2 == "Sí, ¡Buenísimo! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "a98d7a33-e46c-415f-9a01-1c5daa36cdf3", x: 1032, y: -864} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_2)
end

```

<!-- { section: "5d6f6a2c-be71-4111-94cc-cef72274cb7e", x: 2136, y: -96} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text("No te preocupes, todavía tienes tiempo. Es clave tener tu red de apoyo")
  then(Message_4)
end

```

<!-- { section: "a90a4e8b-c0f6-4e99-9844-4a26b7fcee0c", x: 2136, y: 408} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text("Increíble, ¡ya sabes en quién puedes confiar!")
  then(Message_4)
end

```

<!-- { section: "2faeeb15-a0fe-42e4-b5f9-283e0e9e9bc4", x: 2616, y: 24} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Recuerda que, si hay algo de la historia de Pilar o hay alguna pregunta te haga sentir incómoda, puedes parar y volver cuando te sientas lista. ¡Para mí es muy importante que te sientas bien!"
  )

  then(Message_5)
end

```

<!-- { section: "f36add87-ba6e-4436-8517-9ca9263378f1", x: 7416, y: -864} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_10_1)
end

```

<!-- { section: "1c9d9242-56b3-4ce4-8b86-5cdada13dc35", x: 3216, y: 0} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "MEDIA_AUDIO" do
  audio("d06dc8e2-1565-4a62-9e8f-b63f1280d9d0-M4_P1_A1.mp3")
  then(Message_6)
end

```

<!-- { section: "07aab1ce-f6f6-475c-9158-2004ad7c92b2", x: 3792, y: 0} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ya escuché el audio"]) do
      text("Cuando termines el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_7 when ref_Message_6 == "Ya escuché el audio")
  then(Catch_all_3)
end

```

<!-- { section: "e61ded93-8a51-4dc8-b531-03f6e6f46f93", x: 3816, y: -1080} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_6)
end

```

<!-- { section: "41825974-40f5-424c-a9b1-4417c1094f5c", x: 5736, y: -384} -->

```stack
card Message_8_1, "Message_8_1",
  version: "1",
  uuid: "4fa17f97-59bc-50b4-aaa7-bfc5081c1410",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Sí! Tristemente, en esta situación es normal que una persona se sienta ansiosa y abrumada, pues esta presión puede hacer que duden de sí mismas y de sus decisiones. Pueden sentir que no tienen el control y que están solas o que no pueden pedir ayuda. Si alguien está en esta situación, es importante poder hablarlo con alguien en su red de apoyo y que se sienta cobijada y no juzgada."
  )

  then(Message_9)
end

```

<!-- { section: "3254ddd1-d5be-4b18-bf66-5e3264e9f2f1", x: 4512, y: 0} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Ansiosa y abrumada🥺", "Un poco incómoda🤔", "No es para tanto 🙄"]) do
      text(
        "En el episodio, escuchamos que Pilar se sintió muy presionada por Camilo para enviarle una foto. Es una situación común en el entorno digital en el que vivimos. ¿Cómo crees que se siente alguien que está bajo presión para hacer algo incómodo?"
      )
    end

  then(Message7_1 when ref_Message_7 == "Ansiosa y abrumada🥺")
  then(Message7_2 when ref_Message_7 == "Un poco incómoda🤔")
  then(Message7_3 when ref_Message_7 == "No es para tanto 🙄")
end

```

<!-- { section: "61282550-97dc-4a82-b146-abc1ab0f7468", x: 6456, y: -840} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_9)
end

```

<!-- { section: "bc63e912-b08c-4caf-b332-847e51fad09b", x: 6384, y: 24} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Siguiente audio"]) do
      text(
        "Es normal sentirse ansiosa y abrumada por la presión que otros, como amistades o parejas, pueden ejercer sobre nosotras. Si te encuentras en esta situación, busca apoyo en alguien dentro de tu red de apoyo. No estás sola, y es fundamental que te sientas apoyada y no juzgada. ¡Veamos cómo lo hace Pilar! 🌸"
      )
    end

  then(Message_10 when ref_Message_9 == "Siguiente audio")
  then(Catch_all_4)
end

```

<!-- { section: "8dcd7627-1caf-4c65-b38f-31f232ba3c38", x: 6960, y: 24} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "MEDIA_AUDIO" do
  audio("8f8073a6-230c-4dfa-b282-0438af62b66b-M4_P2_A1.mp3")
  then(Message_10_1)
end

```

<!-- { section: "91d88556-f4e6-4e36-8333-fb6202cdab34", x: 8064, y: 0} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "QUESTION" do
  ref_Message_11 =
    ask(
      "¡Todas tenemos características que nos hacen únicas y especiales! Algunas somos valientes, como Pilar, que enfrenta sus miedos con el apoyo de sus amigas. Otras somos perseverantes y siempre estamos ahí para ayudar a los demás. ¡Son nuestros superpoderes!
¿Crees que tienes características que te hacen especial? ¿Cómo las demuestras en tu vida diaria? Escribe al menos una y comparte por qué es importante para ti."
    )

  then(Branch_06ba9c)
end

```

<!-- { section: "6a762958-a99a-49ce-84d5-c315e1c9ec0f", x: 14376, y: -1080} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_16)
end

```

<!-- { section: "05fbcc95-9e86-4bf3-a2c8-3ce93e253ccc", x: 9912, y: -456} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["¡Por supuesto!", "Lo dudo 🤔", "No lo creo🤷‍♀️"]) do
      text(
        "En el episodio escuchamos que hubo un momento en el que Pilar se confronta consigo misma por todo lo que le está pasando, al punto de pensar que será imposible para ella salir de esta situación. Sin embargo, luego de conversar con su amiga, Pilar recuerda que ya ha superado cosas difíciles antes y que, aunque es complejo lo que está pasando, tiene el poder de enfrentar la situación.

¿Crees que, si te pasara algo retador, podrías enfrentar la situación?"
      )
    end

  then(Message12_1 when ref_Message_12 == "¡Por supuesto!")
  then(Message12_2 when ref_Message_12 == "Lo dudo 🤔")
  then(Message12_3 when ref_Message_12 == "No lo creo🤷‍♀️")
  then(Catch_all_6)
end

```

<!-- { section: "0b28b2f0-cb58-4b80-ae7f-c2e628a8cf05", x: 9072, y: -1128} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_12)
end

```

<!-- { section: "558f2453-1d4c-4b6a-8ccf-5869404590bd", x: 11328, y: -384} -->

```stack
card Message_13_1, "Message_13_1",
  version: "1",
  uuid: "1291fb19-e887-5ee6-bd07-8da2a7fd9af0",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*¡Genial! Creer en ti misma es fundamental.* Todos tenemos la capacidad de enfrentar desafíos. Al igual que Pilar, seguramente tú también has superado momentos complicados antes y eso te ha hecho más fuerte 🤩

Hablar con alguien de confianza (como Pilar lo hizo con Laura), reflexionar acerca de tu superpoder, puede ayudarte a ver la situación con más claridad y encontrar soluciones."
  )

  then(Message_14)
end

```

<!-- { section: "bff85483-aecb-4d96-930b-401e98d1b38e", x: 11328, y: 144} -->

```stack
card Message_13_2, "Message_13_2",
  version: "1",
  uuid: "d0156aec-009c-548e-bd2f-fda3750d412b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*Es normal sentir dudas en situaciones difíciles,* pero es importante recordar que todos tenemos la capacidad de enfrentar desafíos. Al igual que Pilar, seguramente tú también has superado momentos complicados antes y eso te ha hecho más fuerte 💪

Hablar con alguien de confianza (como Pilar lo hizo con Laura), reflexionar acerca de tu superpoder, puede ayudarte a ver la situación con más claridad y encontrar soluciones."
  )

  then(Message_14)
end

```

<!-- { section: "d703b5c4-2bd0-4c17-958d-090bdd84af58", x: 11328, y: 720} -->

```stack
card Message_13_3, "Message_13_3",
  version: "1",
  uuid: "d0b53090-c491-560e-9fdb-e2ba5b1436df",
  code_generator: "TEXT_MESSAGE" do
  text(
    "*Es normal sentir dudas en situaciones difíciles,* pero es importante recordar que todos tenemos la capacidad de enfrentar desafíos. Al igual que Pilar, seguramente tú también has superado momentos complicados antes y eso te ha hecho más fuerte. Date una oportunidad para intentarlo 🤗

Hablar con alguien de confianza (como Pilar lo hizo con Laura), reflexionar acerca de tu superpoder, puede ayudarte a ver la situación con más claridad y encontrar soluciones."
  )

  then(Message_14)
end

```

<!-- { section: "3839d36c-e219-453b-b10f-71a9b75e4741", x: 12072, y: -24} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Le digo que bueno ✅", "Digo NO así se enoje", "No estoy segura 🤷"]) do
      text(
        "Imagínate que, cuando Pilar estaba de novia de Camilo, él le pidió que dejara de ir a entrenar su deporte favorito para estar más tiempo con él. ¿Qué crees que harías tú si estuvieras en esa situación?"
      )
    end

  then(Message14_1 when ref_Message_14 == "Le digo que bueno ✅")
  then(Message14_2 when ref_Message_14 == "Digo NO así se enoje")
  then(Message14_3 when ref_Message_14 == "No estoy segura 🤷")
  then(Catch_all_7)
end

```

<!-- { section: "313d16ff-72bb-496d-bc37-e6f28d9b833b", x: 12048, y: -1032} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_14)
end

```

<!-- { section: "7863de10-1914-44d9-976c-a1e0c2cd0799", x: 13728, y: -48} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Siguiente pregunta"]) do
      text(
        "Es importante considerar tus propios intereses y no sacrificar lo que te gusta por complacer a tu pareja. Reconocer lo que es importante para ti te ayuda a mantener tu identidad y bienestar en la relación."
      )
    end

  then(Message_16 when ref_Message_15 == "Siguiente pregunta")
  then(Catch_all_8)
end

```

<!-- { section: "0ea36802-2cbb-4a64-87d7-5da9d54c5adb", x: 13752, y: -1152} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_15)
end

```

<!-- { section: "05bad941-ce7d-48ee-b291-9e171a25a4b2", x: 14448, y: -48} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["Algo con mi pareja", "Algo en el colegio", "Un problema en casa"]) do
      text(
        "Todas tenemos momentos en que necesitamos esa chispita para poder seguir adelante. Tú, ¿cuándo has necesitado más recordarte a ti misma que tienes un superpoder?

Cuando me pasa..."
      )
    end

  then(Message16_1 when ref_Message_16 == "Algo con mi pareja")
  then(Message16_2 when ref_Message_16 == "Algo en el colegio")
  then(Message16_3 when ref_Message_16 == "Un problema en casa")
  then(Catch_all_5)
end

```

<!-- { section: "aca66b2f-42e4-47a3-b011-c63ae0b5617a", x: 15816, y: -432} -->

```stack
card Message_17_1, "Message_17_1",
  version: "1",
  uuid: "5277b1d8-b73e-5457-b6fc-a3e93bef9c08",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! A veces hay situaciones de pareja que se pueden volver complejas por muchas razones. Tu superpoder seguro te ayuda a llevar tu relación de una mejor manera 🌟 *Recuerda: nuestros superpoderes crecen entre más los pongamos en práctica* ¡Sigue así!"
  )

  then(Mesage_18)
end

```

<!-- { section: "d4bcc126-c568-43f2-b87a-8201ba3feb24", x: 16584, y: 72} -->

```stack
card Mesage_18, "Mesage_18",
  version: "1",
  uuid: "76403693-41af-5a2e-9738-86c3881afd06",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Recuerda que creer en ti misma es clave! Todos enfrentamos desafíos y podemos dudar por la presión de otros. Aún así, como Pilar, has superado momentos difíciles que te han fortalecido. Hablar con alguien de confianza, reflexionar sobre tus fortalezas, formar tu propio criterio ante las opiniones de otros o lo que veas en redes te ayudará a encontrar claridad y formar tu propio camino 🌸"
  )

  then(Message_19)
end

```

<!-- { section: "6b75608f-7f89-4013-91ea-09ba98a63156", x: 16704, y: -888} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "20a1e49b-fff9-45c0-8c46-a2a1b163feb2", x: 17232, y: 72} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["¡Manda mis stickers!"]) do
      text(
        "Muy bien! Has escuchado el episodio 4 de la historia de Pilar 🥳

Son temas complejos, por ello para ayudarte a navegarlos, te dejo unos stickers buenísimos sobre este tema y que puedes usar para responder si llegas a vivir algo similar"
      )
    end

  then(Message_20_sticker_1 when ref_Message_19 == "¡Manda mis stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "514ede98-7b27-48e5-8738-0a8d00968a97", x: 17304, y: -792} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_19)
end

```

<!-- { section: "39d12d5e-f4b1-4ad6-bd87-b239295991b1", x: 19392, y: -72} -->

```stack
card Message_20_sticker_6, "Message_20_sticker_6",
  version: "1",
  uuid: "91404e6d-acfe-5f1c-916c-aa16a2996e53",
  code_generator: "MEDIA_IMAGE" do
  image("e66e549f-54f0-4921-a0cd-39f42a593a86-Módulo4_Ubicación2.webp")
  text("")
  then(Message_21)
end

```

<!-- { section: "ea2f4ff2-9497-4e8c-b3f0-cdc407d78355", x: 19848, y: -48} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "TEXT_MESSAGE" do
  text("Todas tenemos un superpoder en alguna parte de nuestras vidas.")
  then(Message_22)
end

```

<!-- { section: "1527f25c-f2b5-4e4c-8455-cfcab5d76e7b", x: 18888, y: -1080} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "99a6f827-7a81-4bfa-ba67-63d06590b1a8", x: 20376, y: -72} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["Apoyada", "Poderosa", "Libre"]) do
      text(
        "Ahora te voy a dejar este reto: ¿Recuerdas esa actividad/comunidad que es muy importante para ti? Para mañana, piensa en una vez en la que esa actividad o comunidad haya marcado la diferencia para ti. Puede ser un logro en particular o tan solo ejemplos de un buen día. ¿Cómo te hizo sentir?"
      )
    end

  then(Message22_1 when ref_Message_22 == "Apoyada")
  then(Message22_2 when ref_Message_22 == "Poderosa")
  then(Message22_3 when ref_Message_22 == "Libre")
  then(Catch_all_13)
end

```

<!-- { section: "383ea97e-1d15-4134-95c1-f69d017efb89", x: 20376, y: -696} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_22)
end

```

<!-- { section: "cdc8502e-a21c-4046-b69f-f7bf3a9f1d39", x: 23640, y: 576} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["¡Quiero saberlo!🧐"]) do
      text(
        "Ok amiga, esto fue todo por hoy. ¡Prepárate porque el episodio de mañana va a estar increíble! ¿Qué crees que harán Pilar y Laura para confrontar a Camilo? ¡Averigualo mañana!"
      )
    end

  then(Profile_c75e44 when ref_Message_23 == "¡Quiero saberlo!🧐")
  then(Catch_all_14)
end

```

<!-- { section: "70c3f54d-ae82-4dfa-bab6-e7d67c15c130", x: 24624, y: 672} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "TEXT_MESSAGE" do
  text("¡Nos vemos mañana! 👋🌟")
  then(ModuleCompleted)
end

```

<!-- { section: "a0774a29-d04e-40a0-956e-87e1b1c386b9", x: 23640, y: -96} -->

```stack
card Catch_all_14, "Catch_all_14",
  version: "1",
  uuid: "29fd27f6-47f0-5aec-8054-b4d312e8fcca",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien eso. Por favor, intenta de nuevo usando mis botones")
  then(Message_23)
end

```

<!-- { section: "66f3a284-6bc6-4334-8048-7a18690bc88e", x: 24216, y: 672} -->

```stack
card Profile_c75e44, "Profile_c75e44",
  version: "1",
  uuid: "e7ab96f5-bb7c-5edc-8a23-b68cadecd4dc",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_4")
  then(Message_24)
end

```

<!-- { section: "4d8a6922-2864-403b-a0e3-c6d1ed64733f", x: 5712, y: 216} -->

```stack
card Message_8_2, "Message_8_2",
  version: "1",
  uuid: "a6f29f91-5f48-5dc4-80c4-063a12073e9e",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Aunque parezca algo menor y de lo que una puede zafarse fácil, en esta situación es normal que una persona se sienta ansiosa y abrumada, pues esta presión puede hacer que duden de sí mismas y de sus decisiones. Pueden sentir que no tienen el control y que están solas o que no pueden pedir ayuda. Si alguien está en esta situación, es importante poder hablarlo con alguien en su red de apoyo y que se sienta cobijada y no juzgada."
  )

  then(Message_9)
end

```

<!-- { section: "d9d099d7-fbcc-4261-9656-f79ab80b110b", x: 5712, y: 864} -->

```stack
card Message_8_3, "Message_8_3",
  version: "1",
  uuid: "0f6800cf-6cc5-5057-b513-b93cecfe9ce3",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Aunque hay personas que se pueden sentir más fuertes para evitar una situación como esta, en este caso es normal que una persona se sienta sienta ansiosa y abrumada, pues esta presión puede hacer que duden de sí mismas y de sus decisiones. Pueden sentir que no tienen el control y que están solas o que no pueden pedir ayuda. Si alguien está en esta situación, es importante poder hablarlo con alguien en su red de apoyo y que se sienta cobijada y no juzgada."
  )

  then(Message_9)
end

```

<!-- { section: "954cc460-d6ef-4802-869b-4421349821f5", x: 7488, y: 0} -->

```stack
card Message_10_1, "Message_10_1",
  version: "1",
  uuid: "58278096-b795-5536-b01b-0189dc2a87c9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_1 =
    buttons(["Ya escuché el audio!"]) do
      text("Cuando termines el audio, pulsa el botón *Ya escuché el audio*")
    end

  then(Message_11 when ref_Message_10_1 == "Ya escuché el audio!")
  then(Catch_all_2)
end

```

<!-- { section: "ab984dd4-620c-4f04-9146-50e9d3973196", x: 15816, y: 48} -->

```stack
card Message_17_2, "Message_17_2",
  version: "1",
  uuid: "983efb4d-903a-5096-8c7a-e5384646d97a",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! A veces no es fácil sortear situaciones del colegio que pueden complicarse por muchas razones. Tu superpoder seguro te ayuda a llevar mejor estos retos🌟 *Recuerda: nuestros superpoderes crecen entre más los pongamos en práctica* ¡Sigue así!"
  )

  then(Mesage_18)
end

```

<!-- { section: "d57dca88-9237-457b-8fe5-7dbbdba1d58e", x: 15816, y: 528} -->

```stack
card Message_17_3, "Message_17_3",
  version: "1",
  uuid: "ec2f9663-7fe1-516c-b8cd-1d916cb61c04",
  code_generator: "TEXT_MESSAGE" do
  text(
    "¡Gracias por contarme! A veces no es fácil manejar situaciones en casa que pueden volverse complejas por muchas razones. Tu superpoder seguro te ayuda a navegar mejor tus relaciones en casa🌟 *Recuerda: nuestros superpoderes crecen entre más los pongamos en práctica* ¡Sigue así!"
  )

  then(Mesage_18)
end

```

<!-- { section: "6b7e0315-8e32-4613-ab5a-f4fab5a6060d", x: 18936, y: -48} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("2c74d5b8-21c4-4b2d-adf2-756135f9fc17-Módulo4_Ubicación1.webp")
  text("")
  then(Message_20_sticker_6)
end

```

<!-- { section: "9c1b5cdd-b2cd-4915-a3da-c36c04af714a", x: 17904, y: -456} -->

```stack
card Message_20_sticker_1, "Message_20_sticker_1",
  version: "1",
  uuid: "1bd64fe1-edca-5b84-a021-a521b042695b",
  code_generator: "MEDIA_IMAGE" do
  image("8042a3b2-e2fb-4c82-b466-2ca8f10f90ac-Módulo4_AltoAhi.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "7bb30103-3c49-44f9-b1b5-5040778f1f84", x: 17880, y: 0} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("bfa20730-1e91-4146-8452-127b12206e26-Módulo4_No.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "48be4881-0ff6-4edb-9467-65f35d9bc2a7", x: 18456, y: -432} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("1c751e9d-5833-41bd-a700-0ea718674ea9-Módulo4_Nograsias.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "f9c8c6de-dc13-4e2c-a444-43f1e2249051", x: 18432, y: 72} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("64de5dd5-fa7c-4ef0-a85f-28e68ced50d4-Módulo4_Toma.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "aed872e1-5301-41a9-a307-c077aedd6b37", x: 22632, y: 576} -->

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

<!-- { section: "9c56f4d6-7c2c-437e-82d7-57c0ef437ab4", x: 23112, y: 576} -->

```stack
card Safe_Guarding_2, "Safe_Guarding_2",
  version: "1",
  uuid: "be3ce969-d47d-522d-9af4-2579a8212d11",
  code_generator: "TEXT_MESSAGE" do
  text(
    "1. Línea Púrpura (WhatsApp): +57 300 7551846 o *Visita aquí* https://www.sdmujer.gov.co/nuestros-servicios/servicios-para-las-mujeres/linea-purpura  
2. Línea 141 (ICBF) – Atención 24/7
3. Reporte en Línea: *Te Protejo* https://teprotejocolombia.org/"
  )

  then(Message_23)
end

```

<!-- { section: "766e1da0-1bcc-48ac-a472-26e129e1e04a", x: 8552, y: 0} -->

```stack
card Branch_06ba9c, "Branch_06ba9c",
  version: "1",
  uuid: "0dce67f8-4e8d-5913-b0b8-718474237552",
  code_generator: "CONDITIONALS" do
  then(Message11 when event.message.type == "audio")
  then(Message11 when event.message.type == "text")
  then(Catch_all_2_1)
end

```

<!-- { section: "74189146-479e-4fba-b20d-1d70a80d3988", x: 8544, y: 720} -->

```stack
card Catch_all_2_1, "Catch_all_2_1",
  version: "1",
  uuid: "79456830-b96f-5fd7-aa51-2b770947a5ad",
  code_generator: "TEXT_MESSAGE" do
  text("No entendí muy bien. Por favor, inténtalo de nuevo usando texto o nota de voz.")
  then(Message_11)
end

```

<!-- { section: "b7927cd7-13e8-4789-92df-39ba87d3e63c", x: 9648, y: 456} -->

**@Buhle**

Please save users response here,

**DS note:** Flow result: module4_self_reflection {user input}

<!-- { section: "1875eeed-14d2-46b3-931f-8be9c2eefa5f", x: 10176, y: 528} -->

**@Buhle**

Please save users response here

<!-- { section: "1bdcaf87-bb4c-409f-bc96-8c8f6bd037c0", x: 20496, y: 552} -->

**@Buhle**

Please save users response here

need a variable /insight name

<!-- { section: "6a676c76-7063-42a5-ba96-ee810e680ee8", x: -696, y: 576} -->

**@Buhle**

Please add the other thingies here^

<!-- { section: "9e103c12-f7cf-4c10-92a4-2ba117dda53b", x: 288, y: 480} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

**DS note:** Flow result: module4_started (yes)

<!-- { section: "1325fece-a1cb-4b05-98ca-eb80462802d4", x: 1200, y: 408} -->

**@Buhle**

Please save insight here

<!-- { section: "c6803d4a-b1f8-4df7-b497-5b8e8e4e7462", x: 24864, y: 1200} -->

**@Buhle**

**DS note:** Flow result: module4_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "89d53543-18ce-4c80-9eb4-3d46d8091456", x: 24432, y: 1224} -->

**@Buhle**

Schedule Module 5 to start next day (6pm , Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "447de134-bb83-4b88-95c0-549099387779", x: 24216, y: 888} -->

Update contact field, contact module = Module 4 ✅

<!-- { section: "311b957c-dc19-4660-8950-a2ce35278de2", x: 4464, y: 552} -->

**@Buhle**

Please save variables here and then link them to their messages

<!-- { section: "7c7924d9-74d8-4880-982a-3b6a904e1d85", x: 14448, y: 456} -->

**@buhle**

Please save the insights here

<!-- { section: "396c51a6-b322-40a7-98ff-fe53fdfe0842", x: 9072, y: -72} -->

```stack
card Message11 do
  write_result("module4_self_reflection", "@ref_message_11")
  then(Message_12)
end

```

<!-- { section: "4a8a2f23-3ab6-4dff-bb31-9bb4bef1f27b", x: 25080, y: 672} -->

```stack
card ModuleCompleted do
  log("Module 4 Complete")
  write_result("module4_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 23, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "f383ca4a-66f5-41a1-9784-4fcb9bdf9e90", x: 5088, y: -216} -->

```stack
card Message7_1 do
  write_result("module4_beliefs", "a")
  then(Message_8_1)
end

```

<!-- { section: "a0df9874-373b-4760-b92f-4f7c686f3d53", x: 5088, y: 144} -->

```stack
card Message7_2 do
  write_result("module4_beliefs", "b")
  then(Message_8_2)
end

```

<!-- { section: "d2b47ebf-236f-49aa-9c76-153ad5060b9b", x: 5088, y: 600} -->

```stack
card Message7_3 do
  write_result("module2_challenge_followup", "c")
  then(Message_8_3)
end

```

<!-- { section: "6b13b1f2-1620-48e6-8c55-e07468741e03", x: 528, y: -48} -->

```stack
card Message1 do
  write_result("module4_started", "yes")
  then(Message_2)
end

```

<!-- { section: "32dc2c6f-fa77-4297-846b-d1eea3f79538", x: 1464, y: 264} -->

```stack
card Message2_2 do
  write_result("module4_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "3877d0bf-7397-4ad7-ab5e-56431ed2d2ee", x: 1488, y: -240} -->

```stack
card Message2_1 do
  write_result("module4_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "f0397392-5176-4eb0-99a8-0f8e85e59fdb", x: 21600, y: -192} -->

```stack
card Message22_1 do
  write_result("module2_social_norms", "a")
  then(Safe_Guarding_1)
end

```

<!-- { section: "87c3a0c0-1681-4ca5-b9c8-d30ff485b7b2", x: 21576, y: 312} -->

```stack
card Message22_2 do
  write_result("module4_behavioral_activation", "b")
  then(Safe_Guarding_1)
end

```

<!-- { section: "bd77c3e3-817a-4249-82fc-67b8588d3f1f", x: 21600, y: 816} -->

```stack
card Message22_3 do
  write_result("module4_behavioral_activation", "c")
  then(Safe_Guarding_1)
end

```

<!-- { section: "bab987cc-b9ca-4506-9b60-05f59ad1d211", x: 15096, y: -480} -->

```stack
card Message16_1 do
  write_result("module4_social_norms", "a")
  then(Message_17_1)
end

```

<!-- { section: "bf4a8ed3-87fc-4477-a9c5-2b13faa73e38", x: 15096, y: -24} -->

```stack
card Message16_2 do
  write_result("module4_social_norms", "b")
  then(Message_17_2)
end

```

<!-- { section: "db87897d-7760-43a4-88ff-00b9f0141ebf", x: 15096, y: 384} -->

```stack
card Message16_3 do
  write_result("module4_social_norms", "c")
  then(Message_17_3)
end

```

<!-- { section: "dcbb345f-0568-4886-b608-c294c4d32687", x: 12912, y: -528} -->

```stack
card Message14_1 do
  write_result("module4_attitudes", "a")
  then(Message_15)
end

```

<!-- { section: "227012ba-8616-4044-af37-ce4e0e7ab7a5", x: 12912, y: -72} -->

```stack
card Message14_2 do
  write_result("module4_attitudes", "b")
  then(Message_15)
end

```

<!-- { section: "4f82064a-87c4-461c-9d27-b613d5a2fb00", x: 12888, y: 384} -->

```stack
card Message14_3 do
  write_result("module4_attitudes", "c")
  then(Message_15)
end

```

<!-- { section: "5fe68a0b-8263-41ff-8529-9aa16e53ac0d", x: 10800, y: -456} -->

```stack
card Message12_1 do
  write_result("module4_beliefs_self_efficacy", "a")
  then(Message_13_1)
end

```

<!-- { section: "1d9e401d-dfc7-4e39-9877-a2565a519e0c", x: 10800, y: 48} -->

```stack
card Message12_2 do
  write_result("module4_beliefs_self_efficacy", "b")
  then(Message_13_2)
end

```

<!-- { section: "5f2efdeb-f0fd-4d36-926c-62cef637fd24", x: 10800, y: 672} -->

```stack
card Message12_3 do
  write_result("module4_beliefs_self_efficacy", "c")
  then(Message_13_3)
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
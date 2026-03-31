<!-- { section: "f4804754-ee46-4f1f-b3d7-69aebb96d30e", x: -1536, y: -96} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_2" and contact.arm == "GAMIFIED" and
       contact.onboarding_complete == true

```

<!-- { section: "08bb5a16-e7b8-4412-a4d7-57ef9c86fbf9", x: -576, y: -24} -->

```stack
card Message_1_, "Message_1_", code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 Welcome to the third episode of Pilar and Mari's podcast. This keeps getting better!"
  )

  then(Message1)
end

```

<!-- { section: "920f7b2f-da5f-47b3-949b-e78332043865", x: -792, y: 600} -->

```stack
card Branch_251945, "Branch_251945", code_generator: "CONDITIONALS" do
  then(
    RESERVED_DEFAULT_CARD
    when contact.arm == "GAMIFIED" and contact.onboarding_complete == true and
           contact.contact_module == "MODULE_2"
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "b7b86a5a-438b-4dc2-8a04-5cc4398dade9", x: 624, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time", "Very good 👍"]) do
      text(
        "Yesterday's challenge was to do your first day of Zen practice 🧘 🎵 ✍️ How did yesterday's challenge go?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time")
  then(Message2_2 when ref_Message_2 == "Very good 👍")
  then(Catch_all_1)
end

```

<!-- { section: "10b5d96e-ebfe-45b4-ba54-a1bec6b576b3", x: 576, y: -648} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "dbc7f180-4f3f-4b7a-9a14-dab34d5624da", x: 1608, y: 48} -->

```stack
card Message_3_1, "Message_3_1", code_generator: "TEXT_MESSAGE" do
  text("Don't worry, you can catch up today!")
  then(Message_4)
end

```

<!-- { section: "90377797-0d05-4f9d-a445-f01bcb515a8d", x: 1656, y: 264} -->

```stack
card Message_3_2, "Message_3_2", code_generator: "TEXT_MESSAGE" do
  text("Awesome, I bet it's going to show in your answers today!")
  then(Message_4)
end

```

<!-- { section: "75f8fe86-51b8-410c-a9e2-b65c7c52ec05", x: 2352, y: 72} -->

```stack
card Message_4, "Message_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Okay 👍"]) do
      text("Remember that the longer your streak, the more stickers you accumulate!")
    end

  then(Message_5 when ref_Message_4 == "Okay 👍")
  then(Catch_all_2)
end

```

<!-- { section: "48106215-ac54-4891-b491-e4a1d67104cd", x: 2280, y: -696} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "0f9b14fe-a7b7-44b6-bdd9-fcc29026570d", x: 2832, y: 96} -->

```stack
card Message_5, "Message_5", code_generator: "TEXT_MESSAGE" do
  text(
    "In this third episode Pilar and Mari will talk about how we can be support for someone who is going through a difficult situation. 🫂 You can also think about how you would ask for help if one day you need it 🫰"
  )

  then(Messge_6)
end

```

<!-- { section: "9a2ab4e4-79ee-4a11-9753-7524cf095d82", x: 3264, y: 96} -->

```stack
card Messge_6, "Messge_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Messge_6 =
    buttons(["Ok 👌"]) do
      text(
        "Remember that if something makes you uncomfortable, you can stop and come back when you feel ready. The most important thing is that you feel good! 🫶"
      )
    end

  then(Message_7 when ref_Messge_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "9880bb46-1aeb-46ea-a350-2922ee5f3108", x: 3216, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Messge_6)
end

```

<!-- { section: "815c27d1-1568-468e-b6f9-dfabb5849f3d", x: 3648, y: 96} -->

```stack
card Message_7, "Message_7", code_generator: "QUESTION" do
  ref_Message_7 =
    ask(
      "Thinking about this topic, it is always good to remember that having someone to trust is incredible 😎 

For you, what characteristics do you think someone should have for you to consider them a good friend? Write or send by voice note at least two characteristics"
    )

  then(Branch_1f764e)
end

```

<!-- { section: "caf01051-eac6-4f9c-ac22-fbdbd19407eb", x: 4632, y: 96} -->

```stack
card Message_8, "Message_8", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for your response! Now, let's start with the podcast🎧 

Remember that if something makes you uncomfortable, you can stop and come back when you feel ready. The most important thing is that you feel good! 🫶"
  )

  then(Message_9)
end

```

<!-- { section: "9ea286b1-b6f1-4fbb-88c3-c5f0bb93f311", x: 5056, y: 96} -->

```stack
card Message_9, "Message_9", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M3_P1")
  then(Message_10)
end

```

<!-- { section: "b65ab4bd-2ffc-42de-9c70-88f97df8eb21", x: 5544, y: 96} -->

```stack
card Message_10, "Message_10", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["I heard the audio"]) do
      text("List? When the audio ends, press the I heard the audio button")
    end

  then(Message_11 when ref_Message_10 == "I heard the audio")
  then(Catch_all_4)
end

```

<!-- { section: "0dfeeb8a-aa71-4fde-b273-031598f750fc", x: 6072, y: 120} -->

```stack
card Message_11, "Message_11", code_generator: "TEXT_MESSAGE" do
  text("Today's topic is complex! Let's reflect a little.")
  then(Message_12)
end

```

<!-- { section: "ae3ab9ec-0fd7-4d46-842d-80a8c9e4a082", x: 6552, y: 120} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Whose? Gossip🔥", "I don't care🙄", "It's a serious issue"]) do
      text(
        "As Mari and Pilar told us, imagine that in the WhatsApp group of the boys from the soccer team they are sharing photos with sexual content of some teammates. What do you think of this situation?"
      )
    end

  then(Message12_1 when ref_Message_12 == "Whose? Gossip🔥")
  then(Message12_2 when ref_Message_12 == "I don't care🙄")
  then(Message12_3 when ref_Message_12 == "It's a serious issue")
  then(Catch_all_5)
end

```

<!-- { section: "c9697edb-b9f7-45c4-b8aa-fd1890d8eb66", x: 5496, y: -576} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10)
end

```

<!-- { section: "0af10636-4a7a-490d-8b37-36220db599e6", x: 6576, y: -600} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "b936cad2-2099-4818-bc15-d1cf86f232a5", x: 8040, y: -288} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M3_P1_R1")
  then(Message_13_)
end

```

<!-- { section: "2b62eadd-0272-4717-b97d-5e7fbca4adec", x: 8064, y: 264} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M3_P1_R2")
  then(Message_13_)
end

```

<!-- { section: "9ab501ac-5c56-49fe-95ca-79d6282c5649", x: 8064, y: 984} -->

```stack
card Message_13_3, "Message_13_3", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M3_P1_R3")
  then(Message_13_)
end

```

<!-- { section: "1e985cf2-38aa-42d5-a081-8e802173b265", x: 8688, y: -840} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "5fe3b4a8-d5c4-4da5-82c0-40ca358b50df", x: 8712, y: 456} -->

```stack
card Message_13_, "Message_13_", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13_ =
    buttons(["Follow the podcast"]) do
      text("When the audio ends, press the Follow the podcast button 🎧")
    end

  then(Message_14_1 when ref_Message_13_ == "Follow the podcast")
  then(Catch_all_8)
end

```

<!-- { section: "93ddd2e0-43a8-49f8-ad81-62f7b57b74dd", x: 8712, y: 48} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13_)
end

```

<!-- { section: "8eb643d0-b78e-4984-b807-8be0dde6113e", x: 9192, y: 456} -->

```stack
card Message_14_1, "Message_14_1", code_generator: "TEXT_MESSAGE" do
  text("send audio G_M3_P2")
  then(Message_14)
end

```

<!-- { section: "29d72341-f910-49b5-acab-2d38072e8205", x: 9600, y: 432} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_15 when ref_Message_14 == "I heard the audio")
  then(Catch_all_9)
end

```

<!-- { section: "9dac4005-e3f0-45d7-9900-ae0d8063a8fb", x: 9840, y: -1104} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14)
end

```

<!-- { section: "a26a9635-33b9-448f-9ae4-bb404c0d08ec", x: 10128, y: 456} -->

```stack
card Message_15, "Message_15", code_generator: "QUESTION" do
  ref_Message_15 = ask("What do you think of what Pilar and Mar have said?")
  then(Message15)
end

```

<!-- { section: "d23ee484-277f-469d-aca5-936b543641b0", x: 11088, y: 432} -->

```stack
card Message_16, "Message_16", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["List! 🏁"]) do
      text(
        "We are going to tell you a couple of situations so that you can tell us what you think of each one. Ready?"
      )
    end

  then(Message_17 when ref_Message_16 == "List! 🏁")
  then(Catch_all_10)
end

```

<!-- { section: "dde6bfad-475c-4290-9c09-4a96edf4fc92", x: 11016, y: -1104} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16)
end

```

<!-- { section: "d88b3729-41c4-4304-b6ec-ec19ea26c957", x: 11736, y: 432} -->

```stack
card Message_17, "Message_17", code_generator: "LIST" do
  ref_Message_17 =
    list("List", [
      "Let's look for help🗣️",
      "I don't believe you 😲",
      "That makes you stupid",
      "Let's kill the guy!"
    ]) do
      text(
        "Imagine that one day you walk into your living room and see that a friend is crying. She secretly tells you that her boyfriend is blackmailing her that he is going to share her intimate photos if she lets him 📸 

What would you say to him?"
      )
    end

  then(Message17_1 when ref_Message_17 == "Let's look for help🗣️")
  then(Message17_2 when ref_Message_17 == "I don't believe you 😲")
  then(Message17_3 when ref_Message_17 == "That makes you stupid")
  then(Message17_4 when ref_Message_17 == "Let's kill the guy!")
  then(Catch_all_11)
end

```

<!-- { section: "0ed0d920-45be-40fb-ae4a-99d00de6eae2", x: 11784, y: -1200} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_17)
end

```

<!-- { section: "b11a8959-4945-4c5e-8cce-38f11ec11f92", x: 15168, y: 192} -->

```stack
card Message_18, "Message_18", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Next question"]) do
      text("When the audio ends, press the next question button.")
    end

  then(Message_19 when ref_Message_18 == "Next question")
  then(Catch_all_14)
end

```

<!-- { section: "287bf6c8-1fa3-4155-84e7-00c319f2cc88", x: 14016, y: -744} -->

```stack
card Message_18_1, "Message_18_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M3_P2_R1")
  then(Message_18)
end

```

<!-- { section: "40b57be2-c807-4596-82e4-9b5aa8238b43", x: 14136, y: -48} -->

```stack
card Message_18_2, "Message_18_2", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M3_P2_R2")
  then(Message_18)
end

```

<!-- { section: "28558efa-5611-4b8c-bb46-48493c893401", x: 14112, y: 672} -->

```stack
card Message_18_3, "Message_18_3", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M3_P2_R3")
  then(Message_18)
end

```

<!-- { section: "30f57d28-806c-4573-8738-eab0763dddf6", x: 14184, y: 1320} -->

```stack
card Message_18_4, "Message_18_4", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M3_P2_R4")
  then(Message_18)
end

```

<!-- { section: "920e4fd2-b99f-4f69-affb-f83a5a3ddd8d", x: 13752, y: -1272} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "e0fac5d8-5113-4cbf-806c-07ab95037da2", x: 13728, y: -360} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "ff6d632d-eef9-4cd0-a935-479f9c08910d", x: 15288, y: -312} -->

```stack
card Catch_all_14, "Catch_all_14", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18)
end

```

<!-- { section: "243b0d7b-4df3-4dfb-a39c-1fa91c8f00a1", x: 13728, y: 1032} -->

```stack
card Catch_all_15, "Catch_all_15", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "e38e9ea5-0daa-4cf8-8b88-fce668391987", x: 15864, y: 96} -->

```stack
card Message_19, "Message_19", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["The fights 🥊", "The gossip 🗣️", "The support 🤝"]) do
      text("In your group of friends, what is the most common thing that occurs?")
    end

  then(Message19_1 when ref_Message_19 == "The fights 🥊")
  then(Message19_2 when ref_Message_19 == "The gossip 🗣️")
  then(Message19_3 when ref_Message_19 == "The support 🤝")
  then(Catch_all_16)
end

```

<!-- { section: "5aabf310-c548-4427-b36d-b7d77000895c", x: 15816, y: -1272} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_19)
end

```

<!-- { section: "8ee1f018-5082-47a5-b426-e8ffca6ba0b4", x: 17424, y: 216} -->

```stack
card Message_20, "Message_20", code_generator: "TEXT_MESSAGE" do
  text(
    "Each group of friends has its own dynamic, and it is useful to reflect on which aspects predominate. If fighting or gossip is common, consider how it could be addressed to improve the relationship. If support is most common, it's a great sign of a strong and supportive group! 💫"
  )

  then(Message_21_1)
end

```

<!-- { section: "0ce1a9eb-be5c-4f28-bb0e-ac0c89042947", x: 18624, y: 240} -->

```stack
card Message_21, "Message_21", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_21 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_22 when ref_Message_21 == "I heard the audio")
  then(Catch_all_17)
end

```

<!-- { section: "2fdd8deb-02fc-4d65-9344-41a61b1b80d0", x: 18672, y: -792} -->

```stack
card Catch_all_17, "Catch_all_17", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_21)
end

```

<!-- { section: "947b00a6-bad3-4d73-8747-54cfb3e0a29c", x: 19152, y: 240} -->

```stack
card Message_22, "Message_22", code_generator: "TEXT_MESSAGE" do
  text("It's good that you're already thinking about how to best support a friend!")
  then(Message_23)
end

```

<!-- { section: "72cb2ba0-65f3-4d07-8ba9-6a51bd97b173", x: 19560, y: 240} -->

```stack
card Message_23, "Message_23", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["Send my stickers!"]) do
      text(
        "You completed episode 3 of our podcast! 🥳 Today I have more stickers so you can use them and help you if one day you face a situation like this."
      )
    end

  then(Message_24_sticker_1 when ref_Message_23 == "Send my stickers!")
  then(Catch_all_18)
end

```

<!-- { section: "6b63c459-4ba6-4690-b021-1430132668cf", x: 19440, y: -744} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_23)
end

```

<!-- { section: "b94c7f21-1cc1-4b17-9083-c370263a97b6", x: 20448, y: -720} -->

```stack
card Message_24_sticker_1, "Message_24_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("fcf080e7-c5de-4c90-8471-6cbe5085d281-Módulo3_Ayvv.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "df34462a-22f0-4a50-843b-dd5ccf76dd8b", x: 21168, y: 264} -->

```stack
card Message_25, "Message_25", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Understood! 🫡"]) do
      text(
        "It's 3 out of 6 days of streak in the podcast challenge! Don't forget to listen to us tomorrow! 🎧"
      )
    end

  then(Message_26 when ref_Message_25 == "Understood! 🫡")
  then(Catch_all_19)
end

```

<!-- { section: "5ab07cc3-03f7-404e-9f41-ee31cbacbd42", x: 21192, y: -864} -->

```stack
card Catch_all_19, "Catch_all_19", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_25)
end

```

<!-- { section: "96b57673-20a7-4800-9f09-44ac3fae5015", x: 21672, y: 288} -->

```stack
card Message_26, "Message_26", code_generator: "QUESTION" do
  ref_Message_26 =
    ask(
      "Today we heard some tips that we can use to help someone feel better... What phrases can you think of that you could say to a friend who is going through a bad time?"
    )

  then(Message26)
end

```

<!-- { section: "bf2204c2-485a-4a93-8811-c0a780f3218b", x: 22800, y: 264} -->

```stack
card Message_27, "Message_27", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_27 =
    buttons(["Friend 👯‍♀️", "Mom or dad 👩‍👧", "Family 👩🧑"]) do
      text(
        "Now, I'm going to leave you this challenge: For tomorrow, reflect on who would be the person for you who can offer you a safe space to tell your things and help you. Who is that person for you?"
      )
    end

  then(Message27_1 when ref_Message_27 == "Friend 👯‍♀️")
  then(Message27_2 when ref_Message_27 == "Mom or dad 👩‍👧")
  then(Message27_3 when ref_Message_27 == "Family 👩🧑")
  then(Catch_all_20)
end

```

<!-- { section: "5baaeb75-e88f-42b1-af19-cac8366a6216", x: 22488, y: -840} -->

```stack
card Catch_all_20, "Catch_all_20", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_27)
end

```

<!-- { section: "c23d91ca-4e29-406b-b23d-7160e1f3a419", x: 24000, y: 312} -->

```stack
card Message_28, "Message_28", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_28 =
    buttons(["Understood 🌸"]) do
      text(
        "Ok friend, that's all for today. Get ready because tomorrow's episode is going to be amazing! We will talk about how powerful we can be 💪 and the changes we can make in our lives."
      )
    end

  then(Message_29 when ref_Message_28 == "Understood 🌸")
  then(Catch_all_21)
end

```

<!-- { section: "5a3f3c5a-b77a-4bb6-8ce2-76326506f02c", x: 24648, y: 336} -->

```stack
card Message_29, "Message_29", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_f04464)
end

```

<!-- { section: "3c36eb46-324a-450c-b457-668d0d79d3f4", x: 23544, y: -744} -->

```stack
card Catch_all_21, "Catch_all_21", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_28)
end

```

<!-- { section: "1bfb55df-e27a-4fe6-8993-2ae5d6688519", x: 25152, y: 336} -->

```stack
card Profile_f04464, "Profile_f04464", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_3")
  then(ModuleCompleted)
end

```

<!-- { section: "0708e608-5dc6-4b95-ab8c-b7f49c249045", x: 18024, y: 216} -->

```stack
card Message_21_1, "Message_21_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M3_P3")
  then(Message_21)
end

```

<!-- { section: "ac0714c2-c131-4e30-ba62-88f058eb9d57", x: 20448, y: -336} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("7752e80e-de3d-4a5a-9c70-452580c28030-Módulo3_Hablemos.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "1ad22369-3e23-41cd-9115-cd7a6df1e218", x: 20448, y: 120} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("0d7e872e-92a7-4f57-9a47-8b2972a94981-Módulo3_LasChicas.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "92231cb7-1e21-41c5-854f-5375305749ba", x: 20448, y: 696} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("9f6d1f44-df6d-4b74-a095-06fb4e1d68ea-Módulo3_Rapido.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "ac4a8b94-888e-4ae6-a8e4-29a4fa0ab328", x: 20448, y: 1224} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("99606837-f4b7-4b45-b34f-9fddfee8cf08-Módulo3_Siempre.png")
  text("")
  then(Message_25)
end

```

<!-- { section: "b02f9274-ee54-49de-85a1-e16478ab078b", x: 3960, y: -192} -->

```stack
card Branch_1f764e, "Branch_1f764e", code_generator: "CONDITIONALS" do
  then(Message7 when @event.message.type == "audio")
  then(Message7 when @event.message.type == "text")
  then(Text_ff8356)
end

```

<!-- { section: "3b22ca62-565c-4a05-b14f-2e619c77ca00", x: 3624, y: -384} -->

```stack
card Text_ff8356, "Text_ff8356", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_7)
end

```

<!-- { section: "d51076af-2984-4462-ac35-e5608bcbadee", x: 2832, y: 408} -->

Emoji problem here

<!-- { section: "c5a445b3-0c73-401d-8a01-e8dbe8ed0264", x: 3312, y: 504} -->

Emoji problem here

<!-- { section: "477c0c78-f2d5-4c81-b869-06eed546df13", x: 4608, y: 432} -->

emoji problem here

<!-- { section: "42982ede-06ae-4253-8822-a832bc6db420", x: 5016, y: 408} -->

if we switch message 9 and 10 we can avoid the problem that button messages cannot have audio files attached

<!-- { section: "2ac6a541-2a6e-4258-8aa0-aad4eeb8a282", x: 6744, y: 624} -->

@Buhle

Please save insights here

<!-- { section: "b0270f7f-b9d2-47fd-b0c5-a4c265b233e7", x: 9528, y: 1464} -->

just in case

<!-- { section: "1db1c299-2024-435d-b52e-a577aec74efa", x: 10248, y: 696} -->

**@Buhle**

Please save users response here

<!-- { section: "5d349e19-f5a6-4490-baf6-c11ddf54db4f", x: 11832, y: 1224} -->

**@buhle**

Please save users response here

<!-- { section: "14248cf1-7b18-423e-b8af-3ed6d1640b1a", x: 14064, y: 1608} -->

Add missing audio files here ^

<!-- { section: "92f75f1c-4d18-4f84-9fdd-578dbc619043", x: 15720, y: 600} -->

**@Buhle**

Please save users response here

need a variable /insight name

<!-- { section: "7a0eea4f-9732-4daa-8484-cbbe4b423285", x: 18024, y: 504} -->

missing audio file here^

<!-- { section: "ff314288-f125-4d26-9c53-a7fd239d2c70", x: 20040, y: 552} -->

**@Tam**

These are PNGs

<!-- { section: "c92c7676-be5b-45a0-b2ed-1ed36062963e", x: 21168, y: 600} -->

Emoji does not show up

<!-- { section: "ce5d4549-549c-48e8-b6d0-47ec48289899", x: 26064, y: 696} -->

**@Buhle**

Schedule Quiz Post Module 3 to start next day (6pm , Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "f89cd743-b85b-4a95-9f12-7901e5846274", x: -1056, y: 504} -->

**@Buhle**

Please add the other thingies here^

<!-- { section: "9255bb3e-3435-4d11-9de3-29fabc2cc5a3", x: 24, y: 312} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module3_started (yes)

<!-- { section: "2a6568e1-d3bb-4476-87d7-6c073d2557db", x: 744, y: 552} -->

**@Buhle**

Please save the insights here

<!-- { section: "245e1d2a-2765-4101-b4c7-c89ce5dfdbe1", x: 4128, y: 456} -->

**@Buhle**

DS note: Flow result: module3_social_support {user input}****

Please save the users response here, gave you both blocks, please dlt the one you dont need

<!-- { section: "7cb01a78-d313-4069-8810-558b781b2ea5", x: 22056, y: 672} -->

**@Buhle**

please save DS note here, I added in a code block just in case

DS note: Flow result: module3_social_support2 {user input}

<!-- { section: "1d5664d4-768a-48af-9a83-3e55739d59db", x: 22920, y: 696} -->

**@Buhle**

Please save insights here

<!-- { section: "3ee2df37-9f27-42a6-91db-dbff9f645c0f", x: 24456, y: 576} -->

Update contact field, 
contact module = Module 3✅

<!-- { section: "46fd7f73-0b8a-4ea8-9c4c-e4399bd34c0f", x: 25008, y: 624} -->

**@Buhle**

DS note: Flow result: module3_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "f0dbe030-cc0d-4f88-8532-083934e5eeb1", x: 26040, y: 888} -->

Colombia has one time zone, Colombia Time (COT), which is located in the **UTC−05:00** zone, 5 hours behind Coordinated Universal Time (UTC)

<!-- { section: "4334ee70-640b-495f-8c79-55c545ca836c", x: 24, y: -72} -->

```stack
card Message1 do
  write_result("module3_started", "yes")
  then(Message_2)
end

```

<!-- { section: "66464e21-f968-42ea-9570-08292bf13793", x: 4224, y: 96} -->

```stack
card Message7 do
  write_result("module3_social_support", "@ref_message_7")
  then(Message_8)
end

```

<!-- { section: "faf96124-fc06-4d3e-9e83-eb3f748c9eaa", x: 22176, y: 264} -->

```stack
card Message26 do
  write_result("module3_social_support2", "@ref_message_26")
  then(Message_27)
end

```

<!-- { section: "712efa2d-9313-4f01-92a7-a0ff08834db4", x: 25680, y: 288} -->

```stack
card ModuleCompleted do
  log("Module 3 Complete")
  write_result("module3_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 13, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "d4ad4987-f917-48fb-884b-a5f80dee23e8", x: 1104, y: -48} -->

```stack
card Message2_1 do
  write_result("module3_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "3223a8f1-41fa-4080-bd6f-b1899f2740a5", x: 1104, y: 288} -->

```stack
card Message2_2 do
  write_result("module3_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "57c6f3f2-10bf-44ba-9fee-8438ef0433f9", x: 7272, y: -72} -->

```stack
card Message12_1 do
  write_result("module3_beliefs", "a")
  then(Message_13_1)
end

```

<!-- { section: "fa5072af-2e36-4237-9234-50d667f51ebd", x: 7296, y: 288} -->

```stack
card Message12_2 do
  write_result("module3_beliefs", "b")
  then(Message_13_2)
end

```

<!-- { section: "a0a2f947-453e-41c7-99f1-d9d9d3afed52", x: 7296, y: 648} -->

```stack
card Message12_3 do
  write_result("module3_beliefs", "c")
  then(Message_13_3)
end

```

<!-- { section: "72508460-1b06-4efa-847e-86c52d42a0ca", x: 10608, y: 408} -->

```stack
card Message15 do
  write_result("module3_opinion", "@ref_message_15")
  then(Message_16)
end

```

<!-- { section: "846c3692-3bc2-47bc-a6f0-d98d64132454", x: 12432, y: 120} -->

```stack
card Message17_1 do
  write_result("module3_attitudes", "a")
  then(Message_18_1)
end

```

<!-- { section: "3bb72293-e59a-4af9-beaa-4101176e33ba", x: 12456, y: 456} -->

```stack
card Message17_2 do
  write_result("module3_attitudes", "b")
  then(Message_18_2)
end

```

<!-- { section: "56e65e14-3f5e-4a08-8992-0a6bb08bb827", x: 12456, y: 792} -->

```stack
card Message17_3 do
  write_result("module3_attitudes", "c")
  then(Message_18_3)
end

```

<!-- { section: "a80eb0fd-1e59-43d6-a874-adb7f5f335ea", x: 12480, y: 1128} -->

```stack
card Message17_4 do
  write_result("module3_attitudes", "d")
  then(Message_18_4)
end

```

<!-- { section: "784808de-a678-4a25-86fb-c350e3638207", x: 16488, y: -144} -->

```stack
card Message19_1 do
  write_result("module3_social_norms", "a")
  then(Message_20)
end

```

<!-- { section: "c76103ea-7cd5-44b6-a574-705ac2dfc10b", x: 16512, y: 216} -->

```stack
card Message19_2 do
  write_result("module3_social_norms", "b")
  then(Message_20)
end

```

<!-- { section: "90e6167b-16ea-4a0c-8130-66cfe1718f8f", x: 16536, y: 624} -->

```stack
card Message19_3 do
  write_result("module3_social_norms", "c")
  then(Message_20)
end

```

<!-- { section: "001944a9-0fc0-4190-991d-f2e93a107303", x: 23352, y: 72} -->

```stack
card Message27_1 do
  write_result("module3_behavioral_activation", "a")
  then(Message_28)
end

```

<!-- { section: "0f114d2d-9d09-4714-83be-099ef3f82a73", x: 23352, y: 384} -->

```stack
card Message27_2 do
  write_result("module3_behavioral_activation", "b")
  then(Message_28)
end

```

<!-- { section: "f70e8f4b-cc9f-49d1-8224-cb729c9064be", x: 23352, y: 744} -->

```stack
card Message27_3 do
  write_result("module3_behavioral_activation", "c")
  then(Message_28)
end

```

<!-- { section: "d274336d-a084-492c-9342-70d7a022ecb4", x: -1152, y: -216} -->

```stack
card RESERVED_TEMPLATE, "RESERVED_TEMPLATE", code_generator: "RESERVED_TEMPLATE" do
  # placeholder_template
end

```

<!-- { section: "7297b375-cdbd-46ae-941b-d61bc0f8aded", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
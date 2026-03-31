<!-- { section: "6d84630b-0cd9-45c1-8cac-7dc2ff4ea563", x: -1032, y: 0} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "gm1")

```

<!-- { section: "3e979dc5-f572-4c55-9ffe-6d55c9d4c0c2", x: -600, y: 96} -->

```stack
card Branch_450f80, "Branch_450f80", code_generator: "CONDITIONALS" do
  then(Message_1 when contact.onboarding_complete == true and contact.arm == "GAMIFIED")
  then(RunStack_e94a5d when contact.onboarding_complete == false and contact.arm == "NARRATIVE")
  then(RunStack_126216 when contact.onboarding_complete == true and contact.arm == "NARRATIVE")
  then(RunStack_31c610)
end

```

<!-- { section: "01bcd322-c4d0-475e-90d3-5bea141be2c0", x: -96, y: 24} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 Today we will listen to the first episode of Pilar and Mari's podcast. This first episode and all those to come are divided into three parts"
  )

  then(Message1)
end

```

<!-- { section: "87aa5e5f-4261-4c62-a817-5d0d9fabd8a0", x: 984, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["Tell me more!"]) do
      text("This podcast is also a challenge 🎯
")
    end

  then(Message_3 when ref_Message_2 == "Tell me more!")
  then(Catch_all_1)
end

```

<!-- { section: "b2bab305-e884-495a-8f5d-db1dde984952", x: 1008, y: -456} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "ab9abeab-0c66-4975-98d7-2eeab25e959a", x: 1464, y: 24} -->

```stack
card Message_3, "Message_3", code_generator: "TEXT_MESSAGE" do
  text(
    "Have you ever wanted to have the perfect sticker that will make all your friends laugh or that can get you out of an awkward situation?"
  )

  then(Message_4)
end

```

<!-- { section: "b74db51d-562c-4a4f-b2e4-fc705408c492", x: 1944, y: 24} -->

```stack
card Message_4, "Message_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Brilliant!"]) do
      text(
        "Pilar and Mari will ask you questions after each part of the episode to get your opinion. If you answer the questions we will send you fun stickers at the end of the episode. There are no right or wrong answers, we just want to know what you think."
      )
    end

  then(Message_5 when ref_Message_4 == "Brilliant!")
  then(Catch_all_2)
end

```

<!-- { section: "e68047c4-bf15-4db0-b44d-5af99077c7c4", x: 1944, y: -480} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "2938bf34-f30f-4ee4-ac43-b03c0ec15ef6", x: 2688, y: 0} -->

```stack
card Message_5, "Message_5", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Understood! 🫡"]) do
      text(
        "The more episodes you listen to, the more stickers you can earn! Try not to break your streak!"
      )
    end

  then(Message_6 when ref_Message_5 == "Understood! 🫡")
  then(Catch_all_3)
end

```

<!-- { section: "e883f0c1-3671-49cc-bc58-fa68acce6177", x: 2688, y: -504} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_5)
end

```

<!-- { section: "65af6e00-6285-46cc-ae59-f6a5a2b439df", x: 3384, y: 0} -->

```stack
card Message_6, "Message_6", code_generator: "TEXT_MESSAGE" do
  text(
    "Now, you are going to listen to the first episode of Pilar and Mari's podcast in which they will talk about healthy and toxic relationships ☠️. Remember that if there is something that Pilar and Mar talk about or a question that makes you feel uncomfortable, you can stop and come back when you feel ready. The most important thing is that you feel good!"
  )

  then(Message_7)
end

```

<!-- { section: "0d5174ba-b928-4e9e-be23-0a7faeb1dcfc", x: 4176, y: 0} -->

```stack
card Message_7, "Message_7", code_generator: "TEXT_MESSAGE" do
  text("Missing audio - Send audio - M1 PART 1")
  then(Message_8)
end

```

<!-- { section: "9f52cf75-2111-4fa0-b863-38713239ebb6", x: 4608, y: 0} -->

```stack
card Message_8, "Message_8", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the *I heard the audio* button")
    end

  then(Message_9 when ref_Message_8 == "I heard the audio")
  then(Catch_all_4)
end

```

<!-- { section: "66fe3046-fdb2-4d4e-b798-02880c25f560", x: 4920, y: -576} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "35b7cf75-6520-4264-94d8-e1d2f9ec7fc2", x: 5064, y: -48} -->

```stack
card Message_9, "Message_9", code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "What do you think of what Pilar and Mar say? Do you think that if someone looks for you all the time and calls you very often, it's cute or a form of control? 🧐 You can reply using text or voice notes"
    )

  then(Branch_eafe3e)
end

```

<!-- { section: "c041e2ff-8736-49df-a012-4804a87331b7", x: 6168, y: 24} -->

```stack
card Message_10, "Message_10", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Follow the podcast "]) do
      text("Thanks for your response ✨")
    end

  then(Message_11 when ref_Message_10 == "Follow the podcast ")
  then(Catch_all_5)
end

```

<!-- { section: "515d9d2d-ac70-441c-b46c-090031e7be7d", x: 6072, y: -552} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10)
end

```

<!-- { section: "6fda981f-3bcb-43f3-9480-ccd3959fded7", x: 7056, y: 0} -->

```stack
card Message_11_1, "Message_11_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_12 when ref_Message_11_1 == "I heard the audio")
  then(Catch_all_6)
end

```

<!-- { section: "ad183fb4-628f-4345-9441-ecfda2ba5223", x: 7032, y: -600} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11_1)
end

```

<!-- { section: "51edc687-6833-4b3e-b8a9-18952d479ef0", x: 6936, y: 0} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["He's caring for her ", "I'm not sure 😕", "It's possessive 🚫"]) do
      text(
        "You already know that Mari's boyfriend was very attentive, he not only asked her where she was but also asked her to send him her location whenever she went out 📍 

He always wanted to know where and who she was with and told Mari that it's because he cared about her all the time... 

What do you think this means? 🤔
"
      )
    end

  then(Message12_1 when ref_Message_12 == "He's caring for her ")
  then(Message12_2 when ref_Message_12 == "I'm not sure 😕")
  then(Message12_3 when ref_Message_12 == "It's possessive 🚫")
  then(Catch_all_7)
end

```

<!-- { section: "6831d50d-18b9-4249-8cc7-722286ecb7aa", x: 7680, y: -624} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "dcf714e5-bcba-4da5-853e-ae78e5b78b16", x: 8760, y: 72} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio feedback - G_M1_P2_R1")
  then(Message_13_4)
end

```

<!-- { section: "c3249a80-a578-4a47-b21c-df1a9d2559fe", x: 8760, y: 456} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text("Send audio feedback - G_M1_P2_R2")
  then(Message_13_4)
end

```

<!-- { section: "93231c60-b050-41b9-a11c-a4fcded44440", x: 8736, y: 960} -->

```stack
card Message_13_3, "Message_13_3", code_generator: "TEXT_MESSAGE" do
  text("Send audio feedback - G_M1_P2_R3")
  then(Message_13_4)
end

```

<!-- { section: "870d6079-0d3c-48a8-b14d-29a3e791bd27", x: 9312, y: 432} -->

```stack
card Message_13_4, "Message_13_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13_4 =
    buttons(["Follow the podcast"]) do
      text("When the audio ends, press the Follow the podcast button 🎧")
    end

  then(Message_14_1 when ref_Message_13_4 == "Follow the podcast")
  then(Catch_all_10)
end

```

<!-- { section: "c1505ed6-b109-4341-9903-66c9ed6771b7", x: 9384, y: 0} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13_4)
end

```

<!-- { section: "03773d18-57e0-46d0-a2f5-5c802aa253d2", x: 10320, y: 456} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_15 when ref_Message_14 == "I heard the audio")
  then(Catch_all_11)
end

```

<!-- { section: "87ef8283-7544-4467-ac45-160c4b35b2d7", x: 9864, y: -744} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14)
end

```

<!-- { section: "abba95db-ba27-4078-b701-8744ca1bcd90", x: 10872, y: 456} -->

```stack
card Message_15, "Message_15", code_generator: "LIST" do
  ref_Message_15 =
    list("List", [
      "I would respond quickly",
      "I don't answer🚫",
      "I don't know 🤷",
      "He surely loves you",
      "That's not right"
    ]) do
      text(
        "Imagine that Mari's partner also got upset when she didn't respond quickly to his messages😠 What do you think you would do if you were in that situation?"
      )
    end

  then(Message15_1 when ref_Message_15 == "I would respond quickly")
  then(Message15_2 when ref_Message_15 == "I don't answer🚫")
  then(Message15_3 when ref_Message_15 == "I don't know 🤷")
  then(Message15_4 when ref_Message_15 == "He surely loves you")
  then(Message15_5 when ref_Message_15 == "That's not right")
  then(Catch_all_12)
end

```

<!-- { section: "49e2a5f0-46b4-4d0d-a8a1-7683f3ebd6cc", x: 10800, y: -720} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15)
end

```

<!-- { section: "1306c978-e401-490a-9faf-38c364e771fe", x: 13296, y: -336} -->

```stack
card Message_16_1, "Message_16_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio file - G_M1_P3_R1")
  then(Message_16_6)
end

```

<!-- { section: "595bae02-290d-4567-bfb7-fbeaa43fc708", x: 13320, y: 288} -->

```stack
card Message_16_2, "Message_16_2", code_generator: "TEXT_MESSAGE" do
  text("Send audio file - G_M1_P3_R2")
  then(Message_16_6)
end

```

<!-- { section: "82da0f85-cf78-44cf-b1d5-e10d81fbfc37", x: 13320, y: 960} -->

```stack
card Message_16_3, "Message_16_3", code_generator: "TEXT_MESSAGE" do
  text("Send audio file - G_M1_P3_R3

Content missing ")
  then(Message_16_6)
end

```

<!-- { section: "df827586-0674-4164-b5b0-a0fe5ba331a1", x: 13272, y: 1584} -->

```stack
card Message_16_4, "Message_16_4", code_generator: "TEXT_MESSAGE" do
  text("Send audio file - G_M1_P3_R4")
  then(Message_16_6)
end

```

<!-- { section: "faea924a-5106-4112-b567-d5b3b656b336", x: 13248, y: 2400} -->

```stack
card Message_16_5, "Message_16_5", code_generator: "TEXT_MESSAGE" do
  text("Send audio file - G_M1_P3_R5")
  then(Message_16_6)
end

```

<!-- { section: "188ca741-11f9-431a-a802-4a5f2d346c35", x: 13104, y: -960} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "44d2d3be-bafe-4ad7-a4dc-bf6967677eee", x: 13992, y: 912} -->

```stack
card Message_16_6, "Message_16_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_6 =
    buttons(["Follow the podcast "]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_17_1 when ref_Message_16_6 == "Follow the podcast ")
  then(Catch_all_15)
end

```

<!-- { section: "08c81c00-7dcb-4dfc-82ff-d7f61a022afa", x: 14256, y: 240} -->

```stack
card Catch_all_15, "Catch_all_15", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16_6)
end

```

<!-- { section: "65a46551-f5df-46d6-a9d3-12ffe5cbea9e", x: 12840, y: 1320} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "3ec14d5e-cb68-4443-8451-97cc8cf9df5c", x: 12840, y: 2184} -->

```stack
card Catch_all_17, "Catch_all_17", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "2aac5218-47cf-4d68-a0f7-bf56d0b567f0", x: 15096, y: 1032} -->

```stack
card Message_17, "Message_17", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["I heard the audio!"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_18 when ref_Message_17 == "I heard the audio!")
  then(Catch_all_18)
end

```

<!-- { section: "c1dc1c8d-8b6e-43ed-b56d-bb7facae5cd7", x: 14568, y: 1008} -->

```stack
card Message_17_1, "Message_17_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio  - G_M1_P4")
  then(Message_17)
end

```

<!-- { section: "5afd3c1f-9de4-4213-a147-e438fd8e7ce0", x: 9840, y: 480} -->

```stack
card Message_14_1, "Message_14_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio G_M1_P3")
  then(Message_14)
end

```

<!-- { section: "ace96302-702d-4065-bac6-f3cf0ab20858", x: 15048, y: 264} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_17)
end

```

<!-- { section: "4a474414-51ae-4eec-a34e-2609a7cf408e", x: 15720, y: 1032} -->

```stack
card Message_18, "Message_18", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Give them 📱", "No! It's private 🗣️", "I don't know 🤷"]) do
      text(
        "Continuing with the topic of jealousy, what would you say to a friend if her boyfriend, like Camilo, insisted that she give him the passwords and users of all her networks?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Give them 📱")
  then(Message18_2 when ref_Message_18 == "No! It's private 🗣️")
  then(Message18_3 when ref_Message_18 == "I don't know 🤷")
  then(Catch_all_19)
end

```

<!-- { section: "5e6c40ba-fecf-45a2-9d99-d80dab830650", x: 15720, y: 240} -->

```stack
card Catch_all_19, "Catch_all_19", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18)
end

```

<!-- { section: "2538fa8b-08bf-4af9-9315-6a469f4bd834", x: 18192, y: 1008} -->

```stack
card Message_19, "Message_19", code_generator: "TEXT_MESSAGE" do
  text(
    "Your social networks are part of your private life and only you can decide if you feel comfortable sharing them. Something to think about is that whoever has access to your networks has a lot of power over you -- they have all your information and can send messages in your name. 

Do they insist on your friend? Do you feel pressured to give out passwords? If so, it may be a warning sign that he is controlling, not protective 🚫"
  )

  then(Message_20)
end

```

<!-- { section: "6413878d-b948-4969-a111-ec15ec01c898", x: 18696, y: 1008} -->

```stack
card Message_20, "Message_20", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["I want my stickers"]) do
      text(
        "Very good! You have reached the end of the first chapter of the podcast 🥳 

To celebrate, I have some great stickers on this topic that you can use if you experience something similar!"
      )
    end

  then(Sticker_1 when ref_Message_20 == "I want my stickers")
  then(Catch_all_20)
end

```

<!-- { section: "50e4fcd8-9bdf-4956-bc71-7514772977d6", x: 19104, y: 360} -->

```stack
card Catch_all_20, "Catch_all_20", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_20)
end

```

<!-- { section: "6142aee9-d04e-471a-8292-55d169578d8d", x: 20112, y: 960} -->

```stack
card Message_22, "Message_22", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["Understood!"]) do
      text(
        "You've already completed day 1 of 6 in the podcast challenge! Keep it up and complete a perfect streak 🤩"
      )
    end

  then(Message_23 when ref_Message_22 == "Understood!")
  then(Catch_all_21)
end

```

<!-- { section: "5ccd1790-304f-4010-8bb2-4927ac0d877a", x: 20064, y: 288} -->

```stack
card Catch_all_21, "Catch_all_21", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_22)
end

```

<!-- { section: "e7a6c790-606c-4f6c-9aa7-376f679fda39", x: 20664, y: 1008} -->

```stack
card Message_23, "Message_23", code_generator: "QUESTION" do
  ref_Message_23 =
    ask(
      "Do you think you learned something new today? Briefly tell us what you learned. Remember that you can respond using text or voice notes"
    )

  then(Branch_903e4e)
end

```

<!-- { section: "49069749-bab0-4fdb-a5a6-d14e92f0a72e", x: 21768, y: 1008} -->

```stack
card Message_24, "Message_24", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["Friends 👯‍♀️", "Mom 👩‍👧", "Family 💗"]) do
      text(
        "Now I'm going to leave you a challenge: For tomorrow, talk to someone about this topic and ask them what they think. Who do you want to talk to?"
      )
    end

  then(Message24_1 when ref_Message_24 == "Friends 👯‍♀️")
  then(Message24_2 when ref_Message_24 == "Mom 👩‍👧")
  then(Message24_3 when ref_Message_24 == "Family 💗")
  then(Catch_all_22)
end

```

<!-- { section: "3786712b-de87-47f8-9ff5-c1999d663a40", x: 21672, y: 120} -->

```stack
card Catch_all_22, "Catch_all_22", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_24)
end

```

<!-- { section: "d09c738b-f326-4c80-8b89-2ab6970f5894", x: 23496, y: 1224} -->

```stack
card Message_25, "Message_25", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Understood 🌸"]) do
      text(
        "Ok friend, that's all for today. Get ready because tomorrow's episode is going to be amazing! We will talk about what we could do to feel better about ourselves💖"
      )
    end

  then(Text_26edbf when ref_Message_25 == "Understood 🌸")
  then(Catch_all_23)
end

```

<!-- { section: "aafb9e5f-c001-412a-9f06-6fec9e3fc21b", x: 23448, y: -120} -->

```stack
card Catch_all_23, "Catch_all_23", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_25)
end

```

<!-- { section: "bc63d587-5ec5-44c9-9b5f-90a0d5150410", x: 24120, y: 1248} -->

```stack
card Text_26edbf, "Text_26edbf", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_41d474)
end

```

<!-- { section: "c74aca8d-c024-4755-900b-ff1fcca4bfa2", x: -288, y: 912} -->

```stack
card RunStack_31c610, "RunStack_31c610", code_generator: "RUN_STACK" do
  run_stack("b2bbbb0d-61c2-4e56-b926-d5a6ffcba60a")
end

```

<!-- { section: "14a11d10-1e86-4f72-8210-9e51a4a38eda", x: -72, y: 432} -->

```stack
card RunStack_e94a5d, "RunStack_e94a5d", code_generator: "RUN_STACK" do
  run_stack("69ef3715-4988-49b8-bdac-9bde0162cfde")
end

```

<!-- { section: "31391d97-016a-483e-a495-ffc599675f3e", x: -120, y: 648} -->

```stack
card RunStack_126216, "RunStack_126216", code_generator: "RUN_STACK" do
  run_stack("b1dfa95b-9d18-4d9e-b6ac-ebeb8f2f45a8")
end

```

<!-- { section: "405d53f2-a165-49ba-81f3-7f50100dda60", x: 24672, y: 1200} -->

```stack
card Profile_41d474, "Profile_41d474", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_1")
  then(ModuleCompleted)
end

```

<!-- { section: "fa136558-3655-4783-a04c-50b452b5d28a", x: 19152, y: 624} -->

```stack
card Sticker_1, "Sticker_1", code_generator: "MEDIA_IMAGE" do
  image("ac782493-a5da-48ee-9433-24826774863c-sticker.webp")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "75593444-696e-474b-b8c6-4ccd44dd2727", x: 19200, y: 1056} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("f1da06fb-18ca-4177-8ee7-7f0c3aa97305-Módulo1__Ubi.webp")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "8df9ed72-9b8a-43c5-b796-ce09526dacf1", x: 19200, y: 1560} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("6d31b29f-6167-4eaf-9c3a-8c85bb5e2322-Módulo1_DateCuenta.webp")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "e007a5f6-c747-4df0-96a1-102dc249bb83", x: 19248, y: 2088} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("5fd7e17d-ae53-4271-960b-008683a670f8-Módulo1_DejaDeLlamarme.webp")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "e9e75c83-cf7c-43b2-a6f4-02fbeff0e4d7", x: 19736, y: 2088} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("02eea7a0-799d-455b-919d-7e0c0bacacf7-Módulo1_Límites.webp")
  text("")
  then(Message_22)
end

```

<!-- { section: "ab7add5e-ce81-43a6-bfd2-4388dcbd9c8e", x: 6624, y: 72} -->

```stack
card Message_11, "Message_11", code_generator: "TEXT_MESSAGE" do
  text("Send audio G_M1_P2")
  then(Message_11_1)
end

```

<!-- { section: "ef59c839-501e-47e5-83e5-6bbfd76b9dc2", x: 5016, y: 312} -->

```stack
card Catch_all_9_1, "Catch_all_9_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note")
  then(Message_9)
end

```

<!-- { section: "83a5221e-5f61-4fdf-9f2c-c14505e49e88", x: 21000, y: 1008} -->

```stack
card Branch_903e4e, "Branch_903e4e", code_generator: "CONDITIONALS" do
  then(Message23 when @event.message.type == "audio")
  then(Message23 when @event.message.type == "text")
  then(Catch_all_23_1)
end

```

<!-- { section: "077d5e46-3e20-46ed-8706-6ead96c22dd3", x: 20616, y: 1344} -->

```stack
card Catch_all_23_1, "Catch_all_23_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_23)
end

```

<!-- { section: "1ff71cd5-9ea8-4921-b5a8-5da6c098d4c7", x: 5448, y: -48} -->

```stack
card Branch_eafe3e, "Branch_eafe3e", code_generator: "CONDITIONALS" do
  then(Message9 when @event.message.type == "audio")
  then(Message9 when @event.message.type == "text")
  then(Catch_all_9_1)
end

```

<!-- { section: "035a3237-233c-4920-bf8d-3d7b6407ef6c", x: 2712, y: 312} -->

Emoji does not show up

<!-- { section: "be0cc8cd-f2f5-4151-9364-ee43c4250700", x: 5856, y: 456} -->

**@Buhle**

Save user response here
DS note: Flow result: module1_boundaries {user input}

<!-- { section: "f4e6306d-31c5-4afd-9345-f4cff9344554", x: 9888, y: 648} -->

Add audio here

<!-- { section: "70461d8d-8039-4e5c-9f3e-38b0c2c076fd", x: 13368, y: -144} -->

Add audio file here

<!-- { section: "6a788b2f-e84c-4428-a824-78c1d445cbdb", x: 13392, y: 600} -->

Add audio file here

<!-- { section: "dca65de2-8164-44b7-b525-560cc42c1d20", x: 13392, y: 1296} -->

Add audio file here

<!-- { section: "c64ea74e-4aca-4d71-9306-1b7c89c2ccc2", x: 13320, y: 1776} -->

Add audio file here

<!-- { section: "e56b05ab-540d-4683-9871-a38febe5fb76", x: 13320, y: 2832} -->

content missing

<!-- { section: "36729421-9812-47bb-84e8-0353489a6a21", x: 20928, y: 1536} -->

**@Buhle**

Save insight here, I added a code block below in case you need it

DS note: Flow result: module1_learnings {user input}

<!-- { section: "85721a5c-550d-4821-8005-c3d4b8e2f408", x: 25608, y: 1608} -->

**@Buhle**

schedule follow up - post module 1 gamified flow eng

Schedule Quiz post module 1 to start next day (6pm)

Update contact.next_engagement_time

<!-- { section: "3511acbc-5909-4f45-b5af-7c84d2b7765a", x: 16080, y: 1560} -->

**@Buhle**

Save insights here

<!-- { section: "fe51536d-5e8e-4080-a88c-3878de3a04f6", x: 11040, y: 1272} -->

**@Buhle**

Save insights here

<!-- { section: "060e0776-a2ab-43b2-a011-582e45c35981", x: 456, y: 552} -->

**@Buhle**

DS note: Flow result: module1_started (yes)

I think this is a code block, added one below

<!-- { section: "0df66d9c-328f-4ff1-94ba-40cac8980927", x: 8160, y: 1104} -->

**@Buhle**

Save user insights here

<!-- { section: "351d6bfa-2752-4430-94fc-9b1574120cb6", x: 19608, y: 1488} -->

@**Tam**

These are the webp images

<!-- { section: "9bf6a708-e9c5-475c-a1cf-95b8c34ced1e", x: 22104, y: 1392} -->

**@Buhle**

Save insight here

<!-- { section: "a3e12a56-b39e-40c0-9d99-a78dae5213bd", x: 24912, y: 1560} -->

**@Buhle**

DS note: Flow result: Flow result: module1_completed (yes)

<!-- { section: "e1612b94-1ea0-4d9a-9788-dc43ad4f267d", x: -552, y: -72} -->

Re link this before QA starts,

<!-- { section: "5c7c6dfd-c545-46c3-8369-1fef82baed84", x: 4248, y: 168} -->

Add audio here

<!-- { section: "3613b881-34d0-4ee1-9c63-fa821e9aff83", x: 6696, y: 240} -->

Add audio here

<!-- { section: "cc4410dd-6e19-4045-a29e-965ea47f8e00", x: 13320, y: 2568} -->

Add audio file here

<!-- { section: "bc4729dd-cd5d-4e16-80b6-e894a0cf61d4", x: 432, y: -48} -->

```stack
card Message1 do
  write_result("module1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "1c889f57-68bf-46b7-9bf1-7783d63e5a88", x: 21336, y: 1008} -->

```stack
card Message23 do
  log("Saving message 23 response")
  write_result("module1_learnings", "@ref_message_23")
  then(Message_24)
end

```

<!-- { section: "c9d7ef23-d414-4375-a4a4-1f42d4bdb46e", x: 25344, y: 1176} -->

```stack
card ModuleCompleted do
  log("Module 1 Complete")
  write_result("module1_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 13, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "43c7be9b-7284-4230-a4f3-aed693e5d3d2", x: 5784, y: -24} -->

```stack
card Message9 do
  log("Saving message 9 response")
  write_result("module1_boundaries", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "20f4a4d2-eb99-4757-af6a-0c389e77f081", x: 8136, y: 24} -->

```stack
card Message12_1 do
  write_result("module1_beliefs", "a")
  then(Message_13_1)
end

```

<!-- { section: "5681dad5-dbfd-4d2f-87cb-8fc6663cf607", x: 8136, y: 336} -->

```stack
card Message12_2 do
  write_result("module1_beliefs", "b")
  then(Message_13_2)
end

```

<!-- { section: "c5d945bd-b4ce-4341-b05d-e64acf946547", x: 8136, y: 672} -->

```stack
card Message12_3 do
  write_result("module1_beliefs", "c")
  then(Message_13_3)
end

```

<!-- { section: "88f68462-05ba-4beb-b795-00fec7a8d0d7", x: 11448, y: 192} -->

```stack
card Message15_1 do
  write_result("module1_attitudes1", "a")
  then(Message_16_1)
end

```

<!-- { section: "f24cee4f-b991-4f1e-bdeb-81fb882f56b3", x: 11448, y: 504} -->

```stack
card Message15_2 do
  write_result("module1_attitudes1", "b")
  then(Message_16_2)
end

```

<!-- { section: "7ae5555e-069c-4972-9d7c-d3d0f1a9ec67", x: 11448, y: 816} -->

```stack
card Message15_3 do
  write_result("module1_attitudes1", "c")
  then(Message_16_3)
end

```

<!-- { section: "3bf8c21f-afbc-4c5d-bbdf-f795e5e8b4cf", x: 11448, y: 1128} -->

```stack
card Message15_4 do
  write_result("module1_attitudes1", "d")
  then(Message_16_4)
end

```

<!-- { section: "1509c32d-e178-41ff-908d-f3cc1ede7f25", x: 11448, y: 1440} -->

```stack
card Message15_5 do
  write_result("module1_attitudes1", "e")
  then(Message_16_5)
end

```

<!-- { section: "55b10de9-cf02-4f32-bb7d-594ea18ede46", x: 17376, y: 864} -->

```stack
card Message18_1 do
  write_result("module1_attitudes2", "a")
  then(Message_19)
end

```

<!-- { section: "d4a75852-1108-4066-8257-03dff68cb43c", x: 16536, y: 1152} -->

```stack
card Message18_2 do
  write_result("module1_attitudes2", "b")
  then(Message_19)
end

```

<!-- { section: "2a98266a-94a8-4b4e-b233-fbf85223ee22", x: 16536, y: 1464} -->

```stack
card Message18_3 do
  write_result("module1_attitudes2", "c")
  then(Message_19)
end

```

<!-- { section: "a54a7177-f8a4-4d5a-8d42-b48bbc28d6b2", x: 22392, y: 1008} -->

```stack
card Message24_2 do
  write_result("module1_behavioral_activation", "b")
  then(Message_25)
end

```

<!-- { section: "68251139-25e2-4dc1-a187-6f55fa957298", x: 22392, y: 696} -->

```stack
card Message24_1 do
  write_result("module1_behavioral_activation", "a")
  then(Message_25)
end

```

<!-- { section: "8e88675e-78df-462f-aa2a-e2bbe47ac448", x: 22392, y: 1320} -->

```stack
card Message24_3 do
  write_result("module1_behavioral_activation", "c")
  then(Message_25)
end

```

<!-- { section: "b57e1e1a-5905-4821-8742-d7e4d8aa264e", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
<!-- { section: "45a3312c-df64-4e68-94ab-c0ed3cde2af9", x: -2328, y: -48} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "gm6")

```

<!-- { section: "f273fe42-7f11-44f0-97f0-cfcdd0124187", x: -1656, y: 24} -->

```stack
card Branch_4c1d16, "Branch_4c1d16", code_generator: "CONDITIONALS" do
  then(
    Message_1
    when contact.arm == "GAMIFIED" and contact.onboarding_complete == true and
           contact.contact_module == "MODULE_5"
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "a564dda9-a0ec-4e50-914b-e0e537706318", x: -1032, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Are you ready for the last episode of Pilar and Mari's podcast? How quickly time has passed! 🗓️"
  )

  then(Message1)
end

```

<!-- { section: "4d272d89-7c91-4cfb-869f-625da481268d", x: 432, y: 48} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time ", "Super! 👍"]) do
      text(
        "Yesterday's challenge was to think of a famous couple (or not) who was an example of good communication in one of the 3 topics we covered: limits, saying no and healthy discussions. How did it go?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time ")
  then(Message2_2 when ref_Message_2 == "Super! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "f9afef17-1499-478b-ad22-d835605a7980", x: 960, y: -1248} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "2b328860-99d0-44ca-9a9f-5c1573887dff", x: 1728, y: 0} -->

```stack
card Message_3_1, "Message_3_1", code_generator: "TEXT_MESSAGE" do
  text("Don't worry, today you can catch up!")
  then(Message_4)
end

```

<!-- { section: "a2abe860-bee1-4e16-a077-878dce4d8bda", x: 1704, y: 384} -->

```stack
card Message_3_2, "Message_3_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Incredible! There are examples of good and bad communication everywhere. Now you know how to identify them and set your limits 👏"
  )

  then(Message_4)
end

```

<!-- { section: "dfcfa27d-1d6c-4fbd-a268-d5ab9925199e", x: 2256, y: 192} -->

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

<!-- { section: "3e880646-cc6d-40b5-b0e0-bd58b2cbe312", x: 2256, y: -864} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "856b8c05-4f68-4520-8806-adf932cff879", x: 2856, y: 192} -->

```stack
card Message_5, "Message_5", code_generator: "TEXT_MESSAGE" do
  text(
    "In this sixth episode Pilar and Mari will talk about how we can create a plan for risk situations⚠️"
  )

  then(Message_6)
end

```

<!-- { section: "3cb61e67-0f4c-468e-a4a3-7dd9c44be66e", x: 3336, y: 192} -->

```stack
card Message_6, "Message_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "As always, if something makes you uncomfortable, you can stop and come back when you feel ready. It is very important to me that you feel good!"
      )
    end

  then(Message_7 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "5c36c906-8501-4e5d-beb7-4bbf452bc29f", x: 3336, y: -960} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_6)
end

```

<!-- { section: "d656890e-3059-4df9-82d5-2605593500ee", x: 3816, y: 192} -->

```stack
card Message_7, "Message_7", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M6_P1")
  then(Message_8)
end

```

<!-- { section: "f7a49427-db87-4c80-b421-6aa109cf690a", x: 4248, y: 192} -->

```stack
card Message_8, "Message_8", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_9 when ref_Message_8 == "I heard the audio")
  then(Catch_all_4)
end

```

<!-- { section: "981c1124-bcad-4e57-876f-349a163681d0", x: 4416, y: -864} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "8e5c2d55-3da1-4894-85da-ff33765cb5ba", x: 4728, y: 168} -->

```stack
card Message_9, "Message_9", code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "Let's go back to the question. Imagine that your friend's boyfriend asked you to send him an intimate photo of her as proof of love. 

She sent it to him, but now the photo is circulating throughout the room. 

What would you do in your group of friends if this happened to one of you? 🤔"
    )

  then(Message9)
end

```

<!-- { section: "d6566de1-ae49-4816-9d5d-e5f7080e134d", x: 5568, y: 168} -->

```stack
card Message_10, "Message_10", code_generator: "TEXT_MESSAGE" do
  text("Thanks for telling us! Now let's hear what Pilar and Mari would do in this situation.")
  then(Message_11_1)
end

```

<!-- { section: "487481bf-0e91-49b6-8087-418a08aae417", x: 6336, y: 168} -->

```stack
card Message_11, "Message_11", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_12 when ref_Message_11 == "I heard the audio")
  then(Catch_all_5)
end

```

<!-- { section: "63525c30-ff85-4fda-a22d-c3575a9834dc", x: 6120, y: -912} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11)
end

```

<!-- { section: "043aabca-00f4-46be-a619-4295ebcd5e3a", x: 6792, y: 72} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Follow the podcast "]) do
      text(
        "So that you keep them in mind, I once again leave you the 5 steps that Mari and Pilar recommended: 

1) Think about how you feel and seek support 🔍 
2) Save evidence and talk to an adult or expert for help 📄 
3) Check if the social network where the photo circulates has a channel to support you in downloading the photo 📸 
4) Adjust the privacy of your profiles on social networks 👩🏻‍💻 
5) You can report the incident if you want, since sharing your photo is illegal 🚫 

If we go through situations like these, it is important to know that we are not alone and that there are ways to solve this 🫶"
      )
    end

  then(Message_13_1 when ref_Message_12 == "Follow the podcast ")
  then(Catch_all_6)
end

```

<!-- { section: "262b203f-9141-453b-8628-6bdd9cde23f0", x: 6816, y: -792} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "c5fc70d1-8afe-47a2-b4c8-64fabd6ad132", x: 7632, y: 144} -->

```stack
card Message_13, "Message_13", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_14 when ref_Message_13 == "I heard the audio")
  then(Catch_all_7)
end

```

<!-- { section: "dc5e5cf1-5eea-4b42-9746-4d48e5a32c2e", x: 7392, y: -792} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13)
end

```

<!-- { section: "4d6fb6d7-1689-490e-a1d9-cfa595b755c9", x: 8064, y: 192} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["I'm leaving👋", "I don't know🤷‍♀️", "I try to endure 🤔"]) do
      text(
        "Imagine that one of your friends and her partner went to a party. Everything was fine until she realized that her boyfriend was doing drugs with some friends. 

She feels uncomfortable and doesn't want to continue at the party. But she also feels that everyone is very strange and she is afraid that they will take her home😰 Her boyfriend tells her that if she leaves, not to call him again. 

If it were your case, what would you do?🤔"
      )
    end

  then(Message14_1 when ref_Message_14 == "I'm leaving👋")
  then(Message14_2 when ref_Message_14 == "I don't know🤷‍♀️")
  then(Message14_3 when ref_Message_14 == "I try to endure 🤔")
  then(Catch_all_8)
end

```

<!-- { section: "e0013919-ca90-4c03-8911-9ca146b5ed00", x: 8088, y: -720} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14)
end

```

<!-- { section: "e4280b2f-44a3-47d5-99c7-834d8b057eba", x: 9816, y: 24} -->

```stack
card Message_15_1, "Message_15_1", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P3_R1")
  then(Message_15_4)
end

```

<!-- { section: "048367af-7486-4f7d-afaa-97cd1cedb764", x: 9696, y: 720} -->

```stack
card Message_15_2, "Message_15_2", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P3_R2")
  then(Message_15_4)
end

```

<!-- { section: "7df200fb-595d-4b32-ac44-76c8c820ba57", x: 9696, y: 1488} -->

```stack
card Message_15_3, "Message_15_3", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P3_R3")
  then(Message_15_4)
end

```

<!-- { section: "07657131-83d8-4720-b7a9-75ec12e39cef", x: 9720, y: -408} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "db23d7ae-f635-4df2-9124-faf6155fdfd5", x: 10488, y: 288} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15_4)
end

```

<!-- { section: "913f762b-8be1-417e-996d-bf6d2bdc25b5", x: 10416, y: 792} -->

```stack
card Message_15_4, "Message_15_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_4 =
    buttons(["Next question ❓"]) do
      text("When the audio ends, press the next question button.")
    end

  then(Message_16 when ref_Message_15_4 == "Next question ❓")
  then(Catch_all_10)
end

```

<!-- { section: "1bb02b9c-0bcb-47e1-8751-64643059da8d", x: 11136, y: 816} -->

```stack
card Message_16, "Message_16", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["Brilliant! 💸", "It has its risks ⚠️", "Never! ❌"]) do
      text(
        "Now imagine that you are with your friends and one tells them that her boyfriend has proposed that they both send intimate photos to OnlyFans. She tells them the pay is VERY good! What do you think your friends would think about it?"
      )
    end

  then(Message16_1 when ref_Message_16 == "Brilliant! 💸")
  then(Message16_2 when ref_Message_16 == "It has its risks ⚠️")
  then(Message16_3 when ref_Message_16 == "Never! ❌")
  then(Catch_all_12)
end

```

<!-- { section: "48ecac59-09a9-4e78-ba51-219d2bf6169d", x: 11352, y: 72} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16)
end

```

<!-- { section: "1e84c612-ad87-4704-a920-40bc3ad8a0e9", x: 13008, y: 312} -->

```stack
card Message_17_1, "Message_17_1", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P3_R4")
  then(Message_18)
end

```

<!-- { section: "0d823549-f063-4ada-bfe5-371627ba30ae", x: 13008, y: 840} -->

```stack
card Message_17_2, "Message_17_2", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P3_R5")
  then(Message_18)
end

```

<!-- { section: "d3bd1a63-3db7-44af-9f37-a91bb522dd90", x: 12984, y: 1368} -->

```stack
card Message_17_3, "Message_17_3", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P3_R6")
  then(Message_18)
end

```

<!-- { section: "9022051d-fa83-4d75-8326-ba22989eccbd", x: 13968, y: 840} -->

```stack
card Message_18, "Message_18", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Intimate photos📸🔞", "Excessive jealousy😠", "Respond quickly⚡📱"]) do
      text(
        "It is a good habit to have a Plan B for every situation. Think of a plan you could do if your partner or someone else asks you for something you don't want to do. What do you want to focus on?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Intimate photos📸🔞")
  then(Message18_2 when ref_Message_18 == "Excessive jealousy😠")
  then(Message18_3 when ref_Message_18 == "Respond quickly⚡📱")
  then(Catch_all_13)
end

```

<!-- { section: "e7e38417-b6bc-4256-8381-26ba7684fbfc", x: 13968, y: -168} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18)
end

```

<!-- { section: "1fdeeb0c-9f56-4214-9606-2a41ed4b8fea", x: 15096, y: 960} -->

```stack
card Message_19, "Message_19", code_generator: "QUESTION" do
  ref_Message_19 =
    ask(
      "Before we go, it's time to think about your plan! If you are in an uncomfortable situation, do you know what plan B you can activate to get home safely? Think of everything you need to have to call someone or find your way...📋 You can respond in text or voice note"
    )

  then(Branch_ba5547)
end

```

<!-- { section: "5dac3fa3-8ddc-4a79-822c-0e2410c0783d", x: 16944, y: 936} -->

```stack
card Message_20, "Message_20", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_21 when ref_Message_20 == "I heard the audio")
  then(Catch_all_14)
end

```

<!-- { section: "60d82f45-6031-4cb5-8560-d2003a2c919b", x: 16440, y: 72} -->

```stack
card Catch_all_14, "Catch_all_14", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_20)
end

```

<!-- { section: "198c2a92-525a-4e94-89b2-82cdb025b769", x: 17544, y: 960} -->

```stack
card Message_21, "Message_21", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_21 =
    buttons(["Send my stickers!"]) do
      text(
        "You completed episode 6 of our podcast! 🥳 Today I have more stickers so you can use them and help you if one day you face a situation like this."
      )
    end

  then(Message_22_sticker_1 when ref_Message_21 == "Send my stickers!")
  then(Catch_all_15)
end

```

<!-- { section: "f65519eb-2263-4a8e-8242-70f334d009c7", x: 17544, y: 48} -->

```stack
card Catch_all_15, "Catch_all_15", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_21)
end

```

<!-- { section: "ad1c6e6d-eaa1-470d-aab5-6bc20f1d4e56", x: 18360, y: 312} -->

```stack
card Message_22_sticker_1, "Message_22_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("5e1dcb96-25c8-4930-839c-65cb1cf9ac61-Módulo6_Abrilosojos.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "5c3b13e5-cf59-4511-887f-d5fc7b271482", x: 18984, y: 936} -->

```stack
card Message_23, "Message_23", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["Understood! 🫡"]) do
      text(
        "It's been 6 out of 6 days of streak in the podcast challenge! You already finished it, VERY GOOD! 🥳"
      )
    end

  then(Mesage_24 when ref_Message_23 == "Understood! 🫡")
  then(Catch_all_16)
end

```

<!-- { section: "1765c980-83a6-4155-bd4c-148e2077a9b2", x: 18960, y: 72} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_23)
end

```

<!-- { section: "d2a221dd-9b81-4a1e-b496-21a8d8375625", x: 19824, y: 912} -->

```stack
card Mesage_24, "Mesage_24", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Mesage_24 =
    buttons(["Meditation🧘‍♀️", "Talk to someone👥", "Write or breathe"]) do
      text(
        "Today is our last day 😢. But I can't leave without leaving you a challenge that I want you to do every day: Take good care of yourself! I want you to think about what you will do when you don't feel well. What do you want to focus on?"
      )
    end

  then(Message24_1 when ref_Mesage_24 == "Meditation🧘‍♀️")
  then(Message24_2 when ref_Mesage_24 == "Talk to someone👥")
  then(Message24_3 when ref_Mesage_24 == "Write or breathe")
  then(Catch_all_17)
end

```

<!-- { section: "4ccf14c8-d546-4a16-8ef3-6d22a7b90278", x: 19848, y: 72} -->

```stack
card Catch_all_17, "Catch_all_17", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Mesage_24)
end

```

<!-- { section: "76b9da8c-773f-47ad-8814-761c64cb0252", x: 20976, y: 864} -->

```stack
card Message_25, "Message_25", code_generator: "TEXT_MESSAGE" do
  text(
    "I think it's great, think about when and how you can do this activity as part of your daily routine so you don't forget."
  )

  then(Message_26)
end

```

<!-- { section: "0294e76d-c62f-4699-8fd2-7a4f37cde880", x: 21504, y: 864} -->

```stack
card Message_26, "Message_26", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["Bye LiA! 🌸"]) do
      text(
        "Ok friend, I really liked meeting you and interacting with you all these days! I hope everything you learned has been very useful to you and that you don't forget how powerful you are💪"
      )
    end

  then(Message_27 when ref_Message_26 == "Bye LiA! 🌸")
  then(Catch_all_18)
end

```

<!-- { section: "adda6aa5-7bef-4c06-9c9f-813b73b5d2db", x: 22176, y: 984} -->

```stack
card Message_27, "Message_27", code_generator: "TEXT_MESSAGE" do
  text("Bye friend! 👋🌟")
  then(Profile_cbf172)
end

```

<!-- { section: "c6cd185d-446d-411e-bb68-3ec39225314a", x: 21576, y: 144} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_26)
end

```

<!-- { section: "a6984d18-fbc0-4b1d-b8c8-b46777263932", x: 22800, y: 912} -->

```stack
card Profile_cbf172, "Profile_cbf172", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_6")
  then(ModuleCompleted)
end

```

<!-- { section: "e6122331-995c-4b2f-aa16-c437e7c27359", x: 5952, y: 336} -->

```stack
card Message_11_1, "Message_11_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M6_P2")
  then(Message_11)
end

```

<!-- { section: "4596b1b1-967a-41a1-a095-ece7ac32d5f6", x: 7200, y: 144} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M6_P3")
  then(Message_13)
end

```

<!-- { section: "299a5d74-1843-4706-a83a-fe449d23a209", x: 16632, y: 1032} -->

```stack
card Message_20_1, "Message_20_1", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M6_P4")
  then(Message_20)
end

```

<!-- { section: "ff8e5640-5186-4c52-a7c7-0f20d21db7e5", x: 18312, y: 792} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("685abba9-edd3-4417-8d6f-3babaa3225a5-Módulo6_Auxilio.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "444ee784-837e-49d6-a374-6a05368c87c8", x: 18288, y: 1296} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("7cf0b22a-217d-42ea-8ddd-8de942328a7c-Módulo6_Fortalesa.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "693075e9-63a7-487c-acbd-110efa41e663", x: 18288, y: 1800} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("90990cbf-8960-426a-bd15-3b626246800e-Módulo6_Noestassola.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "437d7e2f-6716-4fc1-9b69-a0a198652396", x: 18768, y: 1728} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("ece57674-a826-45ba-b732-df4b26333b1c-Módulo6_Selfcare.png")
  text("")
  then(Message_23)
end

```

<!-- { section: "8b35fc33-3c38-4e68-b13b-9cd6ceb667ea", x: 15576, y: 936} -->

```stack
card Branch_ba5547, "Branch_ba5547", code_generator: "CONDITIONALS" do
  then(Message19 when @event.message.type == "audio")
  then(Message19 when @event.message.type == "text")
  then(Text_5ff7ca)
end

```

<!-- { section: "80eddb5d-a57e-4b20-8f36-f59979b26399", x: 15408, y: 1416} -->

```stack
card Text_5ff7ca, "Text_5ff7ca", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_19)
end

```

<!-- { section: "067e913e-4f61-47d0-b14a-d747d6d787f8", x: 22776, y: 1272} -->

We cannot have audio as button messages, will need extra copy here

if we switch message 7 & 8 we can solve the problem

We cannot have audio as button messages, will need extra copy here

emoji does not show up

We cannot have audio as button messages, will need extra copy here

We cannot have audio as button messages, will need extra copy here

**@Buhle**

Please save insights here

We cannot have audio as button messages, will need extra copy here

emoji does not show up

**@Buhle**

Please add in the other thingies here ^

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module6_started (yes)

**@Buhle**

Please save the insights here

**@Buhle**

Please save this for DS, I added a code block just in case that would be easier
**DS note:** Flow result: module6_beliefs {user input}

**@Buhle**

Please save insights here

**@Buhle**

Please save insights here

**@Buhle**

Please save the user response here, its a DS thing so I added a code block below for you incase that is what you need.

**DS note:** Flow result: module6_action_planning {user input}

**@buhle**

Send stickers named Module 6 here, I have popped the code here and put a message block in its place for now.

Once you have added the stickers/gotten that sorted we can use the code block here

**@buhle**

Please save insights here

update contact field, contact module = module 6 ✅

**@Buhle**

DS note: Flow result: module6_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "6c2f8504-26c9-448d-9f28-252a7342122f", x: 3888, y: 408} -->

missing audio

<!-- { section: "06ee4729-d011-4850-90a1-a616cb448bf0", x: -240, y: -48} -->

```stack
card Message1 do
  write_result("module6_started", "yes")
  then(Message_2)
end

```

<!-- { section: "c78b6986-9f33-43cd-9c65-ea1a8618b58d", x: 5112, y: 120} -->

```stack
card Message9 do
  write_result("module6_beliefs", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "be5961f0-4e35-43b3-82ed-f0c344cbb933", x: 16200, y: 912} -->

```stack
card Message19 do
  write_result("module6_action_planning", "@ref_message_19")
  then(Message_20_1)
end

```

<!-- { section: "00fa5b3d-040b-4217-bdcd-3a65abe49b81", x: 23448, y: 888} -->

```stack
card ModuleCompleted do
  log("Module 6 Complete")
  write_result("module6_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 13, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "bce0d8ba-9ac8-44b8-bc1f-7fc11dec9d1b", x: 1056, y: -192} -->

```stack
card Message2_1 do
  write_result("module6_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "cf5db55e-08d1-4615-9ace-07629b64b985", x: 1056, y: 216} -->

```stack
card Message2_2 do
  write_result("module6_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "085de736-fc8e-45fd-be7a-989eb74fcfcb", x: 8832, y: -72} -->

```stack
card Message14_1 do
  write_result("module6_attitudes", "a")
  then(Message_15_1)
end

```

<!-- { section: "2754c315-a147-4c59-a412-7d52a5b75d6c", x: 8832, y: 408} -->

```stack
card Message14_2 do
  write_result("module6_attitudes", "b")
  then(Message_15_2)
end

```

<!-- { section: "0f9959b7-db10-4370-a9b0-d40cf3f9cf59", x: 8856, y: 840} -->

```stack
card Message14_3 do
  write_result("module6_attitudes", "c")
  then(Message_15_3)
end

```

<!-- { section: "906f9eec-0999-4444-a9c4-002299f07bd1", x: 12024, y: 432} -->

```stack
card Message16_1 do
  write_result("module6_social_norms", "a")
  then(Message_17_1)
end

```

<!-- { section: "6e97d925-08f2-4091-b1a3-23dad37dcc87", x: 12072, y: 840} -->

```stack
card Message16_2 do
  write_result("module6_social_norms", "b")
  then(Message_17_2)
end

```

<!-- { section: "cfa41635-b5fe-4e1c-a160-0b05218adee3", x: 12072, y: 1248} -->

```stack
card Message16_3 do
  write_result("module6_social_norms", "c")
  then(Message_17_3)
end

```

<!-- { section: "75ea9a49-8f7f-4adf-95d5-fe5f7874c46f", x: 14640, y: 504} -->

```stack
card Message18_1 do
  write_result("module6_behavioral_activation", "a")
  then(Message_19)
end

```

<!-- { section: "fb25dafc-72ad-4d00-bf73-18b11d0c5600", x: 14640, y: 888} -->

```stack
card Message18_2 do
  write_result("module6_behavioral_activation", "b")
  then(Message_19)
end

```

<!-- { section: "d31d8dc4-5225-4bd1-a47b-6552edf81418", x: 14616, y: 1248} -->

```stack
card Message18_3 do
  write_result("module6_behavioral_activation", "c")
  then(Message_19)
end

```

<!-- { section: "9b206af6-196a-4c80-ac1e-f1905ddb6c54", x: 20352, y: 720} -->

```stack
card Message24_1 do
  write_result("module6_behavioral_activation2", "a")
  then(Message_25)
end

```

<!-- { section: "ebff418d-afdc-4589-abc8-fbf6d0f89131", x: 20424, y: 1056} -->

```stack
card Message24_2 do
  write_result("module6_behavioral_activation2", "b")
  then(Message_25)
end

```

<!-- { section: "781533f3-00a9-4ef5-94d7-1031cfd94e1f", x: 20424, y: 1416} -->

```stack
card Message24_3 do
  write_result("module6_behavioral_activation2", "c")
  then(Message_25)
end

```

<!-- { section: "7297b375-cdbd-46ae-941b-d61bc0f8aded", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
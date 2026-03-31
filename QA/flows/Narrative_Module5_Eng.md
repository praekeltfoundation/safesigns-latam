<!-- { section: "e9bf2711-48cd-4827-bf2a-b0dadc9cbfe6", x: -1272, y: 48} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_4" and contact.onboarding_complete == true and
       contact.arm == "NARRATIVE"

```

<!-- { section: "2dff6185-8f39-4810-9ab7-7353d4e4f85a", x: 0, y: 48} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text("Hello! 👋 Welcome to the fifth episode of Pilar's story. This keeps getting better!")
  then(Message1)
end

```

<!-- { section: "f5e95461-81d9-47f1-9292-74b64b1eb2d6", x: -216, y: 480} -->

```stack
card Branch_6b1ea9, "Branch_6b1ea9", code_generator: "CONDITIONALS" do
  then(
    RESERVED_DEFAULT_CARD
    when contact.arm == "NARRATIVE" and contact.contact_module == "MODULE_4" and
           contact.onboarding_complete == true
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "80f8d722-1a60-43e1-a0d6-34530d5c64b6", x: 1128, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time ", "Super good 👍"]) do
      text(
        "Yesterday's challenge was to think about a time when your superpower was important to you. How did yesterday's challenge go?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time ")
  then(Message2_2 when ref_Message_2 == "Super good 👍")
  then(Catch_all_1)
end

```

<!-- { section: "0fed580a-fd8b-4627-a44c-6bf07de4f7ee", x: 1200, y: -936} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "5835f5cf-0f0d-4b51-912c-08e3bc88bfe1", x: 2280, y: -72} -->

```stack
card Message_3_1, "Message_3_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Don't worry, find time today to do it! Thinking about what you value and what you are amazing about gives you confidence and energy 💫"
  )

  then(Message_4)
end

```

<!-- { section: "9006532a-136d-4f96-9d55-5c5d79612e05", x: 2304, y: 336} -->

```stack
card Message_3_2, "Message_3_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Amazing, thinking about what you value and what you are amazing about gives you confidence and energy. Keep doing it! 🫶"
  )

  then(Message_4)
end

```

<!-- { section: "e27b6a2e-d09d-47ec-9c86-9d29f026a0dd", x: 2928, y: 120} -->

```stack
card Message_4, "Message_4", code_generator: "TEXT_MESSAGE" do
  text(
    "In this episode, we will know what plan Pilar and Laura will make to confront Camilo. Come with me to find out what they did!"
  )

  then(Message_5)
end

```

<!-- { section: "d54c2686-5e60-469c-a606-79ab91096bc3", x: 3528, y: -960} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_5)
end

```

<!-- { section: "5af606a6-20f6-4932-b366-f181868a4fe7", x: 3504, y: 120} -->

```stack
card Message_5, "Message_5", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Ok 👌"]) do
      text(
        "Remember that if something makes you feel uncomfortable, you can stop and come back if you feel ready. The most important thing is that you feel good!"
      )
    end

  then(Message_6 when ref_Message_5 == "Ok 👌")
  then(Catch_all_2)
end

```

<!-- { section: "8c3789ea-de87-4d87-8dc5-c5c1a6340ad7", x: 4248, y: 120} -->

```stack
card Message_6, "Message_6", code_generator: "TEXT_MESSAGE" do
  text("Send audio file NARRATIVE - CHAPTER 5 - PART 1")
  then(Message_7)
end

```

<!-- { section: "f37231ac-ffdd-4d8f-a5d3-55d83b0cf7d7", x: 4776, y: -888} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_7)
end

```

<!-- { section: "9af12da2-d0c1-456c-9e16-83df609cf145", x: 4776, y: 120} -->

```stack
card Message_7, "Message_7", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_8 when ref_Message_7 == "I heard the audio")
  then(Catch_all_3)
end

```

<!-- { section: "33dfdc00-c526-4795-9d64-b2646d57123f", x: 5400, y: 120} -->

```stack
card Message_8, "Message_8", code_generator: "QUESTION" do
  ref_Message_8 =
    ask(
      "In the episode we hear that Pilar tells her friends that what happened to her was perhaps because she didn't know how to set limits with Camilo, since she didn't know very well what she wanted in their relationship. It's important to know what you want! 

Have you ever set limits on your relationship? 🛑 Regardless of whether you have done it or not, tell me 3 boundaries that you think are important to you."
    )

  then(Message8)
end

```

<!-- { section: "bf416f24-b400-4834-a79a-ed2b6e0461bd", x: 5352, y: -912} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "8071bc95-9da4-4be0-b260-ccdc55c64f20", x: 6552, y: 144} -->

```stack
card Message_9, "Message_9", code_generator: "TEXT_MESSAGE" do
  text(
    "It's good that you are clear about what your limits are! Remember that it is important that you always feel comfortable and it is good that you can tell others what makes you uncomfortable🙌"
  )

  then(Message_10)
end

```

<!-- { section: "79f8996e-2cfa-4040-8161-57ab7b316c36", x: 13392, y: 1056} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_2)
end

```

<!-- { section: "d21a8d58-f3e3-4c2e-b29b-d91e9b940f9c", x: 7176, y: 144} -->

```stack
card Message_10, "Message_10", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Fight harder 😡", "Calm down and talk ", "Leave it and give in"]) do
      text(
        "In the episode we hear that Laura advises Pilar to call Camilo so that she can get rid of the thorn, so that she can sing it to him properly and tell him how toxic he is 😡😡 What do you think Pili should do in this situation? 🤔"
      )
    end

  then(Message10_1 when ref_Message_10 == "Fight harder 😡")
  then(Message10_2 when ref_Message_10 == "Calm down and talk ")
  then(Message10_3 when ref_Message_10 == "Leave it and give in")
  then(Catch_all_21)
end

```

<!-- { section: "9fdd3a94-2354-4492-9a84-a917f0214a3e", x: 9264, y: 384} -->

```stack
card Message_11, "Message_11", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11 =
    buttons(["Next audio"]) do
      text(
        "Conversations are 2. Expressing what we feel is important, but doing so out of anger or a desire for revenge may not be effective. The best thing is that Pilar can do it through assertive communication, where she can say what she feels firmly without having to fall into revenge. 

Remember that communication also includes listening and the purpose must be constructive."
      )
    end

  then(Message_12_1 when ref_Message_11 == "Next audio")
  then(Catch_all_6)
end

```

<!-- { section: "0b265fb1-b0d5-45d5-9fd7-4d049612f84c", x: 9360, y: -912} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11)
end

```

<!-- { section: "50e7fdc8-4a76-49fe-ba8a-a017e9e6b7c2", x: 10704, y: 504} -->

```stack
card Message_12_2, "Message_12_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_2 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_13 when ref_Message_12_2 == "I heard the audio")
  then(Catch_all_9)
end

```

<!-- { section: "bfedccce-9899-4422-8098-17818526e49b", x: 11712, y: 528} -->

```stack
card Message_13, "Message_13", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Anyway, it worked 😡", "I don't do anything", "I talk to an adult"]) do
      text(
        "In the episode, Pilar considered \"fucking\" Camilo on social networks because she thought he had shared her photo. If you were in Pilar's situation, how would you manage your feelings and what boundaries would you set? 🤔 Remember that being assertive is important, but it is essential to do it productively, without rushing to judge or acting without knowing the whole truth."
      )
    end

  then(Message13_1 when ref_Message_13 == "Anyway, it worked 😡")
  then(Message13_2 when ref_Message_13 == "I don't do anything")
  then(Message13_3 when ref_Message_13 == "I talk to an adult")
  then(Catch_all_10)
end

```

<!-- { section: "fd9b25ba-d8c0-4ae3-bce2-7cbb8fee2b63", x: 10752, y: -96} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12_2)
end

```

<!-- { section: "3d8bbd16-e56e-418d-af53-b9823abdcc5e", x: 11688, y: -504} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13)
end

```

<!-- { section: "9d185be4-6022-4e8f-b41f-9de02a8a79f1", x: 13824, y: 240} -->

```stack
card Message_14_1, "Message_14_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_1 =
    buttons(["next part"]) do
      text(
        "Although it is an annoying situation where you would like to do justice, remember that \"fucking\" someone can have serious consequences. Assertive communication is the ability to express your thoughts and feelings honestly and respectfully. Instead of acting out of anger, consider first finding out what really happened and talking to a trusted adult. This can help you make more informed and effective decisions."
      )
    end

  then(Message_15 when ref_Message_14_1 == "next part")
  then(Catch_all_11)
end

```

<!-- { section: "113189d5-7c1a-4ca1-b537-38b1f3a797c9", x: 13776, y: 1704} -->

```stack
card Message_14_3, "Message_14_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_3 =
    buttons(["next part"]) do
      text(
        "Talking to an adult you trust is an excellent option. They can offer you a different perspective and help you communicate assertively, which is the ability to stand up for your rights and express your emotions in a direct and respectful way. Having the experience of someone you trust can guide you in addressing the problem effectively and constructively, without escalating the situation unnecessarily."
      )
    end

  then(Message_15 when ref_Message_14_3 == "next part")
  then(Catch_all_12)
end

```

<!-- { section: "c63a8a01-7780-4452-b766-e9122b908dd8", x: 13560, y: -456} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_1)
end

```

<!-- { section: "5eb96af7-4f01-422e-ae92-00c7b88754e7", x: 12792, y: 2040} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_3)
end

```

<!-- { section: "e85de88d-3dbb-4b43-8786-373671e42ed7", x: 14712, y: 960} -->

```stack
card Message_15, "Message_15", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Send my stickers!"]) do
      text(
        "Very good! Have you heard episode 5 of Pilar's story 🥳 

They are complex topics, so to help you navigate them, I leave you some great stickers on this topic that you can use to respond if you experience something similar."
      )
    end

  then(Message_16_sticker_1 when ref_Message_15 == "Send my stickers!")
  then(Catch_all_13)
end

```

<!-- { section: "513482eb-f5fa-4bdf-82ed-38811f76b126", x: 14736, y: 96} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15)
end

```

<!-- { section: "ce1cdb4d-e166-492f-84ce-dae627a726dd", x: 17016, y: -24} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "e1d6cadc-0c0d-448d-aef5-a8323890730f", x: 15408, y: 1032} -->

```stack
card Message_16_sticker_1, "Message_16_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("b44f1afc-18af-46c2-8fb1-809b937a0598-Módulo5_Escudo.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "633a8e22-2655-4c43-b8b7-93997a176b46", x: 18672, y: 312} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "0646c03b-96ec-4e47-aa65-900044c2ceed", x: 20592, y: 1152} -->

```stack
card Message_18, "Message_18", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Set limits", "Say kesi and keno!", "Fight healthy"]) do
      text(
        "Now, I'm going to leave you this challenge: For tomorrow, talk to someone about a couple you know or a famous one who is an example of good communication 🤘 

What specific element of communication do you want to focus on?"
      )
    end

  then(Message18_1 when ref_Message_18 == "Set limits")
  then(Message18_2 when ref_Message_18 == "Say kesi and keno!")
  then(Message18_3 when ref_Message_18 == "Fight healthy")
  then(Catch_all_19)
end

```

<!-- { section: "f63ab93d-b999-46ab-8c3d-1cb0f05f73c7", x: 20568, y: 384} -->

```stack
card Catch_all_19, "Catch_all_19", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18)
end

```

<!-- { section: "36d812a1-9c9d-45d0-ae9b-366399467009", x: 22464, y: 1296} -->

```stack
card Message_19, "Message_19", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["I want to know!🧐"]) do
      text(
        "Ok friend, that's all for today. Get ready because this last episode is going to be amazing! What will happen between Pilar and Mari? Do you think they will continue to be friends?"
      )
    end

  then(Profile_6cade8 when ref_Message_19 == "I want to know!🧐")
  then(Catch_all_20)
end

```

<!-- { section: "c61e20ce-253f-43b3-94b8-9592a043a175", x: 23520, y: 1392} -->

```stack
card Message_20, "Message_20", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(ModuleCompleted)
end

```

<!-- { section: "04e4bdd7-f9a4-4c4d-af1e-f773f6cb8653", x: 22656, y: 744} -->

```stack
card Catch_all_20, "Catch_all_20", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_19)
end

```

<!-- { section: "00bb7b5c-0166-40f5-94e4-044c0c4eb6b1", x: 7248, y: -816} -->

```stack
card Catch_all_21, "Catch_all_21", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10)
end

```

<!-- { section: "18c302f8-c934-4b0b-a6ec-ef3de6955e57", x: 23016, y: 1392} -->

```stack
card Profile_6cade8, "Profile_6cade8", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_5")
  then(Message_20)
end

```

<!-- { section: "3cbe243d-34c4-431e-84dc-decd4e78d323", x: 10032, y: 504} -->

```stack
card Message_12_1, "Message_12_1", code_generator: "TEXT_MESSAGE" do
  text("send audio file NARRATIVE - CHAPTER 5 - PART 2")
  then(Message_12_2)
end

```

<!-- { section: "f1cc64d9-2520-4bc3-8281-76144944d038", x: 13848, y: 888} -->

```stack
card Message_14_2, "Message_14_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_2 =
    buttons(["next part"]) do
      text(
        "Sometimes doing nothing may seem like the calmest option, but your voice needs to be heard too. Assertive communication involves expressing your feelings and needs clearly, without getting carried away by anger. Investigating the situation and talking to a trusted adult can give you clarity about what really happened and how to best proceed."
      )
    end

  then(Message_15 when ref_Message_14_2 == "next part")
  then(Catch_all_5)
end

```

<!-- { section: "2eb74b7a-135c-4908-b3da-b53b1d977d6f", x: 19224, y: 1032} -->

```stack
card Message_17, "Message_17", code_generator: "QUESTION" do
  ref_Message_17 =
    ask(
      "It's time to practice! How would you tell a friend or boyfriend that you don't want to do something?"
    )

  then(Message17)
end

```

<!-- { section: "01cf5937-3d97-4a44-a076-04f911f8facd", x: 16128, y: 1032} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("c370a25e-f93c-49ef-9a1f-2eecee595732-Módulo5_EstoyIncomoda.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "5233a2da-1e26-4643-bd4f-8dec37eb7252", x: 16848, y: 1056} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("34728fc9-67c2-4e46-9a23-106993d3c958-Módulo5_Ganamos.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "58cc191c-6b81-401f-ba4d-c48e95d6ec7d", x: 17664, y: 1032} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("f4c69dfc-0f37-4506-9605-483f00455245-Módulo5_Llamame.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "740ee35f-ae2c-4df3-bc0d-df256b0333d6", x: 18456, y: 1032} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("fe0be439-cc51-4ac9-899c-b2f3eda06389-Módulo5_Yallegue.png")
  text("")
  then(Message_17)
end

```

<!-- { section: "99dd46da-2b76-4ddc-8bc8-9aa8dc31210f", x: 2376, y: 552} -->

Emoji does not show up

<!-- { section: "72acbbae-a327-4482-a58a-4e8fb390d9a0", x: 24528, y: 1944} -->

**@Buhle**

Schedule Quiz Post Module 5 to start next day (6pm ,
Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "4d953468-afcc-4d92-95a5-35a0579d9a29", x: -648, y: 552} -->

**@Buhle**

Please add the other thingies here^

<!-- { section: "3c4fae1e-40b9-4021-9dcf-6edc046b0aae", x: 528, y: 432} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module5_started (yes)

<!-- { section: "24d9e28c-b7fa-441a-b249-420c310319b4", x: 1296, y: 432} -->

**@Buhle**

Please save these variables here

<!-- { section: "aecffaf1-7bee-49be-9e09-7a668c407e7a", x: 5880, y: 432} -->

**@Buhle**

Save user response here

This is a DS field, not sure which you need so you have both

**DS note:** Flow result: module5_boundaries {user input}

<!-- { section: "715de481-b4e4-452b-a761-1cf20b1a334e", x: 7200, y: 624} -->

**@Buhle**

Please save variables here

<!-- { section: "e393ddca-5c9f-4849-a10c-aed9e4e1499d", x: 11808, y: 1128} -->

**@Buhle**

Please save the insights here

<!-- { section: "cba37cb4-81e2-4eb8-bf49-89bd9ee3a5a4", x: 19608, y: 1560} -->

**@Buhle**
Please save the insights here

its a DS thing so added in the code block just in case

**DS note:** Flow result: module5_boundaries2 {user input}

<!-- { section: "35acb938-b530-4369-b489-948f6d12244b", x: 20640, y: 1680} -->

**@Buhle**

Please save insights here

<!-- { section: "eb46d7c5-bb8f-427e-a2c2-58ba65632d27", x: 24600, y: 1728} -->

**@Buhle**

**DS note:** Flow result: module5_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "e5155033-a04f-45fa-8b62-70c756ea4672", x: 23016, y: 1560} -->

Update contact field, contact module = Module 5 ✅

<!-- { section: "dcf2ede5-1e92-4d2a-988c-0ea50be951dd", x: 15696, y: 1416} -->

**@Tam**

Stickers are PNGs

<!-- { section: "01911bc0-6d52-4ad3-937d-f13a4a69e6f6", x: 10032, y: 696} -->

add audio file here

<!-- { section: "6239b1d8-7bc9-4a15-abee-10d6927a56d8", x: 24216, y: 1296} -->

```stack
card ModuleCompleted do
  log("Module 5 Complete")
  write_result("module5_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 13, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "4924c836-d6a9-4d8e-9530-0015e8644c45", x: 576, y: -24} -->

```stack
card Message1 do
  write_result("module5_started", "yes")
  then(Message_2)
end

```

<!-- { section: "3fcc41ef-5ac4-4991-9c73-0e0a99e9fe0f", x: 5880, y: 72} -->

```stack
card Message8 do
  write_result("module5_boundaries", "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "2429bb07-a8f1-4f77-8cbb-e68b301d6943", x: 19656, y: 1032} -->

```stack
card Message17 do
  write_result("module5_boundaries2", "@ref_message_17")
  then(Message_18)
end

```

<!-- { section: "09d04459-b249-4fe0-9772-0465e13cbfcd", x: 1680, y: -312} -->

```stack
card Message2_1 do
  write_result("module5_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "13e90381-fe4b-4fa0-a9a8-15a459447dee", x: 1680, y: 240} -->

```stack
card Message2_2 do
  write_result("module5_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "6cbc510c-0116-42d4-b5b0-8a50fbfbd141", x: 7896, y: -216} -->

```stack
card Message10_1 do
  write_result("module2_beliefs", "a")
  then(Message_11)
end

```

<!-- { section: "70788e35-a89c-4a6d-b9fc-9d53de33d971", x: 7920, y: 168} -->

```stack
card Message10_2 do
  write_result("module2_beliefs", "b")
  then(Message_11)
end

```

<!-- { section: "ee2936f8-7630-4749-914e-bba1d00f3e6e", x: 7944, y: 528} -->

```stack
card Message10_3 do
  write_result("module2_beliefs", "c")
  then(Message_11)
end

```

<!-- { section: "9c4530b3-60cf-424f-9401-e3b08bcdc433", x: 12456, y: 192} -->

```stack
card Message13_1 do
  write_result("module5_attitudes", "a")
  then(Message_14_1)
end

```

<!-- { section: "f07522e4-b252-4a8a-b920-552df1d27957", x: 12456, y: 576} -->

```stack
card Message13_2 do
  write_result("module5_attitudes", "b")
  then(Message_14_2)
end

```

<!-- { section: "1276f622-c48b-481b-ade2-98f3bcee34d3", x: 12480, y: 912} -->

```stack
card Message13_3 do
  write_result("module5_attitudes   ", "c")
  then(Message_14_3)
end

```

<!-- { section: "ee0b31ab-6385-4a49-afd0-b7a49bed069c", x: 21528, y: 816} -->

```stack
card Message18_1 do
  write_result("module5_behavioral_activation", "a")
  then(Message_19)
end

```

<!-- { section: "ed6399e5-d166-4d34-b9fc-2e3c364ed781", x: 21528, y: 1320} -->

```stack
card Message18_2 do
  write_result("module5_behavioral_activation", "b")
  then(Message_19)
end

```

<!-- { section: "d575f0b6-8d05-4806-8722-ddc219dac291", x: 21504, y: 1728} -->

```stack
card Message18_3 do
  write_result("module5_behavioral_activation", "c")
  then(Message_19)
end

```

<!-- { section: "", x: -772, y: 144} -->

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
<!-- { section: "8be9bf8e-79d9-48ac-8df8-55ce44b54e22", x: -1272, y: 48} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_4" and contact.arm == "GAMIFIED" and
       contact.onboarding_complete == true

```

<!-- { section: "d7c1b6fc-e0ae-4a07-8143-04cd752f36c4", x: 72, y: 48} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 Welcome to the fifth episode of Pilar and Mari's podcast. This keeps getting better!"
  )

  then(Message1)
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
card Message_4, "Message_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Okay 👍"]) do
      text("Remember that the longer your streak, the more stickers you accumulate!")
    end

  then(Message_5 when ref_Message_4 == "Okay 👍")
  then(Catch_all_2)
end

```

<!-- { section: "d3ca8166-fb3c-45f0-8fea-9a5de2810ad6", x: 2928, y: -960} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "50445eaf-7ffd-49e2-8062-7ef2067c9be6", x: 3768, y: 120} -->

```stack
card Message_5, "Message_5", code_generator: "TEXT_MESSAGE" do
  text(
    "In this episode Pilar and Mari will talk about communication and limits in relationships or friendships 💛"
  )

  then(Message_6)
end

```

<!-- { section: "1a452289-579c-48d8-9656-aa82991b673f", x: 4488, y: 120} -->

```stack
card Message_6, "Message_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Remember that if something makes you uncomfortable, you can stop and come back when you feel ready. The most important thing is that you feel good! 🫰"
      )
    end

  then(Message_7 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "ed01f869-d35e-4358-a671-f2883ca13f5f", x: 4488, y: -888} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_6)
end

```

<!-- { section: "09bdebcd-04bc-4e49-96cd-a366e0fff277", x: 5304, y: 144} -->

```stack
card Message_7, "Message_7", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M5_P1")
  then(Message_8)
end

```

<!-- { section: "9cb8c1cb-3b5c-4e7c-a96b-10f3ec822960", x: 5880, y: 144} -->

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

<!-- { section: "eccf3922-c684-4ae3-bce2-465854fba170", x: 5880, y: -960} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "10e5edd3-106f-4462-b495-6996fe319f63", x: 6384, y: 144} -->

```stack
card Message_9, "Message_9", code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "Have you ever set limits on your relationship? 🛑 Regardless of whether you have done it or not, tell me 3 limits that you think are important to you"
    )

  then(Message9)
end

```

<!-- { section: "7ba16cc2-4daa-4515-ba79-878fe437779c", x: 7272, y: 144} -->

```stack
card Message_10, "Message_10", code_generator: "TEXT_MESSAGE" do
  text(
    "It's good that you are clear about what your limits are! Remember that it is important that you always feel comfortable and it is good that you can tell others what makes you uncomfortable🙌"
  )

  then(Message_11_1)
end

```

<!-- { section: "856fe0a6-8f4e-4408-b5f2-1c22954300cc", x: 8184, y: 144} -->

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

<!-- { section: "685446c7-4d6c-4f50-a9f3-121fdb2bd734", x: 7920, y: -912} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11)
end

```

<!-- { section: "23752748-0cbe-4e90-8092-529634f1bcb4", x: 8640, y: 120} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Fight harder 😡", "Calm down and talk ", "Leave it and give in"]) do
      text(
        "Let's go back to the question, let's imagine that Pilar and her partner have a disagreement and that's why they start arguing loudly and angrily 😡😡 What do you think Pilar should do in this situation? 🤔"
      )
    end

  then(Message12_1 when ref_Message_12 == "Fight harder 😡")
  then(Message12_2 when ref_Message_12 == "Calm down and talk ")
  then(Message12_3 when ref_Message_12 == "Leave it and give in")
  then(Catch_all_21)
end

```

<!-- { section: "b19a7c4a-9aa6-4125-a1df-030dc423aa6b", x: 10488, y: -168} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M5_P2_R1")
  then(Message_13)
end

```

<!-- { section: "3105d24d-a3df-493c-8fd9-a56b7ac6a4e3", x: 10488, y: 456} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M5_P2_R2")
  then(Message_13)
end

```

<!-- { section: "86f4c694-8058-48ee-a85b-4b354202b03f", x: 10488, y: 1008} -->

```stack
card Message_13_3, "Message_13_3", code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M5_P2_R3")
  then(Message_13)
end

```

<!-- { section: "43b3aff3-3b11-4312-8ba6-e57969cc7749", x: 10560, y: -1152} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "a5672e43-14ad-42d2-a54b-a0a0cd03c3fc", x: 11280, y: 24} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13)
end

```

<!-- { section: "efb67333-0b81-41f1-b4a1-4061001cdc32", x: 10008, y: 1704} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "6e8745e5-567c-456f-96b7-7cb0a9db3fbc", x: 12312, y: 528} -->

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

<!-- { section: "5e781652-95d4-4901-b550-53f37da314b1", x: 13056, y: 552} -->

```stack
card Message_15, "Message_15", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Very empowered ✅", "Very intense", "I'm not sure 🤷"]) do
      text(
        "So, Pilar and her partner were going to make pizza but when he arrived and saw that they were alone, he told Pilar that they might as well have sex. 

Pilar doesn't want to, so she replied, \"You're making me uncomfortable, I already told you that I want to go slower. If you want, we can hug and spend some time together, but that's it.\" 

What do you think of his answer?🤔"
      )
    end

  then(Message15_1 when ref_Message_15 == "Very empowered ✅")
  then(Message15_2 when ref_Message_15 == "Very intense")
  then(Message15_3 when ref_Message_15 == "I'm not sure 🤷")
  then(Catch_all_10)
end

```

<!-- { section: "c0fac0f1-9d72-4d06-a902-938de4edaab8", x: 11832, y: -192} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14)
end

```

<!-- { section: "a1d00546-b597-4652-a8d2-2e2519ff75b4", x: 13128, y: -552} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15)
end

```

<!-- { section: "9e1ed313-5587-4135-8335-9f8ef9e20782", x: 15264, y: 552} -->

```stack
card Message_16_1, "Message_16_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_1 =
    buttons(["Next question"]) do
      text(
        "Setting limits and being assertive is never intensity, it is our opportunity to respect ourselves! Plus, we never have to feel pressure to do something we don't want to, even if we've done it before. Love is cool when both people are ready! 🤗"
      )
    end

  then(Message_17 when ref_Message_16_1 == "Next question")
  then(Catch_all_11)
end

```

<!-- { section: "3626f015-bf41-491b-9bc3-a9a6c48c9ba0", x: 15192, y: 1512} -->

```stack
card Message_16_2, "Message_16_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_2 =
    buttons(["Next question"]) do
      text(
        "If it wouldn't be easy for you to respond like Pilar, try to practice how you would do it to improve your confidence💪 Your needs are important and should be heard and respected. Talking to your friends about this can be a good step to support each other 💛"
      )
    end

  then(Message_17 when ref_Message_16_2 == "Next question")
  then(Catch_all_12)
end

```

<!-- { section: "58be1280-fde6-4db0-992e-a0ef7c89ba71", x: 15168, y: -264} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16_1)
end

```

<!-- { section: "8f94504f-3d8d-4a28-99c7-087b90792aa5", x: 14880, y: 1200} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16_2)
end

```

<!-- { section: "be8e6db9-94b9-4e77-aded-24a64fd9545a", x: 16440, y: 984} -->

```stack
card Message_17, "Message_17", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["Anyway, it worked 😡", "I don't do anything", "I talk to an adult"]) do
      text(
        "Imagine someone shares a photo of a friend and she considers \"fucking it.\" If you were in your friend's position, how would you handle your feelings and what boundaries would you set? 🤔 Remember that being assertive is important, but it is essential to do it productively, without rushing to judge or acting without knowing the whole truth."
      )
    end

  then(Message17_1 when ref_Message_17 == "Anyway, it worked 😡")
  then(Message17_2 when ref_Message_17 == "I don't do anything")
  then(Message17_3 when ref_Message_17 == "I talk to an adult")
end

```

<!-- { section: "43f64f95-849f-430c-aaa5-9494964132d8", x: 18360, y: 264} -->

```stack
card Message_18_1, "Message_18_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18_1 =
    buttons(["Follow the podcast"]) do
      text(
        "Although it is an annoying situation where you would like to do justice, remember that \"fucking\" someone can have serious consequences. Assertive communication is the ability to express your thoughts and feelings honestly and respectfully. 

Instead of acting out of anger, consider finding out what happened first and talking to a trusted adult. This can help you make better decisions 💛"
      )
    end

  then(Message_19_1 when ref_Message_18_1 == "Follow the podcast")
  then(Catch_all_13)
end

```

<!-- { section: "8c31ae9e-5e94-4c2a-8f4a-4ccae3bd8b3e", x: 18336, y: 1104} -->

```stack
card Message_18_2, "Message_18_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18_2 =
    buttons(["Follow the podcast"]) do
      text(
        "Sometimes doing nothing may seem like the calmest option, but your voice needs to be heard too. Assertive communication involves expressing your feelings and needs clearly, without getting carried away by anger 🫰 

Investigating the situation and talking to a trusted adult can give you clarity about what really happened and how to best proceed 💛"
      )
    end

  then(Message_19_1 when ref_Message_18_2 == "Follow the podcast")
  then(Catch_all_14)
end

```

<!-- { section: "8182c099-1a32-4534-863e-b10ab2ce77b3", x: 18240, y: 2232} -->

```stack
card Message_18_3, "Message_18_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18_3 =
    buttons(["Follow the podcast"]) do
      text(
        "Talking to an adult you trust is an excellent option. They can offer you a different perspective and help you communicate assertively, so you can defend your rights and express your emotions in a direct and respectful way💪

Having the experience of someone you trust can guide you to address the problem effectively and constructively, without escalating the situation unnecessarily 💛"
      )
    end

  then(Message_19_1 when ref_Message_18_3 == "Follow the podcast")
  then(Catch_all_15)
end

```

<!-- { section: "88913ca9-65a3-4b72-bea9-c625d64e1cd2", x: 17904, y: -696} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18_1)
end

```

<!-- { section: "e93a61c8-1ffd-4118-996e-830572c3905f", x: 17928, y: 1344} -->

```stack
card Catch_all_14, "Catch_all_14", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18_2)
end

```

<!-- { section: "f0062e0a-5236-4906-98d8-178e26646aee", x: 17832, y: 2664} -->

```stack
card Catch_all_15, "Catch_all_15", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18_3)
end

```

<!-- { section: "f13ecfb2-38b0-4c1d-8eef-4dedaae1d453", x: 19608, y: 1032} -->

```stack
card Message_19, "Message_19", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["I heard the audio!"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_20 when ref_Message_19 == "I heard the audio!")
  then(Catch_all_16)
end

```

<!-- { section: "4f35b60f-49e4-40ac-971e-0c7604ce70b6", x: 19512, y: 288} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_19)
end

```

<!-- { section: "8fdbbf65-f00c-4778-8eb0-b68d5da9ebd7", x: 20040, y: 864} -->

```stack
card Message_20, "Message_20", code_generator: "QUESTION" do
  ref_Message_20 =
    ask(
      "It's time to practice! How would you tell a friend or boyfriend that you don't want to do something? 

Remember that you can reply with text or voice note"
    )

  then(Branch_b1534d)
end

```

<!-- { section: "e0c724d6-e596-4503-bd86-032d54704e3d", x: 21504, y: 1008} -->

```stack
card Message_21, "Message_21", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for telling me! Remember that the more we practice how to communicate, the easier it will be to do so in complicated moments💪 Keep it up!"
  )

  then(Messge_22)
end

```

<!-- { section: "fef27856-bfc6-432a-b68f-8708aab35313", x: 22104, y: 1008} -->

```stack
card Messge_22, "Messge_22", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Messge_22 =
    buttons(["Send my stickers!"]) do
      text(
        "You completed episode 5 of our podcast! 🥳 Today I have more stickers so you can use them and help you if one day you face a situation like this."
      )
    end

  then(Message_23_sticker_1 when ref_Messge_22 == "Send my stickers!")
  then(Catch_all_17)
end

```

<!-- { section: "64728a0a-2739-4878-9a8e-f7631c8f0db7", x: 21936, y: 384} -->

```stack
card Catch_all_17, "Catch_all_17", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Messge_22)
end

```

<!-- { section: "51fabf47-afc5-48e5-bd5e-aa73032d69e8", x: 22800, y: 528} -->

```stack
card Message_23_sticker_1, "Message_23_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("f3895532-7cae-42e2-b239-e15d882a025f-Módulo5_Escudo.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "5da50a78-1076-4f0a-b368-23413f08f843", x: 23688, y: 984} -->

```stack
card Message_24, "Message_24", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["Understood! 🫡"]) do
      text(
        "It's been 5 out of 6 days of streak in the podcast challenge! Don't forget to listen to us tomorrow, only 1 day left 💥"
      )
    end

  then(Message_25 when ref_Message_24 == "Understood! 🫡")
  then(Catch_all_18)
end

```

<!-- { section: "b1932f3f-3bea-4c3f-9372-2d50e67a96a8", x: 23184, y: 360} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_24)
end

```

<!-- { section: "a4ad70da-de76-439c-b829-649dc22294aa", x: 24288, y: 984} -->

```stack
card Message_25, "Message_25", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Set limits", "Say kesi and keno!", "Fight healthy"]) do
      text(
        "Now, I'm going to leave you this challenge: For tomorrow, talk to someone about a couple you know or a famous one who is an example of good communication 🤘 

What specific element of communication do you want to focus on?"
      )
    end

  then(Message27_1 when ref_Message_25 == "Set limits")
  then(Message27_2 when ref_Message_25 == "Say kesi and keno!")
  then(Message27_3 when ref_Message_25 == "Fight healthy")
  then(Catch_all_19)
end

```

<!-- { section: "0a8e6cca-a13f-440c-abf4-93c7caa5af3f", x: 23976, y: 360} -->

```stack
card Catch_all_19, "Catch_all_19", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_25)
end

```

<!-- { section: "44e21329-8c87-4a1a-8d43-aa994dd2579d", x: 25632, y: 1176} -->

```stack
card Message_26, "Message_26", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["Understood 🌸"]) do
      text(
        "Ok friend, that's all for today. Get ready because in tomorrow's episode (the last 😭) we will talk about how we can create a safe plan for risky situations!⚠️"
      )
    end

  then(Message_27 when ref_Message_26 == "Understood 🌸")
  then(Catch_all_20)
end

```

<!-- { section: "3a6f99f1-9993-47a4-8ef5-9f1187a04604", x: 26304, y: 1152} -->

```stack
card Message_27, "Message_27", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_6cade8)
end

```

<!-- { section: "a5e67f95-e031-4ae6-8fb6-80fa02760894", x: 25848, y: 360} -->

```stack
card Catch_all_20, "Catch_all_20", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_26)
end

```

<!-- { section: "ad7c1e57-4e21-47ec-bacf-78a4738823de", x: 8592, y: -888} -->

```stack
card Catch_all_21, "Catch_all_21", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "0874252e-c650-46fe-b7ab-16c11dca01a6", x: 26760, y: 1128} -->

```stack
card Profile_6cade8, "Profile_6cade8", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_5")
  then(ModuleCompleted)
end

```

<!-- { section: "bb7cf986-b5b0-4e4b-b96a-c55a126d1aa3", x: 7752, y: 144} -->

```stack
card Message_11_1, "Message_11_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M5_P2")
  then(Message_11)
end

```

<!-- { section: "0bd43b6c-bacb-4afb-92d0-ed19315a1125", x: 11088, y: 528} -->

```stack
card Message_13, "Message_13", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Next question"]) do
      text("When the audio ends, press the next question button.")
    end

  then(Message_14_1 when ref_Message_13 == "Next question")
  then(Catch_all_7)
end

```

<!-- { section: "c20cf8b2-2b2c-4eab-8449-a66e3ff87e4f", x: 11688, y: 552} -->

```stack
card Message_14_1, "Message_14_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M5_P3")
  then(Message_14)
end

```

<!-- { section: "4c1653b3-810d-4cb3-ab60-c6a004ebb2b8", x: 19128, y: 1056} -->

```stack
card Message_19_1, "Message_19_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M5_P4")
  then(Message_19)
end

```

<!-- { section: "06109207-d4e5-4e26-8413-1e096f771c62", x: 22776, y: 984} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("db05fa4c-e6fe-4aec-bb66-1c543e2cb52d-Módulo5_EstoyIncomoda.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "2985b032-5b50-499b-887c-14fbe56619c6", x: 22752, y: 1488} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("d72e9a1f-b937-44a5-a000-4365e91c31f5-Módulo5_Ganamos.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "43908efc-afe7-4297-afa4-ead0ffdef06a", x: 22776, y: 2088} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("bc3686a1-85e3-47bf-b68b-ccb18fc84f6c-Módulo5_Llamame.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "1f86aff5-6383-432b-8f1f-1eedde527e66", x: 23304, y: 1992} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("3c2035c7-d4ad-4e1c-bacc-55e9ff2d4423-Módulo5_Yallegue.png")
  text("")
  then(Message_24)
end

```

<!-- { section: "890bb6d1-fb6f-43c3-b11b-8bbf9d3af42a", x: 20528, y: 744} -->

```stack
card Branch_b1534d, "Branch_b1534d", code_generator: "CONDITIONALS" do
  then(Message20 when @event.message.type == "audio")
  then(Message20 when @event.message.type == "text")
  then(Text_c844df)
end

```

<!-- { section: "252348a3-c0d9-4e20-9176-04dd5e4fb4ef", x: 20520, y: 1128} -->

```stack
card Text_c844df, "Text_c844df", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_20)
end

```

<!-- { section: "99dd46da-2b76-4ddc-8bc8-9aa8dc31210f", x: 2376, y: 552} -->

Emoji does not show up

<!-- { section: "6590e967-ebe6-46b5-bb89-de8ce8e0b28f", x: 4536, y: 552} -->

Emoji does not show up

<!-- { section: "a118d329-a2cd-4d6d-854b-c54c173cb1e7", x: 5400, y: 336} -->

audio file missing here

<!-- { section: "b707dae4-7ac9-4614-af2f-a67939fe2156", x: 9024, y: 1032} -->

save users response here    need a variable /insight name

We cannot have audio as button messages, will need extra copy here

<!-- { section: "8bbdc975-21df-4513-897b-2d32f3fa5f34", x: 11688, y: 720} -->

missing audio here^

<!-- { section: "a650a181-50ba-49a9-b4cf-7b3c54b4b504", x: 17256, y: 1944} -->

save users response here    need a variable /insight name

<!-- { section: "91913f41-de7c-41cd-8af4-bd1d727508c3", x: 19368, y: 1224} -->

audio missing here

<!-- { section: "296c283a-87da-45a1-b416-c270b373bd11", x: 23664, y: 1320} -->

emoji does not show up

<!-- { section: "1e838c13-0cf4-4ef7-80ac-a8aee94fc777", x: 27768, y: 1464} -->

**@Buhle**

Schedule Quiz Post Module 5 to start next day (6pm ,
Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "c218e50a-2da7-4d98-8c2c-0dd6d6971bfa", x: -552, y: 552} -->

**@Buhle**

Please add the other thingies here^

<!-- { section: "3c4fae1e-40b9-4021-9dcf-6edc046b0aae", x: 528, y: 432} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module5_started (yes)

<!-- { section: "cc8c9a2b-218a-49e3-bd6d-bd56a0e9accc", x: 1392, y: 432} -->

**@Buhle**

Please save these variables here

<!-- { section: "260a9b54-964b-4520-8d5b-33c25660eb18", x: 6792, y: 408} -->

**@Buhle**

Save user response here

This is a DS field, not sure which you need so you have both

**DS note:** Flow result: module5_boundaries {user input}

<!-- { section: "9cba569d-0232-4a78-8b84-921f09334597", x: 8856, y: 600} -->

**@Buhle**

Please save variables here

<!-- { section: "dc4f16ec-85fa-4371-9ab9-ee42ac295a27", x: 13368, y: 1176} -->

**@Buhle**

Please save the insights here

<!-- { section: "231e55b4-e402-4d83-bf20-efdf33acbc53", x: 16680, y: 1560} -->

**@Buhle**

Please save the insights here

<!-- { section: "040d65fb-b09a-472c-b4f2-3023cf398f2f", x: 20760, y: 1368} -->

**@Buhle**
Please save the insights here

its a DS thing so added in the code block just in case

**DS note:** Flow result: module5_boundaries2 {user input}

<!-- { section: "427250ac-6b79-4470-b5e0-a4473c5ab1ac", x: 24192, y: 1560} -->

**@Buhle**

Please save insights here

<!-- { section: "e9e24388-ebba-486e-a472-50c4d0cb6af2", x: 27048, y: 1392} -->

**@Buhle**

**DS note:** Flow result: module5_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "fc7c1e95-c186-4a4c-a078-5d1b8f3448a8", x: 26112, y: 1440} -->

Update contact field, contact module = Module 5 ✅

<!-- { section: "3721eaee-3f48-4dbc-a036-968b48a658dc", x: 22272, y: 1368} -->

**@Tam**

Images here are pngs

<!-- { section: "d85bf8a1-c343-4afa-bab9-590c0239035b", x: 14352, y: 1608} -->

**16.3 is missing here**

<!-- { section: "eb95cb08-37e6-4296-a55b-3fbac62c2d3b", x: 7896, y: 480} -->

audio file missing

<!-- { section: "7d0c3f09-d26c-4d4f-b97c-e0dbb6d3f86c", x: 27408, y: 960} -->

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

<!-- { section: "93e1a921-a953-41df-b7a2-c2f0a50cd4ee", x: 600, y: -24} -->

```stack
card Message1 do
  write_result("module5_started", "yes")
  then(Message_2)
end

```

<!-- { section: "9e5a37aa-008f-45b9-b84d-5538b776a262", x: 21048, y: 960} -->

```stack
card Message20 do
  write_result("module5_boundaries2", "@ref_message_20")
  then(Message_21)
end

```

<!-- { section: "d4eab0d1-c755-4f43-a53d-9d99f1b8702c", x: 1704, y: -168} -->

```stack
card Message2_1 do
  write_result("module5_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "55766e53-fad2-4fd0-9a56-93f611c12da8", x: 1704, y: 216} -->

```stack
card Message2_2 do
  write_result("module5_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "99bb6b30-60de-4df7-8a79-84fbd21929a3", x: 6792, y: 72} -->

```stack
card Message9 do
  write_result("module5_boundaries", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "fef6d0d8-adad-446b-afe7-265084f20d5f", x: 9240, y: -216} -->

```stack
card Message12_1 do
  write_result("module5_beliefs", "a")
  then(Message_13_1)
end

```

<!-- { section: "6b64fd79-15ac-4dbc-96c0-0182db0be1b6", x: 9240, y: 144} -->

```stack
card Message12_2 do
  write_result("module5_beliefs", "b")
  then(Message_13_2)
end

```

<!-- { section: "8205daed-4044-46f5-a2a5-917c4ffafee5", x: 9240, y: 528} -->

```stack
card Message12_3 do
  write_result("module5_beliefs", "c")
  then(Message_13_3)
end

```

<!-- { section: "9b7847fb-79bb-4d18-84d5-b64823130338", x: 13872, y: 456} -->

```stack
card Message15_1 do
  write_result("module5_attitudes", "a")
  then(Message_16_1)
end

```

<!-- { section: "10cfe1f5-ce26-4507-9ff6-a9dd03f069e2", x: 13848, y: 840} -->

```stack
card Message15_2 do
  write_result("module5_attitudes", "b")
  then(Message_16_2)
end

```

<!-- { section: "b724da04-9e27-4e82-baa0-2bd65356a145", x: 13872, y: 1224} -->

```stack
card Message15_3 do
  write_result("module5_attitudes", "c")
  then(Message_16_2)
end

```

<!-- { section: "94e299b0-19ff-4bd8-baf0-a68ade14064a", x: 17160, y: 720} -->

```stack
card Message17_1 do
  write_result("module5_attitudes2", "a")
  then(Message_18_1)
end

```

<!-- { section: "101a00db-65f9-4df2-b2ea-a9551ee63601", x: 17160, y: 1104} -->

```stack
card Message17_2 do
  write_result("module5_attitudes2", "b")
  then(Message_18_2)
end

```

<!-- { section: "e15444c0-fc29-4bb0-a806-abde413ac777", x: 17232, y: 1512} -->

```stack
card Message17_3 do
  write_result("module5_attitudes2", "c")
  then(Message_18_3)
end

```

<!-- { section: "ea0a273c-db1e-4ae3-b587-41a06a2036d2", x: 24936, y: 744} -->

```stack
card Message27_1 do
  write_result("module5_behavioral_activation", "a")
  then(Message_26)
end

```

<!-- { section: "17e18b06-0176-4790-9e69-263090bd7642", x: 24912, y: 1152} -->

```stack
card Message27_2 do
  write_result("module5_behavioral_activation", "b")
  then(Message_26)
end

```

<!-- { section: "e2fb205f-2c5c-4c0f-aa4e-9476ea66510f", x: 24960, y: 1632} -->

```stack
card Message27_3 do
  write_result("module5_behavioral_activation", "c")
  then(Message_26)
end

```

<!-- { section: "", x: -772, y: 96} -->

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
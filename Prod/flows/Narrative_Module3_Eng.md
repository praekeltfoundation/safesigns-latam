<!-- { section: "5eb7a64c-ffd3-4992-bc02-c0d5afba708d", x: -1608, y: -48} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_2" and contact.onboarding_complete == true and
       contact.arm == "NARRATIVE"

```

<!-- { section: "0152dd20-9382-45f9-b5c9-b53f6aa0562d", x: -576, y: 0} -->

```stack
card Message_1_, "Message_1_", code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 Welcome to the third episode of Pilar's story. This is getting more and more intense!"
  )

  then(Message1)
end

```

<!-- { section: "73e53b46-b102-490a-a208-b5873a6b8e12", x: -744, y: 576} -->

```stack
card Branch_02b583, "Branch_02b583", code_generator: "CONDITIONALS" do
  then(
    RESERVED_DEFAULT_CARD
    when contact.arm == "NARRATIVE" and contact.onboarding_complete == true and
           contact.contact_module == "MODULE_2"
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "bc82c809-d19b-4e35-97fb-9f86e967f852", x: 552, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time", "Very good 👍"]) do
      text(
        "Yesterday's challenge was to apply a strategy to feel better at some point during the day 🧘🎵 ✍️ How did it go?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time")
  then(Message2_2 when ref_Message_2 == "Very good 👍")
  then(Catch_all_1)
end

```

<!-- { section: "c30ed8fa-af35-4ebd-886c-a45b38f4b492", x: 672, y: -600} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "5e486c59-e03c-4cfe-9c4a-c284ab3c0ed7", x: 1512, y: 72} -->

```stack
card Message_3_1, "Message_3_1", code_generator: "TEXT_MESSAGE" do
  text("Don't worry, you can catch up today!")
  then(Message_4)
end

```

<!-- { section: "e7b0e9ae-80ca-4847-92a9-26e6b0024089", x: 1512, y: 264} -->

```stack
card Message_3_2, "Message_3_2", code_generator: "TEXT_MESSAGE" do
  text("Incredible! I bet it will show in your answers today.")
  then(Message_4)
end

```

<!-- { section: "b5fbdacd-3275-4427-bf1c-662130974d7c", x: 1944, y: 96} -->

```stack
card Message_4, "Message_4", code_generator: "TEXT_MESSAGE" do
  text(
    "Do you think that in this third episode we will discover if Pilar has finally appeared? 😲 We'll see!"
  )

  then(Message_5)
end

```

<!-- { section: "5e55f6a5-abd3-4683-962c-5a39df8f7b41", x: 2616, y: -648} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_5)
end

```

<!-- { section: "b642436b-7381-4d66-8f4d-864cddc8df77", x: 2328, y: 96} -->

```stack
card Message_5, "Message_5", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Button 1"]) do
      text(
        "Remember that if something about Pilar's story or a question makes you feel uncomfortable, you can stop and come back when you feel ready. It is very important to me that you feel good!"
      )
    end

  then(Messge_6 when ref_Message_5 == "Button 1")
  then(Catch_all_2)
end

```

<!-- { section: "f3811d37-218d-405e-ba5d-a858d7ae6948", x: 2736, y: 96} -->

```stack
card Messge_6, "Messge_6", code_generator: "QUESTION" do
  ref_Messge_6 =
    ask(
      "Before listening to the third episode, I would like to know something. Having someone to trust is amazing. What characteristics do you think someone should have for you to consider them a good friend? Write or send by voice note at least two characteristics"
    )

  then(Branch_d63adb)
end

```

<!-- { section: "dd4129da-0ce3-4752-bd40-ba9f142964c6", x: 4752, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8_1)
end

```

<!-- { section: "b89954f7-c600-4e61-86ac-a1a031f17ae3", x: 3936, y: 96} -->

```stack
card Message_7, "Message_7", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for your response! Now, let's listen to the audio. Ready? When the audio ends, press the button I heard the audio!"
  )

  then(Message_8)
end

```

<!-- { section: "5cad06c5-bc41-436e-b9a2-208389172960", x: 4320, y: 96} -->

```stack
card Message_8, "Message_8", code_generator: "TEXT_MESSAGE" do
  text("Send audio file NARRATIVE - CHAPTER 3 - PART 1")
  then(Message_8_1)
end

```

<!-- { section: "e34945d5-ca52-4425-b6b3-425fdc2ea048", x: 5184, y: 96} -->

```stack
card Message_9, "Message_9", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["They don't help ❌", "They have a point", "They are very hard "]) do
      text(
        "In the episode we hear how \"the friend\" reacts when Pilar tells her everything that happened. She tells him phrases like: \"How many times did I tell you that he wasn't for you... I warned you... Look how you're crying, that makes you stupid.\" What do you think of these types of comments?"
      )
    end

  then(Message9_1 when ref_Message_9 == "They don't help ❌")
  then(Message9_2 when ref_Message_9 == "They have a point")
  then(Message9_3 when ref_Message_9 == "They are very hard ")
  then(Catch_all_4)
end

```

<!-- { section: "b7c3737a-88df-4f02-9f55-2ed8a2d63f87", x: 6408, y: -408} -->

```stack
card Message_10_1, "Message_10_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_1 =
    buttons(["Next audio"]) do
      text(
        "You're right, those comments aren't helpful. Instead of pointing out what she did wrong, her friend could say things like, \"I understand you feel bad, I'm here for you. How can I help you? You're not alone, we can find a solution together.\" Showing support without judging her is a better way to provide help, as it will make her feel understood and confident in talking to her friend."
      )
    end

  then(Message_11 when ref_Message_10_1 == "Next audio")
  then(Catch_all_22)
end

```

<!-- { section: "f88e9659-0a07-41d8-9145-6ddd822a10e0", x: 7176, y: 504} -->

```stack
card Message_11, "Message_11", code_generator: "TEXT_MESSAGE" do
  text("Send audio NARRATIVO - CAPITULO 2 -PARTE 2")
  then(Message_11_1)
end

```

<!-- { section: "3be64bbe-a4df-4e90-ab71-66af1b94318c", x: 7728, y: 480} -->

```stack
card Message_11_1, "Message_11_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_12 when ref_Message_11_1 == "I heard the audio")
  then(Catch_all_5)
end

```

<!-- { section: "e4ba43d4-22ac-4ba3-bdae-f7bd603095b8", x: 5304, y: -648} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_9)
end

```

<!-- { section: "ba34b9be-7981-4fd9-8126-78c5ef5d79b5", x: 7344, y: -696} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11_1)
end

```

<!-- { section: "5e0da20d-4247-429a-80bc-b3267c2a665f", x: 9240, y: 432} -->

```stack
card Message_13, "Message_13", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Follow the podcast "]) do
      text(
        "Thanks for sharing what you think! Now I will tell you a situation that Pilar could face in the future."
      )
    end

  then(Message_14 when ref_Message_13 == "Follow the podcast ")
end

```

<!-- { section: "1179c01d-922e-46ec-9602-a7ee10ab6122", x: 8232, y: 456} -->

```stack
card Message_12, "Message_12", code_generator: "QUESTION" do
  ref_Message_12 =
    ask(
      "The neighbor has commented that sometimes the girls are very exaggerated and for any small problem they disappear. What do you think of this? Do you think it's true?"
    )

  then(Message12)
end

```

<!-- { section: "c7eda90b-82bd-4bbb-aa66-6eef4e6b57f5", x: 11160, y: 1608} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15_3)
end

```

<!-- { section: "16a42563-ec26-4c78-9ade-b28db5192631", x: 11232, y: 432} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15_2)
end

```

<!-- { section: "a91d8e5c-8198-4c72-9b8e-7b49ddeb82a2", x: 9936, y: 432} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["Let's look for help", "I don't believe you ", "Makes you feel dumb"]) do
      text(
        "Imagine that one day Pilar enters her living room and sees her friend Mari who is crying. Mari secretly tells her that her boyfriend is blackmailing her by saying that he will share intimate photos if she breaks up with him. If Pilar is a good friend, how do you think she would react?"
      )
    end

  then(Message14_1 when ref_Message_14 == "Let's look for help")
  then(Message14_2 when ref_Message_14 == "I don't believe you ")
  then(Message14_3 when ref_Message_14 == "Makes you feel dumb")
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

<!-- { section: "97965a8f-c76c-44d5-bba6-4269690129a5", x: 11424, y: -144} -->

```stack
card Message_15_1, "Message_15_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_1 =
    buttons(["Next question"]) do
      text(
        "Offering to get help is a great first step. Be sure to look for trusted people or professionals who can help. You can also accompany her to find resources and show her that you are there to support her."
      )
    end

  then(Message_16 when ref_Message_15_1 == "Next question")
  then(Catch_all_10)
end

```

<!-- { section: "566e1bac-8856-4a21-9a95-a8aa68ddffc8", x: 10800, y: -816} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15_1)
end

```

<!-- { section: "0ed0d920-45be-40fb-ae4a-99d00de6eae2", x: 11784, y: -1200} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "920e4fd2-b99f-4f69-affb-f83a5a3ddd8d", x: 13752, y: -1272} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "f3ff25a4-f7a1-4c2f-ac4d-181495c8b432", x: 12432, y: -1176} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "f3786688-6310-4ce5-9e69-b1c7346310e5", x: 12648, y: -1104} -->

```stack
card Catch_all_14, "Catch_all_14", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "d9855d03-092f-45f1-851d-0cc05da8793e", x: 12648, y: -984} -->

```stack
card Catch_all_15, "Catch_all_15", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "44010249-c410-488c-8e3c-756240354b81", x: 12168, y: 696} -->

```stack
card Message_16, "Message_16", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["The fights 🥊", "The gossip 🗣️", "The support 🤝"]) do
      text("In your group of friends, what is the most common thing that occurs?")
    end

  then(Message16_1 when ref_Message_16 == "The fights 🥊")
  then(Message16_2 when ref_Message_16 == "The gossip 🗣️")
  then(Message16_3 when ref_Message_16 == "The support 🤝")
  then(Catch_all_16)
end

```

<!-- { section: "2eee4280-ad50-4c6a-94fe-41ccddf48158", x: 12408, y: -360} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16)
end

```

<!-- { section: "a8a868da-3d2b-4c62-983f-f942d48d4e72", x: 13656, y: 840} -->

```stack
card Message_17, "Message_17", code_generator: "TEXT_MESSAGE" do
  text(
    "Each group of friends has its own dynamic, and it is useful to reflect on which aspects predominate. If fighting or gossip is common, consider how it could be addressed to improve the relationship. If support is most common, it's a great sign of a strong and supportive group!"
  )

  then(Message_18)
end

```

<!-- { section: "2fdd8deb-02fc-4d65-9344-41a61b1b80d0", x: 18672, y: -792} -->

```stack
card Catch_all_17, "Catch_all_17", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "83ed8ff3-6b97-4910-986c-0a988abb1271", x: 14136, y: 816} -->

```stack
card Message_18, "Message_18", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_18 =
    buttons(["Send my stickers!"]) do
      text(
        "Very good! Have you heard episode 3 of Pilar's story 🥳 They are complex topics, so to help you navigate them, I leave you some great stickers on this topic that you can use to respond if you experience something similar."
      )
    end

  then(Message_19_sticker_1 when ref_Message_18 == "Send my stickers!")
  then(Catch_all_18)
end

```

<!-- { section: "91c6eb4a-2475-48e9-91c4-270f6e5035ee", x: 14880, y: -24} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_18)
end

```

<!-- { section: "677f0805-ee40-4b7b-89e0-227910b8589e", x: 14616, y: 960} -->

```stack
card Message_19_sticker_1, "Message_19_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("61d2646c-d4aa-4e03-9404-675a8ef6e77f-Módulo3_Ayvv.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "51423c4d-1720-4681-aca1-f4939c2c1ac3", x: 16416, y: 336} -->

```stack
card Catch_all_19, "Catch_all_19", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "3d0ee0f9-614d-434d-b40b-f446d9654962", x: 16512, y: 888} -->

```stack
card Message_20, "Message_20", code_generator: "QUESTION" do
  ref_Message_20 =
    ask(
      "Today we heard some tips that we can use to help someone feel better... What phrases can you think of that you could say to a friend who is going through a bad time?"
    )

  then(Message20)
end

```

<!-- { section: "95e057e0-d7d4-4324-8051-17946dc538c9", x: 17976, y: 1032} -->

```stack
card Message_22, "Message_22", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["Friend 👯‍♀️", "Mom or dad 👩‍👧", "Family 👩🧑"]) do
      text(
        "Now, I'm going to leave you this challenge: For tomorrow, reflect on who would be the person for you who can offer you a safe space to tell your things and help you. Who is that person for you?"
      )
    end

  then(Message22_1 when ref_Message_22 == "Friend 👯‍♀️")
  then(Message22_2 when ref_Message_22 == "Mom or dad 👩‍👧")
  then(Message22_3 when ref_Message_22 == "Family 👩🧑")
  then(Catch_all_20)
end

```

<!-- { section: "f37ac58e-9b80-49f4-ae4e-c3173878282d", x: 18024, y: 576} -->

```stack
card Catch_all_20, "Catch_all_20", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_22)
end

```

<!-- { section: "5933f60a-532b-4f4b-8022-4c4f39f630e7", x: 19536, y: 1200} -->

```stack
card Message_23, "Message_23", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["I want to know!🧐"]) do
      text(
        "Ok friend, that's all for today. Get ready! Because tomorrow's episode is going to be amazing! Will we finally discover what happened to Pilar to make her disappear?"
      )
    end

  then(Message_24 when ref_Message_23 == "I want to know!🧐")
  then(Catch_all_21)
end

```

<!-- { section: "c13b5eeb-1005-4b90-9b65-2d3fc96ffb1f", x: 20328, y: 1272} -->

```stack
card Message_24, "Message_24", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_fa3d29)
end

```

<!-- { section: "bdb1c032-5534-4111-8ad2-f09101461059", x: 19512, y: 528} -->

```stack
card Catch_all_21, "Catch_all_21", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_23)
end

```

<!-- { section: "35d600c3-48b9-445a-a35d-eb0135b2824f", x: 4704, y: 96} -->

```stack
card Message_8_1, "Message_8_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8_1 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_9 when ref_Message_8_1 == "I heard the audio")
  then(Catch_all_3)
end

```

<!-- { section: "9b50f04d-2966-406f-a879-cd191798123c", x: 6384, y: 360} -->

```stack
card Message_10_2, "Message_10_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_2 =
    buttons(["Next audio"]) do
      text(
        "It's natural to want to warn a friend, but instead of pointing out what she did wrong, you could say things like, \"I understand you're feeling bad, I'm here for you. How can I help you? You're not alone, we can find a solution together.\" \". Showing support without judging her is a better way to provide help, as it will make her feel understood and confident in talking to her friend."
      )
    end

  then(Message_11 when ref_Message_10_2 == "Next audio")
  then(Catch_all_23)
end

```

<!-- { section: "fafa660b-6b5f-40c0-b836-e04f5ccf4114", x: 6336, y: 1344} -->

```stack
card Message_10_3, "Message_10_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_3 =
    buttons(["Next audio"]) do
      text(
        "Exactly, those comments can be very harsh. Instead of pointing out what she did wrong, her friend could say things like, \"I understand you feel bad, I'm here for you. How can I help you? You're not alone, we can find a solution together.\" Showing support without judging her is a better way to provide help, as it will make her feel understood and confident in talking to her friend."
      )
    end

  then(Message_11 when ref_Message_10_3 == "Next audio")
  then(Catch_all_24)
end

```

<!-- { section: "1ace5e2c-c9a7-4407-980a-a657f7341fe7", x: 6384, y: -768} -->

```stack
card Catch_all_22, "Catch_all_22", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10_1)
end

```

<!-- { section: "ec0ce2d1-b02a-4152-9ead-9d4de7555da3", x: 5784, y: 528} -->

```stack
card Catch_all_23, "Catch_all_23", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10_2)
end

```

<!-- { section: "fb813787-a453-4535-bb2d-028945680ed8", x: 6336, y: 1104} -->

```stack
card Catch_all_24, "Catch_all_24", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10_3)
end

```

<!-- { section: "f845c745-cf1a-4b84-a715-9a1fd6900de9", x: 11088, y: 744} -->

```stack
card Message_15_2, "Message_15_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_2 =
    buttons(["Next question"]) do
      text(
        "Some common phrases like \"I don't believe you!\" They can make the person feel questioned. It is important to take your friend's emotions and experiences seriously. Consider supporting her in seeking professional help and being a listening ear so she feels supported."
      )
    end

  then(Message_16 when ref_Message_15_2 == "Next question")
  then(Catch_all_8)
end

```

<!-- { section: "239f23b8-319b-4128-b89e-5865e8c92a81", x: 11064, y: 1920} -->

```stack
card Message_15_3, "Message_15_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15_3 =
    buttons(["Next question"]) do
      text(
        "It is important to avoid comments that could make your friend feel even worse. Instead, offer support and guidance in seeking professional help. Empathy and understanding are key to helping in difficult situations."
      )
    end

  then(Message_16 when ref_Message_15_3 == "Next question")
  then(Catch_all_6)
end

```

<!-- { section: "b81e0f3c-c800-47b1-a985-f3e2bc5d7a9b", x: 17400, y: 984} -->

```stack
card Message_21, "Message_21", code_generator: "TEXT_MESSAGE" do
  text("It's good that you're already thinking about how to best support a friend!")
  then(Message_22)
end

```

<!-- { section: "1ccda6fd-bca6-4773-b911-80084df705c5", x: 20816, y: 1272} -->

```stack
card Profile_fa3d29, "Profile_fa3d29", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_3")
  then(ModuleCompleted)
end

```

<!-- { section: "47d32a01-306d-41c5-a542-684f8814c4c1", x: 15072, y: 480} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("5ecf87c4-c81c-400d-a817-dcb45028c683-Módulo3_Hablemos.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "878fbe64-e2b9-46f4-b3a1-e63ed1d7f05c", x: 15432, y: 936} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("42956889-0c31-4a57-a7c8-c76d5b99778e-Módulo3_LasChicas.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "fdff0e35-4cfc-49a5-9f64-e13bfc054916", x: 15768, y: 360} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("42e77a61-ab48-4676-b3fa-cab76591bfc2-Módulo3_Rapido.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "4ced234c-8d27-4658-9c44-6f1daad280d2", x: 16104, y: 936} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("38b46442-f5d7-432b-96e9-1bde427da109-Módulo3_Siempre.png")
  text("")
  then(Message_20)
end

```

<!-- { section: "5a003645-e120-425f-b5f2-ee63fdbad246", x: 3120, y: 96} -->

```stack
card Branch_d63adb, "Branch_d63adb", code_generator: "CONDITIONALS" do
  then(Message6 when @event.message.type == "audio")
  then(Message6 when @event.message.type == "text")
  then(Text_daa618)
end

```

<!-- { section: "505fa371-9db0-4a7e-b3a6-a11b000a701f", x: 2976, y: 528} -->

```stack
card Text_daa618, "Text_daa618", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Messge_6)
end

```

<!-- { section: "7565dad1-ac40-4ceb-87db-365444511924", x: 10032, y: 1032} -->

**@Buhle**

save variable/insights here

<!-- { section: "91c03f95-6b1b-4d0f-8d7c-ae2d4e7947f0", x: 14928, y: 1416} -->

**@Tam**

stickers here are pngs

<!-- { section: "4f4424f8-616b-4efd-8f13-64ab50e52714", x: 1104, y: 600} -->

**@Buhle**

Please save the variable here

<!-- { section: "d6937677-9ab1-4e47-b320-afe2d1c21628", x: -1176, y: 480} -->

**@Buhle**

We need some variables/rules here, let me know if I should do them or of you are okay to do them

Please add the other thingies here^

<!-- { section: "e54056f6-e64f-4ab6-aa99-78c62096f52b", x: 3552, y: 504} -->

**@Buhle**

save users response here

<!-- { section: "624d7309-09ce-4244-9cf1-97c3ea910c61", x: 5280, y: 720} -->

**@Buhle**

save insight here

<!-- { section: "cc40d983-44e3-4f03-a579-936875c1675e", x: 8544, y: 840} -->

**@Buhle**

Save users response here

<!-- { section: "84a23830-11da-4dec-948f-c4d459c87090", x: 12216, y: 1056} -->

**@Buhle**

please save insights here

<!-- { section: "1350121a-75c7-4f18-b71b-2bb79156d8b1", x: 17016, y: 1248} -->

**@Buhle**

Please save user response here,

DS note: Flow result: module3_social_support2 {user input}

<!-- { section: "2adb0f35-f635-40d8-b675-d97a2e1e2b78", x: 72, y: 408} -->

**@buhle**

Please save the DS note here,

DS note: Flow result: module3_started (yes)

<!-- { section: "8ed6bcb9-3ad2-40e4-af43-0bfb6ea47b68", x: 20784, y: 1488} -->

Update contact field, contact module = Module 3✅

<!-- { section: "d99575b0-3185-499d-bad3-e814610f1b45", x: 21336, y: 1704} -->

**@Buhle**

DS note: Flow result: module3_completed (yes)
I added in a code block for you above, please dlt the one you arent using

<!-- { section: "1de1ca29-291b-48df-88f6-67c91acd073c", x: 21984, y: 1584} -->

**@Buhle**

Schedule Quiz Post Module 3 to start next day (6pm , Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "50779478-ef10-4778-a05a-e736eb230213", x: 18120, y: 1512} -->

**@Buhle**

Please save insights here

<!-- { section: "32a1ec17-ffe6-499d-a77c-ac8e5c8fa772", x: 19272, y: 1680} -->

fuse the jump is big from m22 to 28 in numbering

<!-- { section: "f1286030-2679-4e46-aa44-7157f6eff60e", x: 16896, y: 840} -->

```stack
card Message20 do
  write_result("module3_social_support2", "@ref_message_20")
  then(Message_21)
end

```

<!-- { section: "9d0feec2-7f59-496b-b8cd-70aa4d0b1419", x: 24, y: 0} -->

```stack
card Message1 do
  write_result("module3_started", "yes")
  then(Message_2)
end

```

<!-- { section: "90dce161-d8ce-47a0-a42a-ffb8af36aafa", x: 21408, y: 1200} -->

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

<!-- { section: "e13eee42-8a3c-49f4-ab2a-169826694d5c", x: 1080, y: -408} -->

```stack
card Message2_1 do
  write_result("module3_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "997ada15-3ffe-42e6-b9cf-59b879ac2f26", x: 1104, y: 240} -->

```stack
card Message2_2 do
  write_result("module3_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "645e6784-da3f-4d86-a4ae-52d4fc757ce2", x: 3480, y: 24} -->

```stack
card Message6 do
  write_result("module3_social_support", "b")
  then(Message_7)
end

```

<!-- { section: "a06397a1-6f0e-42ab-86c6-ad4befe6f3fb", x: 5760, y: -360} -->

```stack
card Message9_1 do
  write_result("module3_beliefs", "a")
  then(Message_10_1)
end

```

<!-- { section: "e39936d1-b2e1-47e4-804b-e0903a0dd869", x: 5856, y: 144} -->

```stack
card Message9_2 do
  write_result("module3_beliefs", "b")
  then(Message_10_2)
end

```

<!-- { section: "adfbc25c-f43e-4eab-bb27-31c56ab65ee7", x: 5520, y: 744} -->

```stack
card Message9_3 do
  write_result("module3_beliefs", "c")
  then(Message_10_3)
end

```

<!-- { section: "81f97f8b-d8f3-4e25-b6e7-92088764cd64", x: 8736, y: 408} -->

```stack
card Message12 do
  write_result("module3_gender_attitudes", "@ref_message_12")
  then(Message_13)
end

```

<!-- { section: "cd23ec72-ecf3-4fd9-b568-64ba29152520", x: 10560, y: -96} -->

```stack
card Message14_1 do
  write_result("module3_attitudes", "a")
  then(Message_15_1)
end

```

<!-- { section: "618ec61a-2de4-41a9-8f9b-76cdb33ad097", x: 10608, y: 840} -->

```stack
card Message14_2 do
  write_result("module3_attitudes", "b")
  then(Message_15_2)
end

```

<!-- { section: "ada5102c-fe96-4d5e-bf25-50f208d3a332", x: 10536, y: 1512} -->

```stack
card Message14_3 do
  write_result("module3_attitudes", "c")
  then(Message_15_3)
end

```

<!-- { section: "00769b65-5520-4adb-8cb1-f26b391c7dba", x: 12840, y: 336} -->

```stack
card Message16_1 do
  write_result("module3_social_norms", "a")
  then(Message_17)
end

```

<!-- { section: "dfc50551-0f44-4ff0-9cae-8f6d5ff7dad7", x: 12840, y: 696} -->

```stack
card Message16_2 do
  write_result("module3_social_norms", "b")
  then(Message_17)
end

```

<!-- { section: "9aa4ebeb-1aa1-4b20-9a59-c0d4f14a4027", x: 12840, y: 1056} -->

```stack
card Message16_3 do
  write_result("module3_social_norms", "c")
  then(Message_17)
end

```

<!-- { section: "ebd5d2eb-2792-4e3a-8622-2e1a54d11a1c", x: 18696, y: 720} -->

```stack
card Message22_1 do
  write_result("module3_behavioral_activation", "a")
  then(Message_23)
end

```

<!-- { section: "5e932c17-a8d6-431b-b19b-cfc94b34239a", x: 18768, y: 1128} -->

```stack
card Message22_2 do
  write_result("module3_behavioral_activation", "b")
  then(Message_23)
end

```

<!-- { section: "456573cd-4fad-4fcb-8409-2f745cd76100", x: 18768, y: 1488} -->

```stack
card Message22_3 do
  write_result("module3_behavioral_activation", "c")
  then(Message_23)
end

```

<!-- { section: "", x: -1108, y: 0} -->

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
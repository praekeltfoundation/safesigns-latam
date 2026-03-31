<!-- { section: "95a261ae-7fa4-4705-838f-4d1969599792", x: -1488, y: -24} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "gm2")

```

<!-- { section: "7ded634b-f3a0-40b1-9cdf-1b5eadd45b6f", x: -840, y: 24} -->

```stack
card Branch_78efe0, "Branch_78efe0",
  version: "1",
  uuid: "f8b9237f-5bed-5ace-b137-614e3682ba4b",
  code_generator: "CONDITIONALS" do
  then(
    Message_1
    when contact.contact_module == "MODULE_1" and contact.arm == "GAMIFIED" and
           contact.onboarding_complete == true
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "257b5e58-1507-4429-b003-8c4400dbdf3f", x: -408, y: 24} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Ready, let's start with the second episode of Pilar and Mari's podcast. We're getting to know each other better!"
  )

  then(Message1)
end

```

<!-- { section: "f2c400d6-7d11-4ab7-8cf6-ba560cff6daf", x: 672, y: 24} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time ", "Super good 👍"]) do
      text(
        "Yesterday's challenge was to talk to someone you trust about healthy or toxic relationships. How did you do with yesterday's challenge?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time ")
  then(Message2_2 when ref_Message_2 == "Super good 👍")
  then(Catch_all_1)
end

```

<!-- { section: "83b2eb67-ad4c-4df6-9e76-199a0b4e4c21", x: 984, y: -864} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "f65d2a8b-1aa2-47c7-afaa-37396a102911", x: 1824, y: -120} -->

```stack
card Message_3_1, "Message_3_1",
  version: "1",
  uuid: "00e777d8-c313-50e1-9f6d-516d66206ec2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Don't worry, there's still time to do it. It is important to start creating your support network!"
  )

  then(Message_4)
end

```

<!-- { section: "a601a0b2-6bab-4183-ab8b-1ec6dc7927c6", x: 1848, y: 384} -->

```stack
card Message_3_2, "Message_3_2",
  version: "1",
  uuid: "4513e284-78b0-5e5b-8c78-60e3d4f7ebdc",
  code_generator: "TEXT_MESSAGE" do
  text("Incredible, it is important to start creating your support network!")
  then(Message_4)
end

```

<!-- { section: "478a1637-6794-45ec-9a2b-678715bda6ad", x: 2424, y: 120} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Okay 👍"]) do
      text("Also, remember that the longer your streak, the more stickers you accumulate!")
    end

  then(Message_5 when ref_Message_4 == "Okay 👍")
  then(Catch_all_2)
end

```

<!-- { section: "98e910c6-5db8-453c-aeaa-42332c87747c", x: 2280, y: -696} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "62b04e66-01d0-4f28-bcd4-fbd9be815555", x: 3072, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "TEXT_MESSAGE" do
  text(
    "In this second episode Pilar and Mari will talk about what we could do to feel better about ourselves 💖"
  )

  then(Message_6)
end

```

<!-- { section: "a38a47af-fbaf-4ce9-9052-c9240d2c6e16", x: 3768, y: 120} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Remember that if there is something that Pilar and Mari talk about or a question that makes you feel uncomfortable, you can stop and come back if you feel ready. For me it is very important that you feel good!🫰"
      )
    end

  then(Message_7 when ref_Message_6 == "Ok 👌")
  then(Catch_all_3)
end

```

<!-- { section: "1ca16e72-3f2c-4b6b-8a03-5cf5b63a3727", x: 3768, y: -792} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_6)
end

```

<!-- { section: "2cf255dc-caf3-4b94-9d78-0f8741a9c2c7", x: 4488, y: 144} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M2_P1")
  then(Message_8)
end

```

<!-- { section: "aa9f400a-4b97-4598-b762-db16e566f63d", x: 5088, y: 144} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_9 when ref_Message_8 == "I heard the audio")
  then(Catch_all_4)
end

```

<!-- { section: "e511a39e-34a9-410e-99d3-2c057db3bab0", x: 5112, y: -768} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "3e6f109f-6107-40af-9043-8fabea527535", x: 5448, y: 96} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "QUESTION" do
  ref_Message_9 =
    ask(
      "As Mari and Pilar say, it's okay to not be okay. But as Pilar mentions, sometimes it is difficult to talk about these topics...😣 

For you, how easy is it to talk about these topics with your trusted people? 

Remember that you can respond in text or voice notes"
    )

  then(Branch_91a7c6)
end

```

<!-- { section: "26b2f8a6-75ce-4304-839f-a6a97458f4dd", x: 6600, y: 120} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Follow the podcast "]) do
      text("Thanks for telling us! ✨")
    end

  then(Message_11_ when ref_Message_10 == "Follow the podcast ")
  then(Catch_all_13)
end

```

<!-- { section: "d9026258-71cd-4e46-b120-c85efd33bd6d", x: 7416, y: 144} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_12 when ref_Message_11_1 == "I heard the audio")
  then(Catch_all_5)
end

```

<!-- { section: "db1881b4-3b6f-4707-b798-aba3fdcd322d", x: 7512, y: -696} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11_1)
end

```

<!-- { section: "89607111-9341-436f-9566-6885bed317a7", x: 7992, y: 144} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "QUESTION" do
  ref_Message_12 =
    ask(
      "Pilar has not been feeling well in recent days. Things haven't been good and that has left her feeling very sad and confused. She knows she needs to do something to feel better, but she's not sure how to do it. 

If this were happening to you, what would you do?🤔 

Remember that you can respond in text or voice notes"
    )

  then(Branch_1fd2f0)
end

```

<!-- { section: "4c905050-e4a7-42b1-9e5f-64f21be74440", x: 9240, y: 168} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Follow the podcast "]) do
      text("Thank you for sharing these ideas to feel better! ✨")
    end

  then(Message_14_ when ref_Message_13 == "Follow the podcast ")
  then(Catch_all_6)
end

```

<!-- { section: "712cc32f-86e3-442b-ab12-a11b6377b83c", x: 8856, y: -696} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13)
end

```

<!-- { section: "e3bede8b-b94b-4f2e-b32b-de11bef95fac", x: 10128, y: 168} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_1 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_15 when ref_Message_14_1 == "I heard the audio")
  then(Catch_all_7)
end

```

<!-- { section: "2e4d5454-109b-4a9e-abad-555de291e47a", x: 9792, y: -744} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_1)
end

```

<!-- { section: "c5747f1e-d755-406e-a554-9f0da6b12ab2", x: 10536, y: 168} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "TEXT_MESSAGE" do
  text(
    "It's normal to feel overwhelmed, and finding ways to calm yourself is essential. Here are some of the ideas that Pilar and Mari mentioned:"
  )

  then(Message_16)
end

```

<!-- { section: "e605feaf-ec21-4493-965b-a0a5e7a5f21d", x: 11016, y: 168} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "TEXT_MESSAGE" do
  text("🧘 Breathing deeply can help you reduce tension immediately. 
🎵 Listening to empowering music can change your mood and give you a mental break.
✍️ Writing in a journal allows you to vent your thoughts, process what you feel, and reflect on the good in your life. 
🏃🏽‍♀️ Exercise. 
😴 Try to sleep well and rest. 
💃🏾 Do activities that usually fill us with energy.")
  then(Message_17)
end

```

<!-- { section: "e52aab12-b4a9-4cc0-9d2c-18fb7740e651", x: 11504, y: 168} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "TEXT_MESSAGE" do
  text("Any of these options can be useful to manage your emotions and find some calm 😌")
  then(Message_18)
end

```

<!-- { section: "b0071206-bbda-467d-a2ed-4bc5f78db093", x: 12000, y: 168} -->

```stack
card Message_18, "Message_18",
  version: "1",
  uuid: "f7026c34-d676-5420-8cd9-b7e2633bf18a",
  code_generator: "TEXT_MESSAGE" do
  text("Now, let's think a little more about today's topic.")
  then(Message_19)
end

```

<!-- { section: "523996ed-666e-40c7-83b6-03f10e2b97da", x: 12480, y: 168} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["I should seek help", "It's not a big deal ", "I don't know 😢"]) do
      text(
        "Imagine that Pilar hasn't been feeling very well lately. Your relationship with your partner is now only fights and jealousy. She cries every day, gets irritated easily and has distanced herself from her friends 😢 

She feels ashamed of everything that is happening and refuses to tell anyone because, despite everything, her boyfriend gives her gifts and she thinks he loves her too much. Plus, she thinks they're going to judge her. 

What do you think about this? 🤔"
      )
    end

  then(Message19_1 when ref_Message_19 == "I should seek help")
  then(Message19_2 when ref_Message_19 == "It's not a big deal ")
  then(Message19_3 when ref_Message_19 == "I don't know 😢")
  then(Catch_all_12)
end

```

<!-- { section: "9730a12e-6218-4f77-aedd-5490353f6fdc", x: 13968, y: 192} -->

```stack
card Message_20_1, "Message_20_1",
  version: "1",
  uuid: "3c0640c4-ff8d-5995-9bf2-1f14c9dd3e9a",
  code_generator: "TEXT_MESSAGE" do
  text("send audio - G_M2_P3_R1")
  then(Message_21)
end

```

<!-- { section: "f84e74ff-6390-49de-8b34-d2264055b18d", x: 13968, y: 504} -->

```stack
card Message_20_2, "Message_20_2",
  version: "1",
  uuid: "7f14b299-04c1-5c54-b977-1eac1d3d9530",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M2_P3_R2")
  then(Message_21)
end

```

<!-- { section: "0e9d592c-642a-453d-a022-d15644ca687d", x: 13968, y: 864} -->

```stack
card Message_20_3, "Message_20_3",
  version: "1",
  uuid: "585d1da4-fa3c-548a-b6df-91a1f83d6182",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M2_P3_R3")
  then(Message_21)
end

```

<!-- { section: "c97ff8e2-d14b-4b2a-ac51-24de700febb2", x: 13968, y: 1392} -->

```stack
card Message_20_4, "Message_20_4",
  version: "1",
  uuid: "18b248bf-9ff1-5267-836c-be8bdc3578c9",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M2_P3_R4")
  then(Message_21)
end

```

<!-- { section: "b37e456a-ba99-435a-bbe6-1903e65a40cd", x: 15096, y: 432} -->

```stack
card Message_21, "Message_21",
  version: "1",
  uuid: "42ddc0ec-4a49-569c-8d14-b5522e118823",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_21 =
    buttons(["That's normal👍", "It's not a big deal ", "Count on us"]) do
      text(
        "In your case, if you told your friends that you were feeling bad lately in your relationship, what would they say to you?"
      )
    end

  then(Message21_1 when ref_Message_21 == "That's normal👍")
  then(Message21_2 when ref_Message_21 == "It's not a big deal ")
  then(Message21_3 when ref_Message_21 == "Count on us")
  then(Catch_all_8)
end

```

<!-- { section: "0c28f7b3-9694-4e73-81b8-769fac02c81d", x: 15144, y: -840} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_21)
end

```

<!-- { section: "30f69ca7-827c-4c61-87b7-c7e5a9b2daa9", x: 16776, y: 96} -->

```stack
card Message_22_1, "Message_22_1",
  version: "1",
  uuid: "01841d9d-ff48-506e-a331-a939c3ae304f",
  code_generator: "TEXT_MESSAGE" do
  text(
    "This response may make you feel like your problems are not that serious. While it's helpful to receive perspective, it's important to feel validated and supported by your group 🤗"
  )

  then(Message_23)
end

```

<!-- { section: "1026ab5e-580e-4ee3-b5c9-466ea1632f39", x: 16752, y: 504} -->

```stack
card Message_22_2, "Message_22_2",
  version: "1",
  uuid: "2e640323-ec94-58a4-aca6-2179c3a38dd6",
  code_generator: "TEXT_MESSAGE" do
  text(
    "This comment may minimize your feelings and make you feel misunderstood. It is important that you feel validated and supported by your group 🤗"
  )

  then(Message_23)
end

```

<!-- { section: "1e3a50ca-1ee4-41db-8881-ea56270f3076", x: 16752, y: 840} -->

```stack
card Message_22_3, "Message_22_3",
  version: "1",
  uuid: "fa2a20bc-0689-5f92-8070-4b6e3773b4b7",
  code_generator: "TEXT_MESSAGE" do
  text(
    "This response is supportive and encouraging. Your group offers you good support by acknowledging your feelings and showing that they are willing to help and listen to you. It is important to have this type of support in difficult times 🤗
"
  )

  then(Message_23)
end

```

<!-- { section: "020bc88c-2fc2-43cd-b42a-665b3ecfbfd6", x: 17832, y: 480} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["Send my stickers!"]) do
      text(
        "Very good! You completed episode 2 of the podcast 🥳 Today I have more stickers so you can use them to help you if one day you face a situation like this."
      )
    end

  then(Message_24_sticker_1 when ref_Message_23 == "Send my stickers!")
  then(Catch_all_9)
end

```

<!-- { section: "2356c449-9f1c-4e47-b24f-dc40bcf7b646", x: 17784, y: -672} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_23)
end

```

<!-- { section: "331b5559-1216-403a-ab32-da9066b99833", x: 18480, y: -72} -->

```stack
card Message_24_sticker_1, "Message_24_sticker_1",
  version: "1",
  uuid: "cb446ffc-b076-593f-907a-0a8f1d1167b6",
  code_generator: "MEDIA_IMAGE" do
  image("97acc9a8-4fbc-462a-bbb9-6e91ffba41c3-Módulo2_Vibrando.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "d0a35c07-2703-496c-b226-2c38be9b750d", x: 19064, y: 504} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "TEXT_MESSAGE" do
  text(
    "You're already on day 2 of 6 in the podcast challenge! I know you're going to have a perfect streak 🙌"
  )

  then(Message_26)
end

```

<!-- { section: "f5b0ed83-f60a-4235-8d91-4d9cf28259cd", x: 19560, y: 504} -->

```stack
card Message_26, "Message_26",
  version: "1",
  uuid: "ccefd577-e5e5-508a-a17f-662eecb14671",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["after school", "before sleeping", "When I get up"]) do
      text(
        "Now I'm going to leave you this challenge: For tomorrow, do your first day of practice and think about when you want to do your routine so you don't forget?"
      )
    end

  then(Message26_1 when ref_Message_26 == "after school")
  then(Message26_2 when ref_Message_26 == "before sleeping")
  then(Message26_3 when ref_Message_26 == "When I get up")
  then(Catch_all_10)
end

```

<!-- { section: "2b378fcc-40fe-4286-9b46-ddedb61b3422", x: 20664, y: 504} -->

```stack
card Message_27, "Message_27",
  version: "1",
  uuid: "58095b08-ea56-5e0f-9bba-0cdfec59e6c4",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_27 =
    buttons(["Understood 🌸"]) do
      text(
        "Ok friend, that's all for today. Get ready because in tomorrow's episode we will talk about how we can be a support for someone who is going through a difficult situation!"
      )
    end

  then(Message_28 when ref_Message_27 == "Understood 🌸")
  then(Catch_all_11)
end

```

<!-- { section: "38223828-3c7a-40c1-a37e-57afaf0521ab", x: 21264, y: 528} -->

```stack
card Message_28, "Message_28",
  version: "1",
  uuid: "fa2bc47c-07ac-5963-8796-2bedea805ae2",
  code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_c16c7c)
end

```

<!-- { section: "89687717-dfe7-42ec-9345-9f1978306fc3", x: 19536, y: -360} -->

```stack
card Catch_all_10, "Catch_all_10",
  version: "1",
  uuid: "94300c17-3a4c-5cf3-b3b8-8f7ef65bd123",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_26)
end

```

<!-- { section: "1fb02303-0190-4c5c-9a89-f533f916a02c", x: 20640, y: -384} -->

```stack
card Catch_all_11, "Catch_all_11",
  version: "1",
  uuid: "77b44343-8af2-53d7-b85a-c83e97c7fb9b",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_27)
end

```

<!-- { section: "810204ed-2c99-4d19-887c-3ada660ab9e4", x: 12504, y: -936} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_19)
end

```

<!-- { section: "2b9ee1e1-cb4e-4852-8b4e-5a8ca63328dd", x: 6504, y: -648} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10)
end

```

<!-- { section: "679c0a5d-7a05-4737-8cf7-27bd00a632ef", x: 21840, y: 504} -->

```stack
card Profile_c16c7c, "Profile_c16c7c",
  version: "1",
  uuid: "069c5d76-fe0b-5517-94ff-68b07388e6b1",
  code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_2")
  then(ModuleCompleted)
end

```

<!-- { section: "1d069a23-70bc-4e66-97e2-4d1f9de769c6", x: 18432, y: 456} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("f24d8673-c0e8-4edc-96c6-2d39b9c8183c-Módulo2_MipersonaFav.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "aa02f5af-8998-46dd-8c5f-a683887befc7", x: 18384, y: 984} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("2ac18cd6-5656-4294-83d5-d6ee8be1606b-Módulo2_Meamo.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "594371fa-1018-4383-9618-0322521e40fc", x: 18872, y: 984} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("eca19411-8eeb-46bc-bf01-1bc0e531cbc6-Módulo2_InteligenciaEmocional.png")
  text("")
  then(Message_25)
end

```

<!-- { section: "5965c1fb-6567-4c12-a8b7-29211ef4b739", x: 6920, y: 180} -->

```stack
card Message_11_, "Message_11_",
  version: "1",
  uuid: "7cadbd10-97d6-55dd-ba9d-ff103177acc6",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M2_P2")
  then(Message_11_1)
end

```

<!-- { section: "76681278-0b37-479e-8acc-5badd15c4f94", x: 9648, y: 168} -->

```stack
card Message_14_, "Message_14_",
  version: "1",
  uuid: "33d77f34-b487-5244-b303-29d16121f8f9",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M2_P3")
  then(Message_14_1)
end

```

<!-- { section: "f762f4c0-0e22-4539-993a-bc03194046df", x: 5832, y: 96} -->

```stack
card Branch_91a7c6, "Branch_91a7c6",
  version: "1",
  uuid: "7fffa77e-39e0-5027-a564-8c53ab31d36d",
  code_generator: "CONDITIONALS" do
  then(Message9 when event.message.type == "audio")
  then(Message9 when event.message.type == "text")
  then(Text_6f4620)
end

```

<!-- { section: "e76fe1b3-dc30-4e35-b459-3682de81a85e", x: 5784, y: 432} -->

```stack
card Text_6f4620, "Text_6f4620",
  version: "1",
  uuid: "5169fb29-7a95-55a2-be67-28caf884d080",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_9)
end

```

<!-- { section: "15fade51-9fab-4c40-a3bf-0995a314b1da", x: 8424, y: 120} -->

```stack
card Branch_1fd2f0, "Branch_1fd2f0",
  version: "1",
  uuid: "d31f9710-7903-5170-8e6c-1f20f695ad13",
  code_generator: "CONDITIONALS" do
  then(Message12 when event.message.type == "audio")
  then(Message12 when event.message.type == "text")
  then(Catch_all_12_1)
end

```

<!-- { section: "48cd8275-9472-4d8d-a49a-52f861c07e4e", x: 8328, y: 552} -->

```stack
card Catch_all_12_1, "Catch_all_12_1",
  version: "1",
  uuid: "0fede328-1fb1-5e95-9dcf-fa66f2a3c877",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_12)
end

```

<!-- { section: "bd198bc0-60b7-4fae-af54-19037e1122f3", x: 3816, y: 552} -->

Emoji does not show up

<!-- { section: "6576fd29-e791-4475-8751-d89926b625ea", x: 4560, y: 288} -->

Missing audio here

<!-- { section: "04cc6dbb-21dd-4c99-8d78-04dacc917855", x: 5856, y: 600} -->

**@buhle**

please save users response here

Not sure which you needed so here is a code block as well, please dlt the one you dont need

<!-- { section: "3ac40654-f667-4b37-8e3f-672480f96b3a", x: 8616, y: 744} -->

**@buhle**

please save users response here

Not sure which you needed so here is a code block as well, please dlt the one you dont need

<!-- { section: "3eec4590-3262-4c86-8851-8742d9c27b8f", x: 7056, y: 336} -->

Add audio here

<!-- { section: "2e0a4120-2722-485a-8ead-3908c39795c7", x: 9672, y: 360} -->

Audio missing here

<!-- { section: "3d32adbd-6590-4565-aa86-20a2ba3f4db5", x: 12576, y: 960} -->

**@buhle**

please save users response here

<!-- { section: "3eab94b9-7b5c-45d2-bed0-e88596e1d73b", x: 15024, y: 1104} -->

**@buhle**

please save users response here

<!-- { section: "ef870e7d-f3f3-4e40-9afb-760c0ad1e7af", x: 22416, y: 1080} -->

**@Buhle**

Schedule Module 3 start next day (6pm , Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "78fb05e7-728d-4b37-9c57-df4a3bd10c85", x: -1056, y: 720} -->

**@Buhle**

please add in the other thingies here ^

<!-- { section: "8b05990d-fe8a-438f-b56b-444fb17bf0fa", x: 72, y: 360} -->

**@Buhle**

please add in the DS save result,

DS note: Flow result: module2_started (yes)

<!-- { section: "dc208faf-6e41-4a25-85cc-a05da3a65c8c", x: 888, y: 480} -->

**@buhle**

Please save insight here

<!-- { section: "a643df62-81bb-4e39-bc19-693a9b90c7e7", x: 13944, y: 1200} -->

**@TAM**

This is where they  have a random floating option d on this message, so I have popped it in for now, but awaiting feedback from latam

<!-- { section: "f79ad53a-2f93-43de-8a3f-107dc2965387", x: 19584, y: 936} -->

**@buhle**

please save users response here

<!-- { section: "da06be9e-0d10-4d72-87c6-ba2ff4a4de17", x: 22416, y: 888} -->

**@Buhle**

DS note: Flow result:   (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "5b51661c-8996-45d0-870c-a70e679b875d", x: 21336, y: 768} -->

Update contact field, 
contact module = Module 2 ✅

<!-- { section: "7e764e20-9174-4638-a0b5-d854790e7894", x: 5952, y: -576} -->

```stack
card Message9 do
  write_result("module2_social_support", "@ref_message_9")
  then(Message_10)
end

```

<!-- { section: "7d5b48fd-1d4a-448f-927a-121f374863d8", x: 8808, y: 192} -->

```stack
card Message12 do
  write_result("module2_mental_health", "@ref_message_12")
  then(Message_13)
end

```

<!-- { section: "c28290f8-aaec-442c-a060-36d9af6eb66d", x: 22416, y: 456} -->

```stack
card ModuleCompleted do
  log("Module 2 Complete")
  write_result("module2_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 13, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```

<!-- { section: "60acc57d-f722-459c-b0b7-3c0e8f1c8dad", x: 96, y: -24} -->

```stack
card Message1 do
  write_result("module2_started", "yes")
  then(Message_2)
end

```

<!-- { section: "fb640fb7-ea51-4be0-acc2-39c5ac665bb7", x: 1344, y: -120} -->

```stack
card Message2_1 do
  write_result("module2_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "dd57880d-d779-48fe-b432-ff0897be03c7", x: 1344, y: 240} -->

```stack
card Message2_2 do
  write_result("module2_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "05765245-4da3-4778-9855-a6dd2e31bbc5", x: 12968, y: 228} -->

```stack
card Message19_1 do
  write_result("module2_beliefs", "a")
  then(Message_20_1)
end

```

<!-- { section: "6a59f267-7078-4cc0-a09c-654242c4683d", x: 12984, y: 552} -->

```stack
card Message19_2 do
  write_result("module2_beliefs", "b")
  then(Message_20_2)
end

```

<!-- { section: "256cf0e2-1cb9-4ddd-9de4-763cdff19caa", x: 12984, y: 888} -->

```stack
card Message19_3 do
  write_result("module2_beliefs", "c")
  then(Message_20_3)
end

```

<!-- { section: "19d54701-3f85-41e7-8c61-8cdcafa1f8bd", x: 15624, y: 216} -->

```stack
card Message21_1 do
  write_result("module2_social_norms", "a")
  then(Message_22_1)
end

```

<!-- { section: "7f3f8a66-4d84-440b-88bb-69c4830706c4", x: 15648, y: 552} -->

```stack
card Message21_2 do
  write_result("module2_social_norms", "b")
  then(Message_22_2)
end

```

<!-- { section: "9221f773-524f-4d4e-98aa-d43c7234a60f", x: 15648, y: 888} -->

```stack
card Message21_3 do
  write_result("module2_social_norms", "c")
  then(Message_22_3)
end

```

<!-- { section: "5b327fe7-ec8a-4db5-8f52-61e77f714e3a", x: 20064, y: 288} -->

```stack
card Message26_1 do
  write_result("module2_behavioral_activation", "a")
  then(Message_27)
end

```

<!-- { section: "c3873596-a87d-406f-8aa8-feb45e16134f", x: 20088, y: 648} -->

```stack
card Message26_2 do
  write_result("module2_behavioral_activation", "b")
  then(Message_27)
end

```

<!-- { section: "76514b76-798c-4b07-8513-2f9ad6434426", x: 20112, y: 984} -->

```stack
card Message26_3 do
  write_result("module2_behavioral_activation", "c")
  then(Message_27)
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
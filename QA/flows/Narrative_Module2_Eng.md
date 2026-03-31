<!-- { section: "4f6bc1b1-841b-4c12-a20a-8251ffcce125", x: -1632, y: -96} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "nm2")

```

<!-- { section: "605e2713-047d-4249-9179-e4aa10fc035f", x: -384, y: -24} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text("Hello! 👋 Welcome to the second episode of Pilar's story.")
  then(Message1)
end

```

<!-- { section: "d30c9e21-4563-4d5c-ae51-e9338c9fb127", x: 816, y: -24} -->

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

<!-- { section: "bd54db94-ca16-4639-98dc-b2038dc8e5cf", x: 1824, y: 24} -->

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

<!-- { section: "144464bb-2e52-4d98-9876-2cecc3e0b615", x: 1824, y: 288} -->

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
  code_generator: "TEXT_MESSAGE" do
  text("In this second episode we will know why the police called Pilar's mother 💖")
  then(Message_5)
end

```

<!-- { section: "98e910c6-5db8-453c-aeaa-42332c87747c", x: 2280, y: -696} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "22989e5a-2822-46c5-8546-2716f067a9da", x: 2832, y: 120} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Okay"]) do
      text(
        "Remember that if something about Pilar's story or a question makes you feel uncomfortable, you can stop and come back when you feel ready. It is very important to me that you feel good!"
      )
    end

  then(Message_6 when ref_Message_5 == "Okay")
end

```

<!-- { section: "3933b1d2-f824-499c-9130-099f1dc1ce8e", x: 3384, y: 96} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio NARRATIVE - CHAPTER 2 - PART 1")
  then(Message_7)
end

```

<!-- { section: "939ba2e8-d0a4-4477-b247-cbed87245b04", x: 3936, y: -720} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_7)
end

```

<!-- { section: "76198446-33c5-4ec1-8716-7a02d754af14", x: 3936, y: 120} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["I heard the audio!"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_8 when ref_Message_7 == "I heard the audio!")
  then(Catch_all_3)
end

```

<!-- { section: "32b1cf2c-75bc-4d01-8d92-b8ea5f75dc14", x: 4464, y: 96} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["I should seek help", "No big deal 🙄", "It's normal 😐"]) do
      text(
        "In the episode we hear that Pilar hasn't been feeling very well lately. He hasn't gone to training, he hasn't handed in his language work, he hasn't slept well and, furthermore, his stomach has been hurting. 

What do you think about this? 🤔"
      )
    end

  then(Message8_1 when ref_Message_8 == "I should seek help")
  then(Message8_2 when ref_Message_8 == "No big deal 🙄")
  then(Message8_3 when ref_Message_8 == "It's normal 😐")
  then(Catch_all_4)
end

```

<!-- { section: "ad9f01c8-4b61-44eb-b628-3e58f53a4826", x: 4584, y: -720} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "91fc1a69-8097-49fa-9019-6b8a131d70c5", x: 5784, y: -168} -->

```stack
card Message_9_1, "Message_9_1",
  version: "1",
  uuid: "c3a0f754-7f11-5ee1-8038-7f0744548590",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Seeking help is a brave and right step; You can receive the necessary support from friends, family and experts to manage what you are experiencing."
  )

  then(Message_10)
end

```

<!-- { section: "6a310ae9-09e0-45e0-9a76-6993b9a9c20a", x: 6096, y: 312} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "QUESTION" do
  ref_Message_10 =
    ask(
      "Remember: it's okay to not always be okay. But sometimes it's hard to talk about these topics...😣 

For you, how easy is it to talk about these topics with your trusted people? 

Remember that you can respond in text or voice notes"
    )

  then(Branch_4fcb2f)
end

```

<!-- { section: "53b714f7-8cf5-48d9-9806-c57b536375ae", x: 7584, y: 168} -->

```stack
card Message_11_1, "Message_11_1",
  version: "1",
  uuid: "e1e6b4a6-73af-5ff2-8699-ea01816b5889",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11_1 =
    buttons(["Next audio"]) do
      text("Thanks for telling me ✨")
    end

  then(Message_12 when ref_Message_11_1 == "Next audio")
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

<!-- { section: "d14bf29e-7b83-4aa1-8ae4-a5abe16d84ae", x: 8112, y: 192} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "TEXT_MESSAGE" do
  text("Send audio file - NARRATIVE - CHAPTER 2 - PART 2")
  then(Message_12_1)
end

```

<!-- { section: "ef664d3d-b8b7-468b-be1c-92a3644aa4f2", x: 8904, y: 192} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "QUESTION" do
  ref_Message_13 =
    ask(
      "Imagine that Pilar has had several arguments with her partner lately. Things haven't been good and that has left her feeling very stressed and confused. She knows she needs to do something to manage her emotions and calm down, but she's not sure what to do to feel better. 

If it were your case, what would you do?🤔 

Remember that you can respond in text or voice notes"
    )

  then(Branch_2e1be6)
end

```

<!-- { section: "33a2113f-618a-42b4-b812-97f9efa24910", x: 11352, y: -648} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_17)
end

```

<!-- { section: "a977e0c6-7025-4043-8023-c3c88f7fd25e", x: 10032, y: 168} -->

```stack
card Message_14_1, "Message_14_1",
  version: "1",
  uuid: "22dfb5d4-d7ad-5836-a32b-fd9c7d343497",
  code_generator: "TEXT_MESSAGE" do
  text("Thank you for sharing your ideas to feel better! ✨")
  then(Message_15)
end

```

<!-- { section: "10d54b2a-1236-43ad-b68e-98d4d9d2893e", x: 10776, y: -648} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16)
end

```

<!-- { section: "4f46413c-6bfc-4c55-b18e-fe17480e95e3", x: 10416, y: 168} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "TEXT_MESSAGE" do
  text(
    "In general, it is normal to feel overwhelmed after arguments with a partner and finding ways to calm yourself is essential. Here are some additional ideas:"
  )

  then(Message_16)
end

```

<!-- { section: "fd516cd7-cf34-46be-92fc-41c866ace3f9", x: 10752, y: 168} -->

```stack
card Message_16, "Message_16",
  version: "1",
  uuid: "bb0b0c73-5ed6-59a6-b63a-bd70b380beb9",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["Next question"]) do
      text("🧘 Breathing deeply can help you reduce tension immediately. 
🎵 Listening to empowering music can change your mood and give you a mental break. 
✍️ Writing in a journal allows you to vent your thoughts, process what you feel, and reflect on the good in your life. Even better if you write daily about things that happen during the day that you liked or are grateful for. 
🏃🏽‍♀️ Exercise. 
😴 Try to sleep well and rest. 
💃🏾 Do activities that usually fill us with energy. 

Any of these options can be helpful in managing your emotions and finding some peace.")
    end

  then(Message_17 when ref_Message_16 == "Next question")
  then(Catch_all_7)
end

```

<!-- { section: "5d4b0252-ac76-4d2f-8a28-2842b2b9bf1b", x: 11376, y: 168} -->

```stack
card Message_17, "Message_17",
  version: "1",
  uuid: "4f86bb48-7bb2-54eb-852b-fc4f563c5709",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_17 =
    buttons(["That's normal👍", "Not a big deal🙄", "Count on us"]) do
      text(
        "If you told your friends that you have been feeling bad lately in your relationship, what would they say to you?"
      )
    end

  then(Message17_1 when ref_Message_17 == "That's normal👍")
  then(Message17_2 when ref_Message_17 == "Not a big deal🙄")
  then(Message17_3 when ref_Message_17 == "Count on us")
  then(Catch_all_6)
end

```

<!-- { section: "76725b26-c553-4b78-a527-0272d382d403", x: 12504, y: -24} -->

```stack
card Message_18_1, "Message_18_1",
  version: "1",
  uuid: "8a733211-d7eb-5c2b-9a03-0e4bea4cba0b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "This response may make you feel like your problems are not that serious. While it's helpful to receive perspective, it's important to feel validated and supported by your group."
  )

  then(Message_19)
end

```

<!-- { section: "9483a94d-d17b-4643-b968-1dc83d176683", x: 13152, y: 336} -->

```stack
card Message_19, "Message_19",
  version: "1",
  uuid: "fc890cd1-4e1b-5ffb-bae3-defa83ed46f2",
  code_generator: "TEXT_MESSAGE" do
  text(
    "It's not always easy to ask others for help, but it's a super power to put into practice! When you use it you may discover that you have more people than you thought willing to help you 💁‍♀️"
  )

  then(Message_20_)
end

```

<!-- { section: "9ba26e83-fe93-4938-a1d3-e5a2d4b6f06d", x: 13632, y: 336} -->

```stack
card Message_20_, "Message_20_",
  version: "1",
  uuid: "8f5fca40-9def-58ee-b7c0-e79677456838",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20_ =
    buttons(["Send my stickers!"]) do
      text(
        "Very good! Have you heard episode 2 of Pilar's story 🥳 

They are complex topics, so to help you navigate them I leave you some great stickers on this topic that you can use to respond if you experience something similar."
      )
    end

  then(Message_21_sticker_1 when ref_Message_20_ == "Send my stickers!")
  then(Catch_all_12)
end

```

<!-- { section: "7a53063d-1d5f-488b-9943-01dc0bd90030", x: 15048, y: 408} -->

```stack
card Message_22, "Message_22",
  version: "1",
  uuid: "8d0a29f8-0d96-5fef-9b04-27dd7d6d4868",
  code_generator: "QUESTION" do
  ref_Message_22 =
    ask(
      "Have you heard the song \"Mientras me curo del cora\" 💖 by Karol G? 

There is a part of the lyrics that says: \"It's okay not to feel good, it's normal, it's not a crime, and tomorrow it will be prettier.\" 

Do you know any other songs that make you feel better when you're going through a bad time? Write the name here"
    )

  then(Branch_64e016)
end

```

<!-- { section: "93bc7322-b04e-421f-a6fd-3b03dd71ea54", x: 16128, y: -504} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_23)
end

```

<!-- { section: "9e82f797-e050-459a-a65d-2d36a4445ec7", x: 16152, y: 456} -->

```stack
card Message_23, "Message_23",
  version: "1",
  uuid: "e6153fb4-3c26-5a62-b639-12d61f714bc1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["After school 🏫", "Before sleeping 😴", "When I get up 🌞"]) do
      text(
        "Now I'm going to leave you this challenge: For tomorrow, at some point during the day, apply a strategy to feel better. When would you like to do it so you don't forget?"
      )
    end

  then(Message23_1 when ref_Message_23 == "After school 🏫")
  then(Message23_2 when ref_Message_23 == "Before sleeping 😴")
  then(Message23_3 when ref_Message_23 == "When I get up 🌞")
  then(Catch_all_8)
end

```

<!-- { section: "e224b612-15cd-484f-a0b1-78f2b75eecde", x: 17592, y: 456} -->

```stack
card Message_24, "Message_24",
  version: "1",
  uuid: "40a4a3f9-69a7-5e18-bd81-9d5a935b903c",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["I want to know!🧐"]) do
      text(
        "Ok friend, this was all for today. Get ready! Because tomorrow's episode is going to be incredible, what do you think? Will it be that tomorrow we will know where Pilar is?"
      )
    end

  then(Message_25 when ref_Message_24 == "I want to know!🧐")
  then(Catch_all_9)
end

```

<!-- { section: "266b3043-5c8b-4095-8d6e-47d851218dd5", x: 17616, y: -648} -->

```stack
card Catch_all_9, "Catch_all_9",
  version: "1",
  uuid: "716f40be-c939-5261-b228-89a4ab91511f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_24)
end

```

<!-- { section: "c3f64714-392f-45d7-a37b-4391f20010d5", x: 18336, y: 504} -->

```stack
card Message_25, "Message_25",
  version: "1",
  uuid: "73839b09-58d2-590c-85f8-4844ee50a2a9",
  code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(ModuleCompleted)
end

```

<!-- { section: "f1194683-0f33-45af-939c-bdf435a274ef", x: 13608, y: -648} -->

```stack
card Catch_all_12, "Catch_all_12",
  version: "1",
  uuid: "4ffb1907-234f-584b-b972-7c451e40e7ba",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_20_)
end

```

<!-- { section: "65aa3e37-0863-48fe-942f-d76a91d1c6a4", x: 8376, y: -576} -->

```stack
card Catch_all_13, "Catch_all_13",
  version: "1",
  uuid: "2ee9d80c-b598-5fe1-892d-c7a3793ce581",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12_1)
end

```

<!-- { section: "12c9dafa-ce12-44d8-884f-3c7c9465546f", x: 5712, y: 312} -->

```stack
card Message_9_2, "Message_9_2",
  version: "1",
  uuid: "a7a44162-d023-584e-886e-0db24185236b",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Although sometimes feeling low on energy can be normal, lack of interest in school activities, insomnia, and frequent physical discomfort could be symptoms associated with anxiety, stress, or depression. Pilar could be going through a difficult situation and it is important that she seek help."
  )

  then(Message_10)
end

```

<!-- { section: "30ad451b-ca25-4c06-a9e3-a10d42d0b8de", x: 5736, y: 792} -->

```stack
card Message_9_3, "Message_9_3",
  version: "1",
  uuid: "58f08f6d-1c0f-5772-b91b-b7163ce1a543",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Although sometimes feeling low on energy can be normal, lack of interest in school activities, insomnia, and frequent physical discomfort could be symptoms associated with anxiety, stress, or depression. Pilar could be going through a difficult situation and it is important that she seek help."
  )

  then(Message_10)
end

```

<!-- { section: "1ca7c230-40e8-4ebf-beb8-d69691d90fcc", x: 8496, y: 192} -->

```stack
card Message_12_1, "Message_12_1",
  version: "1",
  uuid: "b3faf013-4802-5596-99ea-9df4b6c14c5b",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_1 =
    buttons(["I heard the audio!"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_13 when ref_Message_12_1 == "I heard the audio!")
  then(Catch_all_13)
end

```

<!-- { section: "341268e3-3412-47f6-85ed-23334586f0a5", x: 12528, y: 480} -->

```stack
card Message_18_2, "Message_18_2",
  version: "1",
  uuid: "f991fbc5-7712-5518-a753-a5e3f160f9ef",
  code_generator: "TEXT_MESSAGE" do
  text(
    "This comment may minimize your feelings and make you feel misunderstood. It is important that you feel validated and supported by your group."
  )

  then(Message_19)
end

```

<!-- { section: "a186904e-14ad-4224-af4a-a6084f98bd79", x: 12536, y: 864} -->

```stack
card Message_18_3, "Message_18_3",
  version: "1",
  uuid: "8bf10063-4658-5846-a34e-3c68b1167484",
  code_generator: "TEXT_MESSAGE" do
  text(
    "This response is supportive and encouraging. Your group offers you good support by acknowledging your feelings and showing that they are willing to help and listen to you. It is important to have this type of support in difficult times."
  )

  then(Message_19)
end

```

<!-- { section: "e299750b-d51f-40f5-87fd-7624d9fa7cbf", x: 14208, y: -456} -->

```stack
card Message_21_sticker_1, "Message_21_sticker_1",
  version: "1",
  uuid: "7bcad0af-edec-5046-9d8a-298767885d4b",
  code_generator: "MEDIA_IMAGE" do
  image("3eaee586-a18e-4588-a3d9-d55677e0e90a-Módulo2_Brilla.jpg")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "8653d9e2-8bd6-4db1-bfa5-d7408d58b3e2", x: -336, y: 288} -->

```stack
card Branch_3095e6, "Branch_3095e6",
  version: "1",
  uuid: "9d88703c-7e98-5427-be3f-37382b2e613a",
  code_generator: "CONDITIONALS" do
  then(
    Message_1
    when contact.quiz_post_module1_complete == true and contact.contact_module == "MODULE_1" and
           contact.arm == "NARRATIVE"
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "7dea43d3-ffa2-48e2-975b-2bb972f794e3", x: 14184, y: 24} -->

```stack
card Sticker_2, "Sticker_2",
  version: "1",
  uuid: "d0813bf8-cf35-5331-a291-2c9d4fa6eee9",
  code_generator: "MEDIA_IMAGE" do
  image("fb44ba0c-aa9e-43df-86c8-6c58542b662f-Módulo2_InteligenciaEmocional.jpg")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "16a8c065-6e59-478a-b05f-a4910f353cce", x: 14664, y: 24} -->

```stack
card Sticker_3, "Sticker_3",
  version: "1",
  uuid: "06186ca6-0363-547d-9689-d51f4ab0eafd",
  code_generator: "MEDIA_IMAGE" do
  image("faac8844-37a8-410e-9d2f-d9c25fd8e1d8-Módulo2_Meamo.jpg")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "29b1a782-1601-4d7b-9bce-257067b7c0ef", x: 14184, y: 624} -->

```stack
card Sticker_4, "Sticker_4",
  version: "1",
  uuid: "18a60dad-7161-5715-bede-03e9d891a9c5",
  code_generator: "MEDIA_IMAGE" do
  image("22d61eea-0b74-4e25-8cc3-11c3788ef8e5-Módulo2_MipersonaFav.jpg")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "804a9c23-ef06-4579-a144-4bf739e3c8dc", x: 14712, y: 672} -->

```stack
card Sticker_5, "Sticker_5",
  version: "1",
  uuid: "e03e2e50-6e92-50b7-a8ab-30200103841d",
  code_generator: "MEDIA_IMAGE" do
  image("75a3b9c9-d74b-4850-bdc7-6f14add01ee8-Módulo2_Vibrando.jpg")
  text("")
  then(Message_22)
end

```

<!-- { section: "55a8440b-d0e6-43dd-8411-a0cc529ac856", x: 6584, y: 312} -->

```stack
card Branch_4fcb2f, "Branch_4fcb2f",
  version: "1",
  uuid: "88629154-7842-53a9-ba8c-3bc2cad9a957",
  code_generator: "CONDITIONALS" do
  then(Message10 when event.message.type == "audio")
  then(Message10 when event.message.type == "text")
  then(Text_6c79a6)
end

```

<!-- { section: "765ad697-ff4c-4705-8517-550138fe32bd", x: 6360, y: 768} -->

```stack
card Text_6c79a6, "Text_6c79a6",
  version: "1",
  uuid: "862e2696-9a6f-5201-ab49-c9a6b15b10d0",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_10)
end

```

<!-- { section: "8cd32f28-04a8-4808-a99b-f7814ed775ae", x: 9288, y: 192} -->

```stack
card Branch_2e1be6, "Branch_2e1be6",
  version: "1",
  uuid: "7cc496f7-6b9d-5e81-9517-1ec6c6d0ab3b",
  code_generator: "CONDITIONALS" do
  then(Message13 when event.message.type == "audio")
  then(Message13 when event.message.type == "text")
  then(Text_72ac41)
end

```

<!-- { section: "db4e6f7e-5970-4a85-a244-6f3ddc61feb2", x: 9192, y: 624} -->

```stack
card Text_72ac41, "Text_72ac41",
  version: "1",
  uuid: "4ffd575b-86ff-509f-afbb-7ba99b4112aa",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_13)
end

```

<!-- { section: "9871f798-a43f-458d-806b-bf344ac7be6a", x: 15360, y: 408} -->

```stack
card Branch_64e016, "Branch_64e016",
  version: "1",
  uuid: "6e9f32c6-025c-5a46-b8b1-91253f0e8e41",
  code_generator: "CONDITIONALS" do
  then(Message22 when event.message.type == "text")
  then(Text_400e5d)
end

```

<!-- { section: "5df55ae4-e14e-4b49-be53-fd1805547163", x: 15360, y: 744} -->

```stack
card Text_400e5d, "Text_400e5d",
  version: "1",
  uuid: "2f8714fc-fb3c-586b-8af6-5ade7144e2dc",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text.")
  then(Message_22)
end

```

<!-- { section: "a56ae036-8681-47b6-8423-3f6001ec957d", x: 15576, y: 768} -->

**@Buhle**

save user response here

<!-- { section: "5607b298-b29a-4619-a49c-00fcab331e14", x: 18816, y: 912} -->

**@Buhle**

Set follow up message to go off at 6pm Time zone is Colombia / Bogota time

(Tam is double checking with Chi on this)

<!-- { section: "4c7adacd-f59d-4abf-9c87-acedfae5fe46", x: 16512, y: 960} -->

**@Buhle**\
save user response here

<!-- { section: "698ed1b7-f0df-4399-9dfd-fd3cd08acfaa", x: 12096, y: 1128} -->

**@Buhle**

save user response here

<!-- { section: "53f795ab-df56-4956-8baf-3a01f2f8537b", x: 7032, y: 624} -->

**@Buhle**

save user response here

<!-- { section: "dbac173a-8a4d-4fa1-adfc-e0e62f37ad49", x: 5136, y: 1536} -->

**@Buhle**

save user response here

<!-- { section: "300089b0-dc52-462d-a021-87b8f72682d1", x: 1296, y: 672} -->

**@Buhle**

save user response here

<!-- { section: "d8e1cc34-ee8f-4722-afc1-372ffee8cbb1", x: -1152, y: 648} -->

**@buhle**

Please add the other thingies here^

<!-- { section: "5594193d-060b-4914-a11a-b7414d9c3f1c", x: 14160, y: 1080} -->

**@Tam**

Stickers here are jpgs

<!-- { section: "bdc4adc9-e0b7-4d0f-a09a-a0c84759e5d9", x: 9552, y: 792} -->

**@Buhle please save user response here**

Double check with Colette but I think this name should be fine

DS note: Flow result: module2_attitudes {user input}

<!-- { section: "73191e51-68bc-483b-a938-140a9a16e885", x: 18824, y: 504} -->

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

<!-- { section: "b0503eb3-0d97-46ca-8edf-50debae4dca9", x: 240, y: -24} -->

```stack
card Message1 do
  write_result("module2_started", "yes")
  then(Message_2)
end

```

<!-- { section: "e96257b3-e0e2-417d-86d8-2f939f0ae789", x: 1320, y: -216} -->

```stack
card Message2_1 do
  write_result("module2_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "630f1fca-577d-49f8-93a0-a98e8e0f747b", x: 1320, y: 168} -->

```stack
card Message2_2 do
  write_result("module2_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "bcd6fc5e-e36d-44a4-89fb-14f79076183a", x: 4968, y: -48} -->

```stack
card Message8_1 do
  write_result("module2_beliefs", "a")
  then(Message_9_1)
end

```

<!-- { section: "61e7f09e-f4fb-4a9c-a8ff-d910d6d2dbd4", x: 4968, y: 264} -->

```stack
card Message8_2 do
  write_result("module2_beliefs", "b")
  then(Message_9_2)
end

```

<!-- { section: "82422245-b3cc-43a8-88b5-5f398aa1e495", x: 4968, y: 696} -->

```stack
card Message8_3 do
  write_result("module2_beliefs", "c")
  then(Message_9_3)
end

```

<!-- { section: "c04bdf1f-4fcf-4938-9b19-ea404f87e222", x: 16848, y: 48} -->

```stack
card Message23_1 do
  write_result("module2_behavioral_activation", "a")
  then(Message_24)
end

```

<!-- { section: "ee1934a9-9886-4095-a14c-518f9cc1e60e", x: 16896, y: 432} -->

```stack
card Message23_2 do
  write_result("module2_behavioral_activation", "b")
  then(Message_24)
end

```

<!-- { section: "8318f37f-f0e7-4e15-9932-0c805ab9522e", x: 16896, y: 792} -->

```stack
card Message23_3 do
  write_result("module2_behavioral_activation", "c")
  then(Message_24)
end

```

<!-- { section: "ba6fef3e-85b0-4407-92be-dfdd8db1d5e4", x: 15720, y: 384} -->

```stack
card Message22 do
  write_result("module2_mental_health", "@ref_message_22")
  then(Message_23)
end

```

<!-- { section: "5bf0c111-458f-4662-9a62-54f5108ee24a", x: 11976, y: -144} -->

```stack
card Message17_1 do
  write_result("module2_social_norms", "a")
  then(Message_18_1)
end

```

<!-- { section: "14fb6460-062c-4d22-9d4f-987c3c4d81cd", x: 12000, y: 192} -->

```stack
card Message17_2 do
  write_result("module2_social_norms", "b")
  then(Message_18_2)
end

```

<!-- { section: "851c12e5-6936-4235-a91f-308adf7d6140", x: 12000, y: 576} -->

```stack
card Message17_3 do
  write_result("module2_social_norms", "c")
  then(Message_18_3)
end

```

<!-- { section: "1461a57f-aaeb-422f-b474-8e90db007540", x: 7056, y: 192} -->

```stack
card Message10 do
  write_result("module2_social_support", "@ref_message_10")
  then(Message_11_1)
end

```

<!-- { section: "64811d14-baa8-4f63-98c1-db99e921a344", x: 9624, y: 168} -->

```stack
card Message13 do
  write_result("module2_attitudes", "@ref_message_13")
  then(Message_14_1)
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
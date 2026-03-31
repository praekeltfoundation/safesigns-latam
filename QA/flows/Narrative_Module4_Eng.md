<!-- { section: "0ebd15ee-1bae-4be5-bf73-020e91f2ff3b", x: -1200, y: -24} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "nm4")

```

<!-- { section: "1d808348-4b52-429d-bf73-0b4adaf55df8", x: 48, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 Welcome to the fourth episode of Pilar's story. We're already halfway through! Today we may find out what happened to Pilar!"
  )

  then(Message1)
end

```

<!-- { section: "670d4b4d-488d-408f-ba0b-e5e782e3bae8", x: -528, y: 96} -->

```stack
card Branch_7002ab, "Branch_7002ab", code_generator: "CONDITIONALS" do
  then(
    Message_1
    when contact.contact_module == "MODULE_3" and contact.arm == "NARRATIVE" and
           contact.onboarding_complete == true and contact.quiz_post_module3_complete == true
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "c460776a-f122-4eca-9e53-a3f8c13d9edf", x: 984, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time ", "Yes, great! 👍"]) do
      text(
        "Yesterday's challenge was to think about who would be your trusted person, did you accomplish it?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time ")
  then(Message2_2 when ref_Message_2 == "Yes, great! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "a98d7a33-e46c-415f-9a01-1c5daa36cdf3", x: 1032, y: -864} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "5d6f6a2c-be71-4111-94cc-cef72274cb7e", x: 2136, y: -96} -->

```stack
card Message_3_1, "Message_3_1", code_generator: "TEXT_MESSAGE" do
  text("Don't worry, you still have time. It is key to have your support network")
  then(Message_4)
end

```

<!-- { section: "a90a4e8b-c0f6-4e99-9844-4a26b7fcee0c", x: 2136, y: 408} -->

```stack
card Message_3_2, "Message_3_2", code_generator: "TEXT_MESSAGE" do
  text("Amazing, you know who you can trust!")
  then(Message_4)
end

```

<!-- { section: "2faeeb15-a0fe-42e4-b5f9-283e0e9e9bc4", x: 2616, y: 24} -->

```stack
card Message_4, "Message_4", code_generator: "TEXT_MESSAGE" do
  text(
    "Remember that if anything about Pilar's story or any question makes you feel uncomfortable, you can stop and come back when you feel ready. It is very important to me that you feel good!"
  )

  then(Message_5)
end

```

<!-- { section: "f36add87-ba6e-4436-8517-9ca9263378f1", x: 7416, y: -864} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10_1)
end

```

<!-- { section: "1c9d9242-56b3-4ce4-8b86-5cdada13dc35", x: 3216, y: 0} -->

```stack
card Message_5, "Message_5", code_generator: "TEXT_MESSAGE" do
  text("Send audio file NARRATIVE - CHAPTER 4 - PART 1")
  then(Message_6)
end

```

<!-- { section: "07aab1ce-f6f6-475c-9158-2004ad7c92b2", x: 3792, y: 0} -->

```stack
card Message_6, "Message_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["I heard the audio"]) do
      text("When you finish the audio, press the button I heard the audio")
    end

  then(Message_7 when ref_Message_6 == "I heard the audio")
  then(Catch_all_3)
end

```

<!-- { section: "e61ded93-8a51-4dc8-b531-03f6e6f46f93", x: 3816, y: -1080} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_6)
end

```

<!-- { section: "9f683e35-7b7d-4929-920c-3f177a2c1843", x: 5736, y: -168} -->

```stack
card Message_8_1, "Message_8_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Yeah! Sadly, in this situation it is normal for a person to feel anxious and overwhelmed, as this pressure can cause them to doubt themselves and their decisions. They may feel that they are not in control and that they are alone or that they cannot ask for help. If someone is in this situation, it is important to be able to talk about it with someone in their support network and make them feel safe and not judged."
  )

  then(Message_9)
end

```

<!-- { section: "3254ddd1-d5be-4b18-bf66-5e3264e9f2f1", x: 4512, y: 0} -->

```stack
card Message_7, "Message_7", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Anxious, overwhelmed", "﻿A bit uncomfortable", "Not a big deal"]) do
      text(
        "In the episode we hear that Pilar felt very pressured by Camilo to send him a photo. It is a common situation in the digital environment in which we live. How do you think someone who is under pressure to do something uncomfortable feels?"
      )
    end

  then(Message7_1 when ref_Message_7 == "Anxious, overwhelmed")
  then(Message7_2 when ref_Message_7 == "﻿A bit uncomfortable")
  then(Message7_3 when ref_Message_7 == "Not a big deal")
end

```

<!-- { section: "61282550-97dc-4a82-b146-abc1ab0f7468", x: 6456, y: -840} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_9)
end

```

<!-- { section: "bc63e912-b08c-4caf-b332-847e51fad09b", x: 6384, y: 24} -->

```stack
card Message_9, "Message_9", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Next audio"]) do
      text(
        "It is normal to feel anxious and overwhelmed by the pressure that others, such as friends or partners, can put on us. If you find yourself in this situation, seek support from someone within your support network. You are not alone, and it is essential that you feel supported and not judged. Let's see how Pilar does it! 🌸"
      )
    end

  then(Message_10 when ref_Message_9 == "Next audio")
  then(Catch_all_4)
end

```

<!-- { section: "8dcd7627-1caf-4c65-b38f-31f232ba3c38", x: 6960, y: 24} -->

```stack
card Message_10, "Message_10", code_generator: "TEXT_MESSAGE" do
  text("Send audio file NARRATIVE - CHAPTER 4 - PART 2")
  then(Message_10_1)
end

```

<!-- { section: "91d88556-f4e6-4e36-8333-fb6202cdab34", x: 8064, y: 0} -->

```stack
card Message_11, "Message_11", code_generator: "QUESTION" do
  ref_Message_11 =
    ask(
      "We all have characteristics that make us unique and special! Some of us are brave, like Pilar, who faces her fears with the support of her friends. Others of us are perseverant and are always there to help others. They are our superpowers! Do you think you have characteristics that make you special? How do you demonstrate them in your daily life? Write at least one and share why it is important to you."
    )

  then(Message11)
end

```

<!-- { section: "cf69cfa7-ac14-473a-ae70-4a8dd6d85746", x: 14640, y: -1080} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16)
end

```

<!-- { section: "65887f26-132b-4207-a583-5653235d5af8", x: 9048, y: -72} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Of course!", "I doubt it 🤔", "I don't think so🤷‍♀"]) do
      text(
        "In the episode we hear that there was a moment in which Pilar confronts herself about everything that is happening to her, to the point of thinking that it will be impossible for her to get out of this situation. However, after talking with her friend, Pilar remembers that she has overcome difficult things before and that, although what is happening is complex, she has the power to face the situation. Do you think that if something challenging happened to you, you would be able to cope?"
      )
    end

  then(Message12_1 when ref_Message_12 == "Of course!")
  then(Message12_2 when ref_Message_12 == "I doubt it 🤔")
  then(Message12_3 when ref_Message_12 == "I don't think so🤷‍♀")
  then(Catch_all_6)
end

```

<!-- { section: "0b28b2f0-cb58-4b80-ae7f-c2e628a8cf05", x: 9072, y: -1128} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "576c672f-3d40-48eb-ad1b-72467f412ceb", x: 10848, y: -360} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Brilliant! Believing in yourself is essential. We all have the ability to face challenges. Like Pilar, surely you have also overcome difficult moments before and that has made you stronger 🤩 

Talking to someone you trust (like Pilar did with Laura), reflecting on your superpower, can help you see the situation more clearly and find solutions."
  )

  then(Message_14)
end

```

<!-- { section: "7f1706ff-1e89-4bd7-872a-19a6f4351540", x: 10848, y: 96} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text(
    "It's normal to feel doubt in difficult situations, but it's important to remember that we all have the ability to face challenges. Like Pilar, surely you have also overcome difficult moments before and that has made you stronger 💪 

Talking to someone you trust (like Pilar did with Laura), reflecting on your superpower, can help you see the situation more clearly and find solutions."
  )

  then(Message_14)
end

```

<!-- { section: "ed75c802-d0e3-4b8d-9213-244117d12cf3", x: 10848, y: 600} -->

```stack
card Message_13_3, "Message_13_3", code_generator: "TEXT_MESSAGE" do
  text(
    "It's normal to feel doubt in difficult situations, but it's important to remember that we all have the ability to face challenges. Like Pilar, surely you have also overcome difficult moments before and that has made you stronger. Give yourself a chance to try it 🤗 

Talking to someone you trust (like Pilar did with Laura), reflecting on your superpower, can help you see the situation more clearly and find solutions."
  )

  then(Message_14)
end

```

<!-- { section: "3839d36c-e219-453b-b10f-71a9b75e4741", x: 12072, y: -24} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["I tell him it's good", "Say NO & he gets mad", "I'm not sure 🤷"]) do
      text(
        "Imagine that, when Pilar was dating Camilo, he asked her to stop going to train her favorite sport to spend more time with him. What do you think you would do if you were in that situation?"
      )
    end

  then(Message14_1 when ref_Message_14 == "I tell him it's good")
  then(Message14_2 when ref_Message_14 == "Say NO & he gets mad")
  then(Message14_3 when ref_Message_14 == "I'm not sure 🤷")
  then(Catch_all_7)
end

```

<!-- { section: "313d16ff-72bb-496d-bc37-e6f28d9b833b", x: 12048, y: -1032} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14)
end

```

<!-- { section: "7863de10-1914-44d9-976c-a1e0c2cd0799", x: 13728, y: -48} -->

```stack
card Message_15, "Message_15", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Next question"]) do
      text(
        "It is important to consider your own interests and not sacrifice what you like to please your partner. Recognizing what is important to you helps you maintain your identity and well-being in the relationship."
      )
    end

  then(Message_16 when ref_Message_15 == "Next question")
  then(Catch_all_8)
end

```

<!-- { section: "acf90817-918b-466e-a1cf-90d4daad34a0", x: 13896, y: -1152} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15)
end

```

<!-- { section: "05bad941-ce7d-48ee-b291-9e171a25a4b2", x: 14448, y: -48} -->

```stack
card Message_16, "Message_16", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16 =
    buttons(["When I'm with my bae", "At school", "A problem at home"]) do
      text(
        "We all have moments when we need that spark to be able to move forward. You, when have you most needed to remind yourself that you have a superpower? 

When it happens to me..."
      )
    end

  then(Message16_1 when ref_Message_16 == "When I'm with my bae")
  then(Message16_2 when ref_Message_16 == "At school")
  then(Message16_3 when ref_Message_16 == "A problem at home")
  then(Catch_all_5)
end

```

<!-- { section: "9953441a-e2ae-4b61-b327-5b8571d6d8aa", x: 15840, y: -264} -->

```stack
card Message_17_1, "Message_17_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for telling me! Sometimes there are couple situations that can become complex for many reasons. Your superpower surely helps you lead your relationship in a better way 🌟 Remember: our superpowers grow the more we put them into practice. Keep it up!"
  )

  then(Mesage_18)
end

```

<!-- { section: "b9365332-941f-410c-ae28-e1762cdab612", x: 16512, y: 120} -->

```stack
card Mesage_18, "Mesage_18", code_generator: "TEXT_MESSAGE" do
  text(
    "Remember that believing in yourself is key! We all face challenges and may hesitate due to pressure from others. Still, like Pilar, you have overcome difficult moments that have strengthened you. Talking to someone you trust, reflecting on your strengths, forming your own criteria based on the opinions of others or what you see online will help you find clarity and form your own path 🌸"
  )

  then(Message_19)
end

```

<!-- { section: "6b75608f-7f89-4013-91ea-09ba98a63156", x: 16704, y: -888} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "d9ef5a8f-ff0a-4cdc-9f63-6b2aa79922f1", x: 19632, y: -768} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "2f79ff1e-b4da-4243-9cc0-de415972b1f4", x: 17256, y: 144} -->

```stack
card Message_19, "Message_19", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["Send my stickers!"]) do
      text(
        "Very good! Have you heard episode 4 of Pilar's story 🥳 They are complex topics, so to help you navigate them, I leave you some great stickers on this topic that you can use to respond if you experience something similar."
      )
    end

  then(Message_20_sticker_1 when ref_Message_19 == "Send my stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "514ede98-7b27-48e5-8738-0a8d00968a97", x: 17304, y: -792} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_19)
end

```

<!-- { section: "39d12d5e-f4b1-4ad6-bd87-b239295991b1", x: 19392, y: -72} -->

```stack
card Message_20_sticker_6, "Message_20_sticker_6", code_generator: "MEDIA_IMAGE" do
  image("532f295d-f384-4f55-89e7-cf017543483d-Módulo4_Ubicación2.png")
  text("")
  then(Message_21)
end

```

<!-- { section: "ea2f4ff2-9497-4e8c-b3f0-cdc407d78355", x: 19848, y: -48} -->

```stack
card Message_21, "Message_21", code_generator: "TEXT_MESSAGE" do
  text("We all have a superpower somewhere in our lives.")
  then(Message_22)
end

```

<!-- { section: "1527f25c-f2b5-4e4c-8455-cfcab5d76e7b", x: 18888, y: -1080} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "b12c9692-a57e-46a3-a66b-be2ff865567a", x: 20328, y: -24} -->

```stack
card Message_22, "Message_22", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["Supported", "Powerful", "Free"]) do
      text(
        "Now I'm going to leave you this challenge: Do you remember that superpower you have? For tomorrow, think about a time when this superpower made a difference for you. It could be a particular achievement or just examples of a good day. How did it make you feel?"
      )
    end

  then(Message22_1 when ref_Message_22 == "Supported")
  then(Message22_2 when ref_Message_22 == "Powerful")
  then(Message22_3 when ref_Message_22 == "Free")
  then(Catch_all_13)
end

```

<!-- { section: "cd9e23bf-25d6-4aff-b59e-af02881a651e", x: 20544, y: -672} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_22)
end

```

<!-- { section: "f187ff02-4342-4ada-beb7-1f5b711ecf4a", x: 22872, y: 624} -->

```stack
card Message_23, "Message_23", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_23 =
    buttons(["I want to know!🧐"]) do
      text(
        "Ok friend, that's all for today. Get ready because tomorrow's episode is going to be amazing! What do you think Pilar and Laura will do to confront Camilo? Find out tomorrow!"
      )
    end

  then(Profile_c75e44 when ref_Message_23 == "I want to know!🧐")
  then(Catch_all_14)
end

```

<!-- { section: "df5ad91d-f14e-4f3b-a0a7-9d2000b9afcd", x: 23808, y: 720} -->

```stack
card Message_24, "Message_24", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(ModuleCompleted)
end

```

<!-- { section: "ad8973aa-3c5b-45da-8e94-7d79f6f5fe83", x: 22992, y: -144} -->

```stack
card Catch_all_14, "Catch_all_14", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_23)
end

```

<!-- { section: "1b070273-93e3-4164-94c8-051d1b098519", x: 23376, y: 720} -->

```stack
card Profile_c75e44, "Profile_c75e44", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_4")
  then(Message_24)
end

```

<!-- { section: "74de0812-a735-46f1-81a6-c6f66df80c86", x: 5736, y: 456} -->

```stack
card Message_8_2, "Message_8_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Although it may seem like something minor and something that can be easily gotten away from, in this situation it is normal for a person to feel anxious and overwhelmed, as this pressure can make them doubt themselves and their decisions. They may feel that they are not in control and that they are alone or that they cannot ask for help. If someone is in this situation, it is important to be able to talk about it with someone in their support network and make them feel safe and not judged."
  )

  then(Message_9)
end

```

<!-- { section: "cad86c36-4046-408d-bb30-feee0a29a94a", x: 5712, y: 1128} -->

```stack
card Message_8_3, "Message_8_3", code_generator: "TEXT_MESSAGE" do
  text(
    "Although there are people who may feel stronger to avoid a situation like this, in this case it is normal for a person to feel anxious and overwhelmed, as this pressure can make them doubt themselves and their decisions. They may feel that they are not in control and that they are alone or that they cannot ask for help. If someone is in this situation, it is important to be able to talk about it with someone in their support network and make them feel safe and not judged."
  )

  then(Message_9)
end

```

<!-- { section: "954cc460-d6ef-4802-869b-4421349821f5", x: 7488, y: 0} -->

```stack
card Message_10_1, "Message_10_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_1 =
    buttons(["I heard the audio!"]) do
      text("When you finish the audio, press the button I heard the audio")
    end

  then(Message_11 when ref_Message_10_1 == "I heard the audio!")
  then(Catch_all_2)
end

```

<!-- { section: "1be798e6-36db-4748-a8f1-99fb8165cf01", x: 15816, y: 144} -->

```stack
card Message_17_2, "Message_17_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for telling me! Sometimes it is not easy to navigate school situations that can become complicated for many reasons. Your superpower will surely help you handle these challenges better🌟 Remember: our superpowers grow the more we put them into practice. Keep it up!"
  )

  then(Mesage_18)
end

```

<!-- { section: "d57dca88-9237-457b-8fe5-7dbbdba1d58e", x: 15816, y: 528} -->

```stack
card Message_17_3, "Message_17_3", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for telling me! Sometimes it is not easy to handle situations at home that can become complex for many reasons. Your superpower surely helps you better navigate your relationships at home🌟 Remember: our superpowers grow the more we put them into practice. Keep it up!"
  )

  then(Mesage_18)
end

```

<!-- { section: "6b7e0315-8e32-4613-ab5a-f4fab5a6060d", x: 18936, y: -48} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("d96579f6-fea7-4c4b-bb68-789365227cf4-Módulo4_Ubicación1.png")
  text("")
  then(Message_20_sticker_6)
end

```

<!-- { section: "9c1b5cdd-b2cd-4915-a3da-c36c04af714a", x: 17904, y: -456} -->

```stack
card Message_20_sticker_1, "Message_20_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("a1262c1b-cd52-45f1-8398-9b6349bddc51-Módulo4_AltoAhi.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "7bb30103-3c49-44f9-b1b5-5040778f1f84", x: 17880, y: 0} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("af7ed3c2-1657-4b9f-a0c2-6cc74fc38fa3-Módulo4_No.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "48be4881-0ff6-4edb-9467-65f35d9bc2a7", x: 18456, y: -432} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("1b5e5687-5ab2-4867-8f35-a15a3e053827-Módulo4_Nograsias.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "f9c8c6de-dc13-4e2c-a444-43f1e2249051", x: 18432, y: 72} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("a3debebb-2f24-41f5-a264-94c9b3331511-Módulo4_Toma.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "991f0c33-58cf-42d5-82c3-41bb064a543e", x: 8472, y: 360} -->

**@Buhle**

Please save users response here,

**DS note:** Flow result: module4_self_reflection {user input}

<!-- { section: "3a0dc2d2-7d0c-4067-ba43-36264d8e15eb", x: 9144, y: 648} -->

**@Buhle**

Please save users response here

<!-- { section: "ba0e059c-9265-4f3c-aaee-1a1ef580eb40", x: 12240, y: 480} -->

**@Buhle**

Please save insights here

<!-- { section: "e3a823d9-388f-4886-9609-cd8925e3457b", x: 17808, y: 528} -->

**@TAm**

Stickers are png

<!-- { section: "1bdcaf87-bb4c-409f-bc96-8c8f6bd037c0", x: 20496, y: 552} -->

**@Buhle**

Please save users response here

need a variable /insight name

<!-- { section: "e7bc375d-5c6f-4630-acb4-4894ab55141f", x: -504, y: 576} -->

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

<!-- { section: "f3402c1c-1045-48cf-bed6-5fbab5c80743", x: 23328, y: 936} -->

Update contact field, contact module = Module 4 ✅

<!-- { section: "311b957c-dc19-4660-8950-a2ce35278de2", x: 4464, y: 552} -->

**@Buhle**

Please save variables here and then link them to their messages

<!-- { section: "7c7924d9-74d8-4880-982a-3b6a904e1d85", x: 14448, y: 456} -->

**@buhle**

Please save the insights here

<!-- { section: "04333e56-d87b-47e6-b30e-a4910033515e", x: 8496, y: -72} -->

```stack
card Message11 do
  write_result("module4_self_reflection", "@ref_message_11")
  then(Message_12)
end

```

<!-- { section: "39ab7a19-59a6-43e1-b730-95df2591a13d", x: 24432, y: 648} -->

```stack
card ModuleCompleted do
  log("Module 4 Complete")
  write_result("module4_completed", "yes")

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  next_engagement_time = datetime_add(tomorrow, 13, "h")

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
  then(Message_23)
end

```

<!-- { section: "87c3a0c0-1681-4ca5-b9c8-d30ff485b7b2", x: 21576, y: 312} -->

```stack
card Message22_2 do
  write_result("module4_behavioral_activation", "b")
  then(Message_23)
end

```

<!-- { section: "bd77c3e3-817a-4249-82fc-67b8588d3f1f", x: 21600, y: 816} -->

```stack
card Message22_3 do
  write_result("module4_behavioral_activation", "c")
  then(Message_23)
end

```

<!-- { section: "b9805cbc-5875-4b18-a1b8-8d71e5a058ae", x: 15072, y: -528} -->

```stack
card Message16_1 do
  write_result("module4_social_norms", "a")
  then(Message_17_1)
end

```

<!-- { section: "de030d2d-45ff-4364-bcc3-6a07c12510f3", x: 15144, y: -24} -->

```stack
card Message16_2 do
  write_result("module4_social_norms", "b")
  then(Message_17_2)
end

```

<!-- { section: "2279fd01-e44e-436e-acd7-d48102c8f60c", x: 15192, y: 384} -->

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

<!-- { section: "0e178ca9-9d4b-48bb-a0fe-c96c32f81951", x: 12960, y: -72} -->

```stack
card Message14_2 do
  write_result("module4_attitudes", "b")
  then(Message_15)
end

```

<!-- { section: "238695af-6fea-4853-a127-a43baefa2677", x: 12960, y: 384} -->

```stack
card Message14_3 do
  write_result("module4_attitudes", "c")
  then(Message_15)
end

```

<!-- { section: "613228d3-a21e-4c4e-bfd5-9c0c90e5702c", x: 9840, y: -384} -->

```stack
card Message12_1 do
  write_result("module4_beliefs_self_efficacy", "a")
  then(Message_13_1)
end

```

<!-- { section: "f8f95d88-b207-4e7b-b385-3762d112d49e", x: 9840, y: 48} -->

```stack
card Message12_2 do
  write_result("module4_beliefs_self_efficacy", "b")
  then(Message_13_2)
end

```

<!-- { section: "cc48eab9-0d71-458d-b6e6-815c7578a7a3", x: 9840, y: 432} -->

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
<!-- { section: "c24dd99a-d9d3-4ff5-b8a9-3295f268436e", x: -1200, y: -24} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "gm4")

```

<!-- { section: "02d0e14f-0490-4ce0-92a3-c099af77ec30", x: -672, y: 168} -->

```stack
card Branch_7002ab, "Branch_7002ab", code_generator: "CONDITIONALS" do
  then(
    Message_1
    when contact.contact_module == "MODULE_3" and contact.arm == "GAMIFIED" and
           contact.onboarding_complete == true
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "28d044ea-0aa5-427d-b358-515999a20709", x: -72, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Now, we are ready to listen to the fourth episode of Pilar and Mari's podcast. We're already halfway through!🏃‍♀️‍➡️"
  )

  then(Message1)
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
card Message_4, "Message_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Okay 👍"]) do
      text("Remember that the longer your streak, the more stickers you accumulate!🙌")
    end

  then(Message_5 when ref_Message_4 == "Okay 👍")
  then(Catch_all_2)
end

```

<!-- { section: "e16aa118-dfd6-4a2c-9240-65cfe95965c4", x: 2616, y: -1104} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "827ff4f3-5473-49f6-9dce-21e3e59f0418", x: 3312, y: 0} -->

```stack
card Message_5, "Message_5", code_generator: "TEXT_MESSAGE" do
  text(
    "In this episode Pilar and Mari will talk about how powerful we can be 💪 and the changes we can make in our lives."
  )

  then(Message_6)
end

```

<!-- { section: "07aab1ce-f6f6-475c-9158-2004ad7c92b2", x: 3792, y: 0} -->

```stack
card Message_6, "Message_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Ok 👌"]) do
      text(
        "Remember that if there is something that Pilar and Mari talk about or a question that makes you feel uncomfortable, you can stop and come back when you feel ready. For me it is very important that you feel good!🫰"
      )
    end

  then(Message_7 when ref_Message_6 == "Ok 👌")
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

<!-- { section: "54928e81-88cd-4c53-87dc-104d09136cdd", x: 5592, y: -48} -->

```stack
card Messgae_8, "Messgae_8", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Messgae_8 =
    buttons(["I heard the audio"]) do
      text("When this part of the podcast ends, press the I heard the audio button")
    end

  then(Message_9 when ref_Messgae_8 == "I heard the audio")
  then(Catch_all_4)
end

```

<!-- { section: "3254ddd1-d5be-4b18-bf66-5e3264e9f2f1", x: 4512, y: 0} -->

```stack
card Message_7, "Message_7", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M4_P1")
  then(Messgae_8)
end

```

<!-- { section: "04dc5990-9f19-4fa8-8735-b3f496c84c61", x: 5472, y: -1104} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Messgae_8)
end

```

<!-- { section: "dd87831b-9660-479c-a68f-43a5a3ea3dd1", x: 6168, y: -48} -->

```stack
card Message_9, "Message_9", code_generator: "TEXT_MESSAGE" do
  text(
    "As Pilar and Mari said, we all have characteristics that make us the people we are and make us special, they are our superpower! 💪 

Some of us are very persevering people and we show it on the soccer field ⚽ others are curious and that's why we love to learn📚"
  )

  then(Message_10)
end

```

<!-- { section: "c4a5f8a6-c74a-4d2c-be5c-dc8dd3a70896", x: 6576, y: -48} -->

```stack
card Message_10, "Message_10", code_generator: "QUESTION" do
  ref_Message_10 =
    ask(
      "What characteristics of yours do you feel make you special and where do you demonstrate them? Write at least one and tell me why it is important to you"
    )

  then(Message10)
end

```

<!-- { section: "eab054d6-0d3e-486b-9a4f-c35b877b8112", x: 8184, y: -48} -->

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

<!-- { section: "5731ff24-f7af-4e8d-bc2f-3c94c099a7b3", x: 7656, y: -216} -->

```stack
card Message_11, "Message_11", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M4_P2")
  then(Message_11_1)
end

```

<!-- { section: "230d7de6-9076-499e-b1bc-a74fbb97987e", x: 8112, y: -1032} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11_1)
end

```

<!-- { section: "65887f26-132b-4207-a583-5653235d5af8", x: 9048, y: -72} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["In couple fights", "In school challenges", "In trouble at home"]) do
      text(
        "We all have moments when we need that spark to be able to move forward. You, when have you most needed to remind yourself that you have a superpower?"
      )
    end

  then(Message12_1 when ref_Message_12 == "In couple fights")
  then(Message12_2 when ref_Message_12 == "In school challenges")
  then(Message12_3 when ref_Message_12 == "In trouble at home")
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
    "Thanks for telling me! Sometimes there are couple situations that can become complex for many reasons. Your superpower surely helps you lead your relationship in a better way 🌟 Remember: our superpowers grow the more we put them into practice. Keep it up!"
  )

  then(Message_14_1)
end

```

<!-- { section: "7f1706ff-1e89-4bd7-872a-19a6f4351540", x: 10848, y: 96} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for telling me! Sometimes it is not easy to navigate school situations that can become complicated for many reasons. Your superpower will surely help you handle these challenges better🌟 Remember: our superpowers grow the more we put them into practice. Keep it up!"
  )

  then(Message_14_1)
end

```

<!-- { section: "9d51f494-c585-4a73-b1bd-e510aa263fac", x: 10848, y: 528} -->

```stack
card Message_13_3, "Message_13_3", code_generator: "TEXT_MESSAGE" do
  text(
    "Thanks for telling me! Sometimes it is not easy to handle situations at home that can become complex for many reasons. Your superpower surely helps you better navigate your relationships at home🌟 Remember: our superpowers grow the more we put them into practice. Keep it up!"
  )

  then(Message_14_1)
end

```

<!-- { section: "3839d36c-e219-453b-b10f-71a9b75e4741", x: 12072, y: -24} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_15 when ref_Message_14 == "I heard the audio")
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

<!-- { section: "dcc6d265-830c-4edf-8440-0eadef392bcd", x: 13080, y: -72} -->

```stack
card Message_15, "Message_15", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Of course! 💪", "Sometimes I doubt it", "I don't think so🤷‍♀"]) do
      text(
        "I tell you that Pilar and Mari had had the dream of creating this podcast since they were in seventh grade. 

When they started they had many doubts, but finally they took the risk and now you are listening to it 🫰 

In your case, do you think that if you set out to do something you would do everything possible to achieve it?"
      )
    end

  then(Message15_1 when ref_Message_15 == "Of course! 💪")
  then(Message15_2 when ref_Message_15 == "Sometimes I doubt it")
  then(Message15_3 when ref_Message_15 == "I don't think so🤷‍♀")
  then(Catch_all_8)
end

```

<!-- { section: "457ab1b1-d9bb-4d78-819f-7f8d4882051b", x: 13008, y: -1176} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15)
end

```

<!-- { section: "f46b7cb7-0ef2-456b-b7c1-54dac3438b6e", x: 14832, y: -144} -->

```stack
card Message_16_1, "Message_16_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Brilliant! Believing in yourself is essential. We all have the ability to face challenges. Like Pilar and Mari did, surely you have also overcome difficult moments before and that has made you stronger 🤩 

Talking to someone you trust and reflecting on your superpower can help you see the situation more clearly and find solutions."
  )

  then(Message_17)
end

```

<!-- { section: "2149b66f-6345-4820-887e-c8af2b049c6e", x: 14808, y: 384} -->

```stack
card Message_16_2, "Message_16_2", code_generator: "TEXT_MESSAGE" do
  text(
    "It is normal to have doubts in difficult situations, but it is important to remember that we all have the ability to face challenges. Pilar and Mari also hesitated at first, but they persevered, they are stronger now and they are achieving their dream 💪 

Talking to someone you trust, reflecting on your superpower, can help you see the situation more clearly and find solutions."
  )

  then(Message_17)
end

```

<!-- { section: "f42c05c0-8f86-4bdc-8f2a-090c1a8b006d", x: 14832, y: 984} -->

```stack
card Message_16_3, "Message_16_3", code_generator: "TEXT_MESSAGE" do
  text(
    "It is normal to have doubts in difficult situations, but it is important to remember that we all have the ability to face challenges. Like Pilar and Mari, surely you have also overcome difficult moments before and that has made you stronger. Give it a try 🤗 

Talking to someone you trust, reflecting on your superpower, can help you see the situation more clearly and find solutions."
  )

  then(Message_17)
end

```

<!-- { section: "99c45f8f-877f-4e24-994c-48383f6213c5", x: 15744, y: 384} -->

```stack
card Message_17, "Message_17", code_generator: "TEXT_MESSAGE" do
  text("Now let's think about these situations in the context of relationships 🤔")
  then(Mesage_18)
end

```

<!-- { section: "737e0f80-2fe0-4dcb-ad34-5f791fbc5938", x: 16464, y: 384} -->

```stack
card Mesage_18, "Mesage_18", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Mesage_18 =
    buttons(["I tell him it's good", "I say NO & he's mad", "I'm not sure 🤷"]) do
      text(
        "Imagine that Mari's partner has asked her to stop going to train in her favorite sport to be with him. What do you think you would do if you were in that situation?"
      )
    end

  then(Message18_1 when ref_Mesage_18 == "I tell him it's good")
  then(Message18_2 when ref_Mesage_18 == "I say NO & he's mad")
  then(Message18_3 when ref_Mesage_18 == "I'm not sure 🤷")
  then(Catch_all_9)
end

```

<!-- { section: "28df6e5a-2a3f-4d2b-b553-f6edabb64d9a", x: 16416, y: -552} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Mesage_18)
end

```

<!-- { section: "2c698575-e88c-4c99-b0b7-a1872d1c7a97", x: 18456, y: 264} -->

```stack
card Message_19, "Message_19", code_generator: "TEXT_MESSAGE" do
  text(
    "It is important to consider your own interests and not sacrifice what you like to please your partner. Recognizing what is important to you helps you maintain your identity and well-being in the relationship 🫶"
  )

  then(Message_20)
end

```

<!-- { section: "9736ba29-64d7-4cfa-ae54-d7bd27e59ee0", x: 19128, y: 600} -->

```stack
card Message_20, "Message_20", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["Anxious, overwhelmed", "A bit uncomfortable", "It's not a big deal"]) do
      text(
        "Another thing Mari's boyfriend has done is ask her for intimate photos. She felt very pressured by him to send him a photo. As you know, these types of situations are common nowadays... 📸 

How do you think Marí feels being under pressure to do something uncomfortable?"
      )
    end

  then(Message20_1 when ref_Message_20 == "Anxious, overwhelmed")
  then(Message20_2 when ref_Message_20 == "A bit uncomfortable")
  then(Message20_3 when ref_Message_20 == "It's not a big deal")
  then(Catch_all_10)
end

```

<!-- { section: "5b7fbae1-5a7e-4dfd-b480-00b765a7dd0e", x: 20760, y: -24} -->

```stack
card Message_21_1, "Message_21_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Yeah! Sadly, in this situation it is normal for a person to feel anxious and overwhelmed, as this pressure can make them doubt themselves and their decisions 😣 

These situations can make you feel like you are not in control and alone or that you can't ask for help. If someone is in this situation, it is important to be able to talk about it with someone in their support network and make them feel accompanied and not judged 🫰"
  )

  then(Message_22)
end

```

<!-- { section: "6b8dc7fa-5efe-4895-9629-0a0df5cee35b", x: 20760, y: 744} -->

```stack
card Message_21_2, "Message_21_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Although it may seem like something minor and something that one can easily get rid of, in this situation it is normal for a person to feel anxious and overwhelmed, as this pressure can make them doubt themselves and their decisions 😣 

These situations can make you feel like you are not in control and alone or that you can't ask for help. If someone is in this situation, it is important to be able to talk about it with someone in their support network and make them feel accompanied and not judged 🫰"
  )

  then(Message_22)
end

```

<!-- { section: "255af5b3-2c47-47eb-b8da-3884b0576876", x: 20784, y: 1512} -->

```stack
card Message_21_3, "Message_21_3", code_generator: "TEXT_MESSAGE" do
  text(
    "Although there are people who may feel stronger to avoid a situation like this, in this case it is normal for a person to feel anxious and overwhelmed, since the pressure can make them doubt themselves and their decisions 😣 

These situations can make someone feel like they are not in control and alone or unable to ask for help. If someone is in this situation, it is important to be able to talk about it with a person from their support network and make them feel accompanied and not judged 🫰"
  )

  then(Message_22)
end

```

<!-- { section: "d45ee219-7974-42d0-ae2d-eeae945fce0c", x: 19032, y: -816} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_20)
end

```

<!-- { section: "732b9ab2-1691-4d05-8ad5-c644366f47e8", x: 21984, y: 600} -->

```stack
card Message_22, "Message_22", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_22 =
    buttons(["Send my stickers!"]) do
      text(
        "Wow, you've completed episode 4 of the podcast! 🥳 Today I have more stickers for you to use and help you remember how amazing you are 🤩"
      )
    end

  then(Message_23_sticker_1 when ref_Message_22 == "Send my stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "b5251fc3-99ea-4dba-b8a9-ae685b58f5ed", x: 21984, y: -744} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_22)
end

```

<!-- { section: "9266c86f-7135-4af2-8993-375a218e9f60", x: 22704, y: -168} -->

```stack
card Message_23_sticker_1, "Message_23_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("43f0d5da-a602-4d2a-894e-ae2ad8db05ec-Módulo4_AltoAhi.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "2d2a71fa-0ceb-4443-b071-95a589658b44", x: 23352, y: 624} -->

```stack
card Message_24, "Message_24", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["Understood! 🫡"]) do
      text(
        "You're on a streak of 4 out of 6 days in the podcast challenge! You go all out for your perfect streak 🌟"
      )
    end

  then(Message_25 when ref_Message_24 == "Understood! 🫡")
  then(Catch_all_12)
end

```

<!-- { section: "8e24cfcd-4ddc-49ed-8b80-2a76b735d5a8", x: 23400, y: -288} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_24)
end

```

<!-- { section: "de569d8c-1e09-43ee-83dc-2f006be1d503", x: 24168, y: 624} -->

```stack
card Message_25, "Message_25", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_25 =
    buttons(["Supported", "Powerful", "Free"]) do
      text(
        "Now I'm going to leave you this challenge: Do you remember that superpower you have? For tomorrow, think about a time when this superpower made a difference for you. It could be a particular achievement or just examples of a good day. How did it make you feel?"
      )
    end

  then(Message25_1 when ref_Message_25 == "Supported")
  then(Message25_2 when ref_Message_25 == "Powerful")
  then(Message25_3 when ref_Message_25 == "Free")
  then(Catch_all_13)
end

```

<!-- { section: "5467d4be-fdeb-4a40-a659-1528e16e53c1", x: 24120, y: -336} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_25)
end

```

<!-- { section: "510b216f-a748-42b2-85c1-50d436e8a471", x: 26064, y: 720} -->

```stack
card Message_26, "Message_26", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_26 =
    buttons(["Understood 🌸"]) do
      text(
        "The best friend! Keep feeling that way and for now this was all for today. Get ready because in tomorrow's episode we will talk about limits in relationships or friendships! ❤️"
      )
    end

  then(Message_27 when ref_Message_26 == "Understood 🌸")
  then(Catch_all_14)
end

```

<!-- { section: "4a456419-26ef-45f5-aaf5-297bc27c9917", x: 26904, y: 840} -->

```stack
card Message_27, "Message_27", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_c75e44)
end

```

<!-- { section: "c2933ffd-975d-420a-b152-63adb6b912a7", x: 26184, y: -240} -->

```stack
card Catch_all_14, "Catch_all_14", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_26)
end

```

<!-- { section: "fc8f920c-a379-4a62-bf41-daabb6a3ac04", x: 27360, y: 768} -->

```stack
card Profile_c75e44, "Profile_c75e44", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_4")
  then(ModuleCompleted)
end

```

<!-- { section: "79853a45-d656-402b-89d4-de2f224fa4c1", x: 11592, y: 0} -->

```stack
card Message_14_1, "Message_14_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio - G_M4_P3")
  then(Message_14)
end

```

<!-- { section: "eb063146-8b6e-4e0e-80fd-0387a751a7fa", x: 22704, y: 336} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("25852ade-eacc-4ed4-a7e3-d5fd4d797db1-Módulo4_No.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "7b17026f-1231-4aea-9f8d-aa22dfb3abab", x: 22728, y: 864} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("b3188d26-7b63-4ce4-a3bb-1d8807a57c19-Módulo4_Nograsias.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "a7e9bdea-699f-42d4-ba7b-fd965aea1b4b", x: 22704, y: 1392} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("edc4d6cd-1039-4dc6-a5d7-d16399e31786-Módulo4_Toma.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "c2685e37-d009-4f5c-9486-466463acdf60", x: 22680, y: 1896} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("024e4f14-8aec-4a07-8127-aaa06a919655-Módulo4_Ubicación1.png")
  text("")
  then(Sticker_6)
end

```

<!-- { section: "547c5c29-fb1a-4314-ac95-ac5ca9fc2f7b", x: 23280, y: 1848} -->

```stack
card Sticker_6, "Sticker_6", code_generator: "MEDIA_IMAGE" do
  image("642669d0-d17a-4ee0-92dc-50a9894c135f-Módulo4_Ubicación2.png")
  text("")
  then(Message_24)
end

```

<!-- { section: "d5056623-20e9-47e4-972d-23d1143d3e86", x: 3864, y: 504} -->

Emoji does not show up

<!-- { section: "c54a7610-d3e2-4790-be46-81f64c75d8dc", x: 4632, y: 192} -->

missing audio here, add audio here

<!-- { section: "8b1c7941-6ffd-4da7-ae70-ea3db66d24a5", x: 6960, y: 312} -->

**@Buhle**

Please save users response here,

**DS note:** Flow result: module4_self_reflection {user input}

<!-- { section: "27c4c015-0ace-4da3-8337-2cfb27d45c6b", x: 7992, y: 312} -->

We cannot have audio as button messages, will need extra copy here

<!-- { section: "e980cb5c-168d-4746-a54c-2c3f4ee5db35", x: 9144, y: 360} -->

**@Buhle**

Please save users response here

<!-- { section: "a3034cb3-c0fd-4f2b-abae-513ff1724b9c", x: 11688, y: 192} -->

Audio missing here

<!-- { section: "b88cc17a-100e-4357-b12e-b2075eeec322", x: 13248, y: 600} -->

**@Buhle**

Please save insights here

<!-- { section: "9354a787-d1d0-4791-bdfb-abd0a442d5d6", x: 16656, y: 888} -->

**@buhle**

Please save the insights here

<!-- { section: "708c1a99-2f8b-4966-8d1f-cb1c6331d7da", x: 18480, y: 552} -->

Emoji does not show up

<!-- { section: "5699c88e-5140-4101-8f2b-497b3fb1f67b", x: 22200, y: 1008} -->

**@Tam**

stickers are PNG here

<!-- { section: "c77dc82d-6798-4bad-9738-54b73500677f", x: 24960, y: 1560} -->

save users response here

need a variable /insight name

<!-- { section: "df6509f4-8e5f-4c64-8085-2f070c44119c", x: -504, y: 456} -->

**@Buhle**

Please add the other thingies here^

<!-- { section: "397712e0-1057-477d-952b-87b06e5927ba", x: 312, y: 456} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

**DS note:** Flow result: module4_started (yes)

<!-- { section: "1325fece-a1cb-4b05-98ca-eb80462802d4", x: 1200, y: 408} -->

**@Buhle**

Please save insight here

<!-- { section: "075d7660-5f84-465f-80ca-b4fcab280230", x: 19248, y: 1200} -->

**@buhle**

Please save the insights here

<!-- { section: "37dbc6ff-f74d-438a-8147-5ce57bdf524c", x: 27504, y: 1104} -->

**@Buhle**

**DS note:** Flow result: module4_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "5457f099-63e6-4731-9634-151cbd53541c", x: 28200, y: 1224} -->

**@Buhle**

Schedule Module 5 to start next day (6pm , Time zone is Colombia / Bogota time)

Update contact.next_engagement_time

<!-- { section: "17629c75-a127-4e66-89c5-41f042c7f700", x: 26688, y: 1056} -->

Update contact field, contact module = Module 4 ✅

<!-- { section: "feafc536-9669-43dc-a38b-3c1bfb8c144f", x: 456, y: -24} -->

```stack
card Message1 do
  write_result("module4_started", "yes")
  then(Message_2)
end

```

<!-- { section: "73d55665-bf29-42d9-99da-d3cdac71eccb", x: 7056, y: -72} -->

```stack
card Message10 do
  write_result("module4_self_reflection", "@ref_message_10")
  then(Message_11)
end

```

<!-- { section: "a6b8d1a8-3cd0-403e-b843-c5a6f0a02c75", x: 28152, y: 744} -->

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

<!-- { section: "d1a2b9f0-fa28-4b3e-97b7-cddcb747c105", x: 1512, y: -144} -->

```stack
card Message2_1 do
  write_result("module4_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "48dc59d2-41d1-49eb-9f8d-cf3246950572", x: 1512, y: 240} -->

```stack
card Message2_2 do
  write_result("module4_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "fd7ab27d-9c30-41e8-bf8c-d45298f6d21f", x: 9888, y: -312} -->

```stack
card Message12_1 do
  write_result("module4_general", "a")
  then(Message_13_1)
end

```

<!-- { section: "88e10bdf-4818-4cd9-b2c6-e5b22450ed48", x: 9888, y: 72} -->

```stack
card Message12_2 do
  write_result("module4_general", "b")
  then(Message_13_2)
end

```

<!-- { section: "1b2696e2-a87e-4aaa-88af-a52ec5d111ea", x: 9864, y: 456} -->

```stack
card Message12_3 do
  write_result("module4_general", "c")
  then(Message_13_3)
end

```

<!-- { section: "b444a41f-bbd8-4511-b972-bc320bfcf56f", x: 13920, y: -216} -->

```stack
card Message15_1 do
  write_result("module4_beliefs_self_efficacy", "a")
  then(Message_16_1)
end

```

<!-- { section: "99ef11b4-5069-4122-83e7-2d4914fccdb2", x: 13968, y: 144} -->

```stack
card Message15_2 do
  write_result("module4_beliefs_self_efficacy", "b")
  then(Message_16_2)
end

```

<!-- { section: "b3f953a5-9ef7-4cc4-80f2-b35dcb1282d6", x: 13992, y: 504} -->

```stack
card Message15_3 do
  write_result("module4_beliefs_self_efficacy", "c")
  then(Message_16_3)
end

```

<!-- { section: "1c658a5f-4f7e-4c51-adf1-52a3a363fd45", x: 17328, y: 24} -->

```stack
card Message18_1 do
  write_result("module4_attitudes", "a")
  then(Message_19)
end

```

<!-- { section: "3a4f2061-c7f0-4261-bd3f-bdcb17f3bde9", x: 17352, y: 504} -->

```stack
card Message18_2 do
  write_result("module4_attitudes", "b")
  then(Message_19)
end

```

<!-- { section: "a13ba882-7473-4415-9ff1-ad14cc4e0421", x: 17424, y: 936} -->

```stack
card Message18_3 do
  write_result("module4_attitudes", "c")
  then(Message_19)
end

```

<!-- { section: "69ab0955-610b-4065-b736-be6144ccea7a", x: 19848, y: 336} -->

```stack
card Message20_1 do
  write_result("module4_attitudes", "a")
  then(Message_21_1)
end

```

<!-- { section: "266b6745-bb73-4e07-b37f-280c21640429", x: 19872, y: 720} -->

```stack
card Message20_2 do
  write_result("module4_attitudes", "b")
  then(Message_21_2)
end

```

<!-- { section: "7049dc27-287c-41a0-b154-8fa3baf04a85", x: 19872, y: 1104} -->

```stack
card Message20_3 do
  write_result("module4_attitudes", "c")
  then(Message_21_3)
end

```

<!-- { section: "2df81f6f-1b23-4680-b0f3-36fd92239fcf", x: 24936, y: 216} -->

```stack
card Message25_1 do
  write_result("module4_behavioral_activation", "a")
  then(Message_26)
end

```

<!-- { section: "b3ea9938-e294-4071-9c70-f2af0bc7c5a7", x: 24912, y: 744} -->

```stack
card Message25_2 do
  write_result("module4_behavioral_activation", "b")
  then(Message_26)
end

```

<!-- { section: "828659f9-add5-41da-89d6-df6c95adb40e", x: 24936, y: 1176} -->

```stack
card Message25_3 do
  write_result("module4_behavioral_activation", "c")
  then(Message_26)
end

```

<!-- { section: "7297b375-cdbd-46ae-941b-d61bc0f8aded", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
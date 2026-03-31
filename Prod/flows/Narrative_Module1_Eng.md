<!-- { section: "4b925950-7558-452c-95ff-0532f39698eb", x: -2808, y: -216} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "nm1")

```

<!-- { section: "de73b262-04bc-4eb8-a1de-26d0f309b685", x: -2256, y: -72} -->

```stack
card Branch_9e8873, "Branch_9e8873", code_generator: "CONDITIONALS" do
  then(Message_1 when contact.onboarding_complete == true and contact.arm == "NARRATIVE")
  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "2b2ef48b-c615-455a-94c7-cb5ddf6fd95b", x: -1752, y: -72} -->

```stack
card Message_1, "Message_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_1 =
    buttons(["Understood! 👍"]) do
      text(
        "Hello! 👋 Today we will listen to the first episode of Pilar's story. This first episode has an audio and a series of questions to get your opinion"
      )
    end

  then(Message1 when ref_Message_1 == "Understood! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "8692c7af-9e84-468d-bddc-2ef210368db9", x: -528, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Remember that if there is anything in Pilar's story or a question that makes you uncomfortable, you can stop and come back when you feel ready. It is very important to me that you feel good!"
  )

  then(Message_3)
end

```

<!-- { section: "dc4af612-6ec6-4eef-a78f-6f74c11fc443", x: -1752, y: -480} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_1)
end

```

<!-- { section: "62e7f46d-3731-4f3d-a1f7-e8f5a202b8ff", x: -24, y: 24} -->

```stack
card Message_3, "Message_3", code_generator: "TEXT_MESSAGE" do
  text("When the audio ends, press the I heard the audio button")
  then(Message_4)
end

```

<!-- { section: "660dbdc1-7610-49e9-9863-adc423241229", x: 408, y: -24} -->

```stack
card Message_4, "Message_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["I heard the audio!"]) do
      text("Send audio - M1_P1_A1 (NARRATIVE - PART 1)

Content missing here")
    end

  then(Message_5 when ref_Message_4 == "I heard the audio!")
  then(Catch_all_2)
end

```

<!-- { section: "0e95448b-925b-40f3-be60-b9f5a159aeee", x: 480, y: -528} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "3a193799-c074-4069-aa3d-2b0f20e143dc", x: 912, y: 72} -->

```stack
card Message_5, "Message_5", code_generator: "QUESTION" do
  ref_Message_5 =
    ask(
      "What do you think of what I tell you about Pilar? Do you think that if someone looks for you all the time and calls you very often, it's cute or a form of control? 🧐 You can reply using text or voice notes"
    )

  then(Branch_ffa09f)
end

```

<!-- { section: "47a7cc1c-6276-4944-a48c-515df801993a", x: 2448, y: -648} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_7)
end

```

<!-- { section: "a4ff6d1d-1529-4228-8ca2-821b61a508c7", x: 2208, y: 24} -->

```stack
card Message_6, "Message_6", code_generator: "TEXT_MESSAGE" do
  text("Thanks for your response ✨")
  then(Message_7)
end

```

<!-- { section: "23fb2ae2-57b1-4224-aa4c-f2282a279933", x: 2640, y: 24} -->

```stack
card Message_7, "Message_7", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["I looked after her", "I controlled her 🚫", "I'm not sure 😕"]) do
      text(
        "In the story we saw that Camilo had an app to know where Pilar was all the time. What do you think about that?"
      )
    end

  then(Message7_1 when ref_Message_7 == "I looked after her")
  then(Message7_2 when ref_Message_7 == "I controlled her 🚫")
  then(Message7_3 when ref_Message_7 == "I'm not sure 😕")
  then(Catch_all_3)
end

```

<!-- { section: "88e88d06-9888-4b70-9b98-5c9681c4512f", x: 4104, y: 96} -->

```stack
card Message_8, "Message_8", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["Next question"]) do
      text(
        "It's okay to take care of yourself, but there is a line between care💖 and control🚫. Signs that someone is exercising control is that we get nervous or feel watched, that our boyfriend gets angry if he doesn't always know our whereabouts, or that we feel like we can't move freely. Your peace of mind is the most important thing"
      )
    end

  then(Message_9 when ref_Message_8 == "Next question")
  then(Catch_all_24)
end

```

<!-- { section: "9130242c-d6e2-43cd-baf9-28bcac0600f4", x: 4632, y: 96} -->

```stack
card Message_9, "Message_9", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Give them 📱", "No! It's private 🗣️", "I don't know 🤷"]) do
      text(
        "What would you say to a friend if her boyfriend, like Camilo, insisted that she give him the passwords and users of all her networks?"
      )
    end

  then(Message9_1 when ref_Message_9 == "Give them 📱")
  then(Message9_2 when ref_Message_9 == "No! It's private 🗣️")
  then(Message9_3 when ref_Message_9 == "I don't know 🤷")
  then(Catch_all_4)
end

```

<!-- { section: "28baad4e-2922-4068-8f79-fb59147133c0", x: 4632, y: -576} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_9)
end

```

<!-- { section: "ff0e41ad-5d53-4369-b794-ceba236eeeb3", x: 5736, y: 216} -->

```stack
card Message_10, "Message_10", code_generator: "TEXT_MESSAGE" do
  text(
    "Your social networks are part of your private life and only you can decide if you feel comfortable sharing them. Something to think about is that whoever has access to your networks has a lot of power over you -- they have all your information and can send messages in your name. 

Do they insist on your friend? Do you feel pressured to give out passwords? If so, it may be a warning sign that that person is controlling, not protective 🚫."
  )

  then(Message_11_)
end

```

<!-- { section: "ba3a4880-0d4a-4fd1-a135-876fd3ee1a11", x: 6240, y: 216} -->

```stack
card Message_11_, "Message_11_", code_generator: "TEXT_MESSAGE" do
  text("Send audio - M1_P2_A1
")
  then(Message_12_)
end

```

<!-- { section: "515d9d2d-ac70-441c-b46c-090031e7be7d", x: 6072, y: -552} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "eb09cb06-03b7-494a-b49e-c1654fe3fdfd", x: 6792, y: 168} -->

```stack
card Message_12_, "Message_12_", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_ =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_13 when ref_Message_12_ == "I heard the audio")
  then(Catch_all_6)
end

```

<!-- { section: "654093aa-5467-40be-8965-024cb1452885", x: 6744, y: -600} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12_)
end

```

<!-- { section: "56710db0-e931-4cb3-bea7-205eb6a243a4", x: 7440, y: 216} -->

```stack
card Message_13, "Message_13", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["Tell him, ", "Bad sign 🚨", "I'm not sure🤔"]) do
      text(
        "What would your friends think if the guy you're dating is the coolest guy at school and, at the same time, he asks you to say where you are all the time because if you don't, he'll get angry?"
      )
    end

  then(Message13_1 when ref_Message_13 == "Tell him, ")
  then(Message13_2 when ref_Message_13 == "Bad sign 🚨")
  then(Message13_3 when ref_Message_13 == "I'm not sure🤔")
  then(Catch_all_7)
end

```

<!-- { section: "60d7ec08-5492-4e4f-ae51-1e1a34f2403c", x: 7344, y: -600} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13)
end

```

<!-- { section: "dcf714e5-bcba-4da5-853e-ae78e5b78b16", x: 8760, y: 72} -->

```stack
card Message_14_1, "Message_14_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_1 =
    buttons(["Follow the podcast "]) do
      text(
        "Just because he's the daddy at school doesn't justify that you should be with him. If someone asks you to tell them where you are all the time and gets angry if you don't, it could be a sign of control. Think about how it makes you feel and if it's really what you want in a relationship. If you hear something like this, remind your friends that a partner should trust you, not watch you."
      )
    end

  then(Message_15 when ref_Message_14_1 == "Follow the podcast ")
  then(Catch_all_8)
end

```

<!-- { section: "cbd6b9c4-603a-4d2a-a65d-2c042c6ba9ed", x: 8712, y: -792} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_1)
end

```

<!-- { section: "30a3b124-fb7b-4c2e-9c81-60919e7c07f8", x: 8736, y: 672} -->

```stack
card Message_14_2, "Message_14_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_2 =
    buttons(["Follow the podcast "]) do
      text(
        "Exact! If someone asks you to tell them where you are all the time and gets angry if you don't, it could be a sign of control. Think about how it makes you feel and if it's really what you want in a relationship. If you hear something like this, remind your friends that a partner should trust you, not watch you."
      )
    end

  then(Message_15 when ref_Message_14_2 == "Follow the podcast ")
  then(Catch_all_9)
end

```

<!-- { section: "1c0d1871-c59a-4f69-9a1b-8d60014f0c67", x: 8712, y: 1608} -->

```stack
card Message_14_3, "Message_14_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14_3 =
    buttons(["Follow the podcast "]) do
      text(
        "It's normal to hesitate, but if someone asks you to tell them where you are all the time and gets angry if you don't, it could be a sign of control. Think about how it makes you feel and if it's really what you want in a relationship. If you hear something like this, remind your friends that a partner should trust you, not watch you."
      )
    end

  then(Message_15 when ref_Message_14_3 == "Follow the podcast ")
  then(Catch_all_10)
end

```

<!-- { section: "0b6aabaa-ee4f-486c-ba9e-436dffe97a7f", x: 8376, y: 1224} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_2)
end

```

<!-- { section: "fe99366e-34ec-4db3-9885-1a39ef4315ad", x: 8256, y: 2280} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14_3)
end

```

<!-- { section: "8ff8ea27-ddde-490c-9332-54f6728abf93", x: 9984, y: 480} -->

```stack
card Message_15, "Message_15", code_generator: "TEXT_MESSAGE" do
  text(
    "Sometimes we are busy and it is normal. It is healthy to set limits with our partner and let them know that we cannot always be glued to the cell phone 💁‍♀️"
  )

  then(Message_16_1)
end

```

<!-- { section: "c498aaba-c09c-47fe-a71d-77cd8b6dc9fc", x: 10440, y: -720} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16_1)
end

```

<!-- { section: "49e2a5f0-46b4-4d0d-a8a1-7683f3ebd6cc", x: 10800, y: -720} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "7cc678fb-5be8-4ec2-84b2-4c7d3cc278ef", x: 10584, y: 480} -->

```stack
card Message_16_1, "Message_16_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_16_1 =
    buttons(["I want stickers!"]) do
      text(
        "Very good! You have reached the end of the first episode of Pilar's story 🥳 

They are complex topics, so to help you navigate them I leave you some great stickers on this topic that you can use to respond if you experience something similar."
      )
    end

  then(Message_17_sticker_1 when ref_Message_16_1 == "I want stickers!")
  then(Catch_all_11)
end

```

<!-- { section: "1560bed6-634c-4e07-85fc-87e9b745a933", x: 11616, y: -744} -->

```stack
card Catch_all_13, "Catch_all_13", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "e9b90b5c-e788-4ea4-9c3f-a505c059ece0", x: 11136, y: 288} -->

```stack
card Message_17_sticker_1, "Message_17_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("76a59594-06ab-46d0-ad0e-edbb5d05f386-Módulo1__Ubi.jpg")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "6d43fa17-bbaf-4850-9d8a-dcc18d33dedb", x: 14160, y: 120} -->

```stack
card Message_19, "Message_19", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_19 =
    buttons(["Friends 👯‍♀️", "Mom 👩‍👧", "Family 💗"]) do
      text(
        "Now I'm going to leave you a challenge: For tomorrow, talk to someone about this topic and ask them what they think. Who do you want to talk to?"
      )
    end

  then(Message19_1 when ref_Message_19 == "Friends 👯‍♀️")
  then(Message19_2 when ref_Message_19 == "Mom 👩‍👧")
  then(Message19_3 when ref_Message_19 == "Family 💗")
  then(Catch_all_22)
end

```

<!-- { section: "96f963b7-ee88-4f4c-98aa-e353218f5592", x: 14592, y: -504} -->

```stack
card Catch_all_22, "Catch_all_22", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_19)
end

```

<!-- { section: "0f59989d-f07a-4dcf-9aa0-414544877698", x: 16296, y: 384} -->

```stack
card Message_20, "Message_20", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["I want to know!🧐"]) do
      text(
        "Ok friend, that's all for today. Get ready because tomorrow's episode is going to be amazing! Why do you think the police officer called Pilar's mother?"
      )
    end

  then(Message_21 when ref_Message_20 == "I want to know!🧐")
  then(Catch_all_23)
end

```

<!-- { section: "5faefc81-3cd8-4f3f-afcc-7ba6637b321f", x: 15936, y: -1056} -->

```stack
card Catch_all_23, "Catch_all_23", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_20)
end

```

<!-- { section: "96afb544-5528-4104-b50e-7168dd062609", x: 17280, y: 360} -->

```stack
card Message_21, "Message_21", code_generator: "TEXT_MESSAGE" do
  text("See you tomorrow! 👋🌟")
  then(Profile_c9a342)
end

```

<!-- { section: "7c4bc9c3-c0fe-4723-a021-d28de3969e15", x: 4104, y: -600} -->

```stack
card Catch_all_24, "Catch_all_24", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "0a1a4bd8-0aaf-4d74-80fa-a1b7eaedfd77", x: 13056, y: 192} -->

```stack
card Message_18, "Message_18", code_generator: "QUESTION" do
  ref_Message_18 =
    ask("Do you think you learned something new today? Briefly tell us what you are left with:")

  then(Message18)
end

```

<!-- { section: "0f79fa9d-d1a4-4118-9d3a-535d3bbbc312", x: 17768, y: 360} -->

```stack
card Profile_c9a342, "Profile_c9a342", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_1")
  then(ModuleCompleted)
end

```

<!-- { section: "638dabf4-4e47-4020-a934-685bd2372480", x: 11472, y: 312} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("7900a550-393c-4a7d-a762-3ecadc85f95f-Módulo1_DateCuenta.jpg")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "f15ab419-7384-4d16-ace9-670b970ad269", x: 11856, y: 288} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("d9d34136-4261-4d65-8193-a498c5568115-Módulo1_DejaDeLlamarme.jpg")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "402f3dfe-1fa5-41a3-be26-91da8d42e0c6", x: 12264, y: 288} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("7d382bd1-c1ea-4742-b8aa-26f16243bb64-Módulo1_Ewww.jpg")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "ed17344f-65f8-426b-84fa-2e91e9606d5a", x: 12648, y: 288} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("e6621d3b-fe8b-4bad-8de3-3c257b14fdbb-Módulo1_Límites.jpg")
  text("")
  then(Message_18)
end

```

<!-- { section: "acefe282-3621-4c78-8e36-0588152f2e50", x: 1400, y: 72} -->

```stack
card Branch_ffa09f, "Branch_ffa09f", code_generator: "CONDITIONALS" do
  then(Message5 when @event.message.type == "audio")
  then(Message5 when @event.message.type == "text")
  then(Text_245dd4)
end

```

<!-- { section: "a85491ab-a676-4c3b-b4a1-1de1d42e0a1e", x: 1224, y: 480} -->

```stack
card Text_245dd4, "Text_245dd4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using text or voice note.")
  then(Message_5)
end

```

<!-- { section: "e383c640-32f3-41c1-b62f-9e817772b715", x: 1680, y: 504} -->

Save users response here

I have places a code block below for you to be able to add in the code to save the response if the Save insight is not the right thing to use

<!-- { section: "c174ce61-5792-488e-9fa5-1f04ba361ddb", x: 360, y: 432} -->

Potentially switch message 3 and 4

<!-- { section: "a9e003bb-ee47-4fff-ba75-90b75da1837c", x: 18048, y: 768} -->

schedule follow up - Quiz post module 1 narrative flow eng

<!-- { section: "b9c03796-e937-4b2c-858e-7398e50e3635", x: 14832, y: 1272} -->

need a variable /insight name

<!-- { section: "31d96bc9-d1af-4939-b260-1ce4ccd27f9d", x: 312, y: 312} -->

We cannot have audio as button messages, will need extra copy here

<!-- { section: "db3ca5dd-6264-43d8-9b1f-ac7b0aab5c32", x: 5040, y: 888} -->

save insights

added a code block below incase these are incorrect

<!-- { section: "c4a5203f-a151-4b25-b17b-cae9b5654b7d", x: 13512, y: 672} -->

Save user response here

Added a code block just incase this is wrong

<!-- { section: "6dd26e5d-2894-4524-a25f-c9ccf12ea3ae", x: 11136, y: 696} -->

**@Tam**

These are jpgs

<!-- { section: "fa51b971-fa32-4a52-8c6b-511c024a1211", x: 1800, y: 48} -->

```stack
card Message5 do
  log("Saving message 5 response")
  write_result("module1_boundaries", "@ref_message_5")
  then(Message_6)
end

```

<!-- { section: "3e35e87b-2ec7-41c6-b052-ae49c6ff5708", x: 13512, y: 168} -->

```stack
card Message18 do
  write_result("module1_learnings", "@ref_message_18")
  then(Message_19)
end

```

<!-- { section: "c5309665-9699-4276-9ed1-5b206bb6357c", x: 18216, y: 288} -->

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

<!-- { section: "d7974c66-88ea-4d29-ad23-3fe12676d8cf", x: -1080, y: 0} -->

```stack
card Message1 do
  write_result("module1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "b74c70e4-b0a8-498b-bf8d-ac9836750c4f", x: 3168, y: -264} -->

```stack
card Message7_1 do
  write_result("module1_beliefs", "a")
  then(Message_8)
end

```

<!-- { section: "2b7fcac3-8c8f-4248-9885-eee5b8e41ef2", x: 3168, y: 72} -->

```stack
card Message7_2 do
  write_result("module1_beliefs", "b")
  then(Message_8)
end

```

<!-- { section: "122a3c62-2a53-457e-94b5-cd88ed40fa03", x: 3168, y: 384} -->

```stack
card Message7_3 do
  write_result("module1_beliefs", "c")
  then(Message_8)
end

```

<!-- { section: "0190917d-aec1-4de6-9a11-2d23cdfcda05", x: 5112, y: -144} -->

```stack
card Message9_1 do
  write_result("module1_attitudes", "a")
  then(Message_10)
end

```

<!-- { section: "2e52a41b-1335-4e66-97a6-1570bfac513c", x: 5112, y: 168} -->

```stack
card Message9_2 do
  write_result("module1_attitudes", "b")
  then(Message_10)
end

```

<!-- { section: "121b408e-099b-420b-a319-717455aab102", x: 5112, y: 480} -->

```stack
card Message9_3 do
  write_result("module1_attitudes", "c")
  then(Message_10)
end

```

<!-- { section: "f6cbbc25-7cef-4da1-a312-e98904c19802", x: 7968, y: -96} -->

```stack
card Message13_1 do
  write_result("module1_social_norms", "a")
  then(Message_14_1)
end

```

<!-- { section: "aa4f23dc-f3e0-4d4e-b7b6-7ff2d78b0d47", x: 7968, y: 288} -->

```stack
card Message13_2 do
  write_result("module1_social_norms", "b")
  then(Message_14_2)
end

```

<!-- { section: "5f698f7d-07e0-428c-a9e9-c437e996703d", x: 7968, y: 624} -->

```stack
card Message13_3 do
  write_result("module1_social_norms", "c")
  then(Message_14_3)
end

```

<!-- { section: "c980a29a-d554-4883-821a-0fc53b8ec00f", x: 15120, y: 0} -->

```stack
card Message19_1 do
  write_result("module1_behavioral_activation", "a")
  then(Message_20)
end

```

<!-- { section: "8ad04aaf-6bb4-4987-9703-0f8c756fcfc3", x: 15096, y: 408} -->

```stack
card Message19_2 do
  write_result("module1_behavioral_activation", "b")
  then(Message_20)
end

```

<!-- { section: "a396415c-dca1-42a4-97ac-62a6b612a912", x: 15072, y: 744} -->

```stack
card Message19_3 do
  write_result("module1_behavioral_activation", "c")
  then(Message_20)
end

```

<!-- { section: "b57e1e1a-5905-4821-8742-d7e4d8aa264e", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
<!-- { section: "6978e976-69e4-4e75-92cd-0f30046e222f", x: -3240, y: -72} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "nm6")

```

<!-- { section: "65964135-2766-4c6a-acdb-5527ec39d211", x: -2064, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 Now, welcome to the sixth and final episode of Pilar's story. What a turn the story took and how quickly time has passed!"
  )

  then(Message1)
end

```

<!-- { section: "25c059a1-ca07-455b-b0ac-12327eeef82d", x: -2592, y: 48} -->

```stack
card Branch_4c1d16, "Branch_4c1d16", code_generator: "CONDITIONALS" do
  then(
    Message_1
    when contact.arm == "NARRATIVE" and contact.onboarding_complete == true and
           contact.contact_module == "MODULE_5" and contact.quiz_post_module5_complete_ == true
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "0017fb97-29a3-4892-b59b-cc45a2f5cc8e", x: -792, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["I didn't have time ", "Super! 👍"]) do
      text(
        "Yesterday's challenge was to find a famous couple or friend who was a good example of the topics we talked about. How did it go?"
      )
    end

  then(Message2_1 when ref_Message_2 == "I didn't have time ")
  then(Message2_2 when ref_Message_2 == "Super! 👍")
  then(Catch_all_1)
end

```

<!-- { section: "6aeadd00-1875-45f7-a018-36ac0959aae9", x: -744, y: -960} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "9c0317eb-9c77-41de-90da-d6228713b4c6", x: 672, y: -48} -->

```stack
card Message_3_1, "Message_3_1", code_generator: "TEXT_MESSAGE" do
  text("Don't worry, today you can catch up!")
  then(Message_4)
end

```

<!-- { section: "d5f6d774-c244-452d-a3df-6eb84918b0fc", x: 600, y: 528} -->

```stack
card Message_3_2, "Message_3_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Incredible! There are examples of good and bad communication everywhere. Now, you know how to identify and set your limits, say yes/no or argue, but in a healthy way!"
  )

  then(Message_4)
end

```

<!-- { section: "44f21be7-054e-4a4b-93b9-0e747c55e84c", x: 1152, y: 192} -->

```stack
card Message_4, "Message_4", code_generator: "TEXT_MESSAGE" do
  text(
    "In this episode we will find out what happened, after Mari confessed that she had been the one who had shared Pilar's photo. Come with me to learn what they did and how they created a safety plan!"
  )

  then(Message_5)
end

```

<!-- { section: "3b8412ed-8f34-40b6-a734-fb819dbfaa24", x: 5088, y: 1368} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10_2)
end

```

<!-- { section: "592936fe-82a7-468a-ad7d-5adc48512218", x: 1656, y: 192} -->

```stack
card Message_5, "Message_5", code_generator: "TEXT_MESSAGE" do
  text(
    "As always, if something makes you uncomfortable, you can stop and come back when you feel ready. It is very important to me that you feel good!"
  )

  then(Message_6)
end

```

<!-- { section: "cbfe7eff-d24f-458c-9b1b-2b17d038497a", x: 2136, y: 192} -->

```stack
card Message_6, "Message_6", code_generator: "TEXT_MESSAGE" do
  text("Send audio file NARRATIVE - CHAPTER 6 - Part 1")
  then(Message_7)
end

```

<!-- { section: "cd611862-2e5e-4df7-80fb-99855fc719a9", x: 4680, y: -744} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_9)
end

```

<!-- { section: "32129b75-a715-4807-9693-d8edf4a3e527", x: 2640, y: 192} -->

```stack
card Message_7, "Message_7", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["I heard the audio"]) do
      text(
        "Now, let's listen to the audio. List? When the audio ends, press the I heard the audio button"
      )
    end

  then(Message_8 when ref_Message_7 == "I heard the audio")
  then(Catch_all_4)
end

```

<!-- { section: "66ab3a68-b626-4222-af1c-acf74f453124", x: 2736, y: -552} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_7)
end

```

<!-- { section: "5814b397-35ee-47ff-a890-cb7851115f43", x: 3264, y: 168} -->

```stack
card Message_8, "Message_8", code_generator: "QUESTION" do
  ref_Message_8 =
    ask(
      "Imagine that your friend's boyfriend asked her to send him an intimate photo as proof of love. 

She sent it to him, but now the photo is circulating throughout the room. 

What would you do about it? 🤔"
    )

  then(Message8)
end

```

<!-- { section: "68d918c1-ed33-4998-a973-5fee84bb637b", x: 4488, y: 168} -->

```stack
card Message_9, "Message_9", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Very empowered", "Very intense", "I'm not sure 🤷"]) do
      text(
        "In this episode we hear a simulation about how Pilar could have responded to Camilo when he asked her for the photo. Camilo: \"Do you not trust me? Don't you love me? Besides, how long are you going to keep me waiting?\" Pilar: \"Yes, I love you and I believe you, but I really don't feel comfortable sharing photos like these, and if you really love me, you have to respect my decision.\" 

What did you think of his response? 🤔"
      )
    end

  then(Message9_1 when ref_Message_9 == "Very empowered")
  then(Message9_2 when ref_Message_9 == "Very intense")
  then(Message9_3 when ref_Message_9 == "I'm not sure 🤷")
  then(Catch_all_3)
end

```

<!-- { section: "20a94baa-4e1f-473b-8797-ca376520e498", x: 5568, y: -384} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10_1)
end

```

<!-- { section: "b442982c-09fc-4f44-9d7b-11b39526d298", x: 9624, y: -624} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_13)
end

```

<!-- { section: "a09f2105-7284-4595-8137-689b3d864b36", x: 10536, y: -576} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_14)
end

```

<!-- { section: "275602d1-13ec-4644-9ab9-4cd39b62a75d", x: 6600, y: 192} -->

```stack
card Message_11, "Message_11", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_11 =
    buttons(["Call someone📞", "I don't know🤷‍♀️", "I try to endure 🤔"]) do
      text(
        "Pilar told us that there were parties where she felt uncomfortable because Camilo's friends brought drugs. But since he was the one who took her, he didn't know how to leave those places. What would you do if you were in Pilar's situation? 🤔

If it were your case, what would you do?🤔"
      )
    end

  then(Message11_1 when ref_Message_11 == "Call someone📞")
  then(Message11_2 when ref_Message_11 == "I don't know🤷‍♀️")
  then(Message11_3 when ref_Message_11 == "I try to endure 🤔")
  then(Catch_all_8)
end

```

<!-- { section: "8932dfb8-3604-4855-a11c-d997ef1e07c4", x: 6744, y: -600} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_11)
end

```

<!-- { section: "d3f494a1-d308-4380-baf2-2e964574e769", x: 8160, y: -168} -->

```stack
card Message_12_1, "Message_12_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_1 =
    buttons(["Next audio"]) do
      text(
        "Calling someone you trust to come and pick you up is a great way to have a plan B in an uncomfortable situation. It is always good to have support to get out of those places and make sure you are safe."
      )
    end

  then(Message_13_1 when ref_Message_12_1 == "Next audio")
  then(Catch_all_9)
end

```

<!-- { section: "39fde91c-488f-439e-9843-0ab1229adc56", x: 8136, y: 552} -->

```stack
card Message_12_2, "Message_12_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_2 =
    buttons(["Next audio"]) do
      text(
        "Remember that there is always something you can do. It is best that you have a plan B to act in accordance with your values ​​and well-being. Consider calling someone you trust to pick you up if you need help leaving the party."
      )
    end

  then(Message_13_1 when ref_Message_12_2 == "Next audio")
  then(Catch_all_10)
end

```

<!-- { section: "3f1f4ee9-eabd-4d91-9982-80a84d16813b", x: 8160, y: 1392} -->

```stack
card Message_12_3, "Message_12_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12_3 =
    buttons(["Next audio"]) do
      text(
        "You don't have to endure a situation that makes you feel bad. There is always something you can do. It is best that you have a plan B to act in accordance with your values. Consider calling someone you trust to pick you up if you need help leaving the party."
      )
    end

  then(Message_13_1 when ref_Message_12_3 == "Next audio")
  then(Catch_all_11)
end

```

<!-- { section: "a821aa83-b563-489f-af12-f68eef6ec12e", x: 7872, y: -672} -->

```stack
card Catch_all_9, "Catch_all_9", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12_1)
end

```

<!-- { section: "8ad5580b-9414-447f-bdf6-5edf0cedae39", x: 7896, y: 216} -->

```stack
card Catch_all_10, "Catch_all_10", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12_2)
end

```

<!-- { section: "d4f4f24f-1ecf-4f9c-89e3-41d994eaf315", x: 8064, y: 984} -->

```stack
card Catch_all_11, "Catch_all_11", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12_3)
end

```

<!-- { section: "5c5385ae-058c-453b-b593-01b0f0db431e", x: 12024, y: 744} -->

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

<!-- { section: "88219057-0c32-4755-94f7-0ad64bd8446b", x: 12384, y: 72} -->

```stack
card Catch_all_12, "Catch_all_12", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_16)
end

```

<!-- { section: "b3df70a8-1872-4fbf-b726-a50ab87e2ba3", x: 13440, y: 288} -->

```stack
card Message_17_1, "Message_17_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Money can be tempting, but you also have to consider how it can affect your life in the long term. If you hear something like this, remind your friends that sometimes opportunities that seem \"good\" can have hidden risks. It is important to mention that you have to think carefully about all the consequences before deciding, as this could affect your privacy and well-being in the future."
  )

  then(Message_18)
end

```

<!-- { section: "5c2669d5-4228-4c48-8c36-6ef800ff1d97", x: 13416, y: 864} -->

```stack
card Message_17_2, "Message_17_2", code_generator: "TEXT_MESSAGE" do
  text(
    "It is important to recognize that there are risks and consequences. If you hear something like this, remind your friends that sometimes opportunities that seem \"good\" can have hidden risks. It is important to mention that you have to think carefully about all the consequences before deciding, as this could affect your privacy and well-being in the future."
  )

  then(Message_18)
end

```

<!-- { section: "c0173ff7-fb87-4b03-a8c5-cd7be365515a", x: 13464, y: 1416} -->

```stack
card Message_17_3, "Message_17_3", code_generator: "TEXT_MESSAGE" do
  text(
    "Defending your privacy and well-being is essential. If you hear your friends thinking about it, remind them that sometimes opportunities that seem \"good\" can have hidden risks. It is important to mention that you have to think carefully about all the consequences before deciding, as this could affect your privacy and well-being in the future."
  )

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

<!-- { section: "331ebc6d-33df-4809-b0fe-faa1cee2da14", x: 15240, y: 960} -->

```stack
card Message_19, "Message_19", code_generator: "QUESTION" do
  ref_Message_19 =
    ask(
      "It's time to think about your plan! If you are in an uncomfortable situation, do you know what plan B you can activate to get home safely? Think of everything you need to have to call someone or find your way."
    )

  then(Message19)
end

```

<!-- { section: "7db5f6f9-08ff-41cf-8e18-ab94fdecbc99", x: 16488, y: 888} -->

```stack
card Message_20, "Message_20", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_20 =
    buttons(["Send my stickers!"]) do
      text(
        "\"Very good! Have you heard episode 6 of Pilar's story 🥳 

They are complex topics, so to help you navigate them, I leave you some great stickers on this topic that you can use to respond if you experience something similar.\""
      )
    end

  then(Message_21_sticker_1 when ref_Message_20 == "Send my stickers!")
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

<!-- { section: "f65519eb-2263-4a8e-8242-70f334d009c7", x: 17544, y: 48} -->

```stack
card Catch_all_15, "Catch_all_15", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "520736fc-37ca-4559-8734-7e5f44ad91f1", x: 17088, y: 960} -->

```stack
card Message_21_sticker_1, "Message_21_sticker_1", code_generator: "MEDIA_IMAGE" do
  image("1e1cf144-0611-4b68-b129-051d24f6dc67-Módulo6_Abrilosojos.png")
  text("")
  then(Sticker_2)
end

```

<!-- { section: "1765c980-83a6-4155-bd4c-148e2077a9b2", x: 18960, y: 72} -->

```stack
card Catch_all_16, "Catch_all_16", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "cbae3b8a-84b6-4248-90a5-90d77e77cfc0", x: 19296, y: 888} -->

```stack
card Mesage_22, "Mesage_22", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Mesage_22 =
    buttons(["Meditation🧘‍♀️", "Talk to someone👥", "Write or breathe"]) do
      text(
        "Today is our last day 😢. But I can't leave without leaving you a challenge that I want you to do every day: Take good care of yourself! I want you to think about what you will do when you don't feel well. What do you want to focus on?"
      )
    end

  then(Message22_1 when ref_Mesage_22 == "Meditation🧘‍♀️")
  then(Message22_2 when ref_Mesage_22 == "Talk to someone👥")
  then(Message22_3 when ref_Mesage_22 == "Write or breathe")
  then(Catch_all_17)
end

```

<!-- { section: "4ccf14c8-d546-4a16-8ef3-6d22a7b90278", x: 19848, y: 72} -->

```stack
card Catch_all_17, "Catch_all_17", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Mesage_22)
end

```

<!-- { section: "76b9da8c-773f-47ad-8814-761c64cb0252", x: 20976, y: 864} -->

```stack
card Message_23, "Message_23", code_generator: "TEXT_MESSAGE" do
  text(
    "I think it's great, think about when and how you can do this activity as part of your daily routine so you don't forget."
  )

  then(Message_24)
end

```

<!-- { section: "0294e76d-c62f-4699-8fd2-7a4f37cde880", x: 21504, y: 864} -->

```stack
card Message_24, "Message_24", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_24 =
    buttons(["Bye LiA! 🌸"]) do
      text(
        "Ok friend, I really liked meeting you and interacting with you all these days! I hope everything you learned has been very useful to you and that you don't forget how powerful you are💪"
      )
    end

  then(Profile_cbf172 when ref_Message_24 == "Bye LiA! 🌸")
  then(Catch_all_18)
end

```

<!-- { section: "3d64f3d5-f112-4aa5-ac54-7a0066309e86", x: 23256, y: 864} -->

```stack
card Message_25, "Message_25", code_generator: "TEXT_MESSAGE" do
  text("Bye friend! 👋🌟")
end

```

<!-- { section: "c6cd185d-446d-411e-bb68-3ec39225314a", x: 21576, y: 144} -->

```stack
card Catch_all_18, "Catch_all_18", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_24)
end

```

<!-- { section: "8ab8bdf3-6c00-4056-a46a-1dd1d8d29a6e", x: 21992, y: 924} -->

```stack
card Profile_cbf172, "Profile_cbf172", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "MODULE_6")
  then(QuizComplete)
end

```

<!-- { section: "be6ee9e6-e805-406a-9a18-7bb03f7e3c6d", x: 5664, y: 120} -->

```stack
card Message_10_1, "Message_10_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_1 =
    buttons(["Next question"]) do
      text(
        "Setting limits and clearly expressing how you feel is never intensity, it is our opportunity to respect ourselves and it is part of a healthy relationship. We never have to feel pressure to do something we don't want to, even if we have done it before. Love is cool when both people are ready!"
      )
    end

  then(Message_11 when ref_Message_10_1 == "Next question")
  then(Catch_all_5)
end

```

<!-- { section: "ee00d079-14ef-459c-824c-4982c07a6f59", x: 5784, y: 816} -->

```stack
card Message_10_2, "Message_10_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10_2 =
    buttons(["Next question"]) do
      text(
        "If it wouldn't be easy for you either, try practicing as you would to improve your confidence. Your needs are important and should be heard and respected. Talking to your friends about this can be a good step to support each other."
      )
    end

  then(Message_11 when ref_Message_10_2 == "Next question")
  then(Catch_all_2)
end

```

<!-- { section: "dce38301-9423-4f06-8029-723777f7e39b", x: 8952, y: 720} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text("Send audio file NARRATIVE - CHAPTER 6 - Part 2")
  then(Message_13)
end

```

<!-- { section: "9429dc35-0402-4719-9375-9e584e13d5d7", x: 9528, y: 720} -->

```stack
card Message_13, "Message_13", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_13 =
    buttons(["I heard the audio"]) do
      text("When the audio ends, press the I heard the audio button")
    end

  then(Message_14 when ref_Message_13 == "I heard the audio")
  then(Catch_all_6)
end

```

<!-- { section: "818352c1-a996-4ea1-82db-42b39c69cdb7", x: 10152, y: 696} -->

```stack
card Message_14, "Message_14", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_14 =
    buttons(["No idea🤷‍♀️", "We have it clear", "Not considered yet"]) do
      text(
        "In your group of friends, do you know what to do if a situation like Pilar's were to happen to one of you?"
      )
    end

  then(Message14_1 when ref_Message_14 == "No idea🤷‍♀️")
  then(Message14_2 when ref_Message_14 == "We have it clear")
  then(Message14_3 when ref_Message_14 == "Not considered yet")
  then(Catch_all_7)
end

```

<!-- { section: "33af2ff3-a08c-4cdd-98b3-d09963e93e67", x: 11352, y: 768} -->

```stack
card Message_15, "Message_15", code_generator: "TEXT_MESSAGE" do
  text(
    "It is essential that your group of friends talk about situations like Pilar's. Being clear about what to do can make all the difference in difficult times. 

Tools offered by social networks, such as deleting messages on Telegram, WhatsApp or reporting the image on Facebook are some ideas. It is always good to have a plan and support each other, so everyone will be more prepared to face any situation that arises. 

So that we remember, let's repeat the steps that Pilar mentioned to us: 
1) First, think about how you feel and seek support 🔍 
2) Then save evidence and talk to an adult or expert for help 📄 
3) Check if the social network where the photo circulates has a channel to support you in downloading the photo 📸 
4) Adjust the privacy of your profiles on social networks 👩🏻‍💻 
5) You can report the incident if you want, since sharing your photo is illegal 🚫 
If we go through situations like these, it is important to know that we are not alone and that there are ways to solve this!"
  )

  then(Message_16)
end

```

<!-- { section: "f5a29d69-efa8-4bb1-bfc6-e08cda6a938d", x: 17472, y: 960} -->

```stack
card Sticker_2, "Sticker_2", code_generator: "MEDIA_IMAGE" do
  image("c2a57560-d969-4a1c-ad0b-e0c7110e3004-Módulo6_Auxilio.png")
  text("")
  then(Sticker_3)
end

```

<!-- { section: "e367df12-006c-4aef-8a5f-111972607f6a", x: 17952, y: 960} -->

```stack
card Sticker_3, "Sticker_3", code_generator: "MEDIA_IMAGE" do
  image("f60f68b6-dc96-4703-a1ba-c99632c6560e-Módulo6_Fortalesa.png")
  text("")
  then(Sticker_4)
end

```

<!-- { section: "5615a4fc-87c0-40e9-a61c-c277c364545a", x: 18408, y: 960} -->

```stack
card Sticker_4, "Sticker_4", code_generator: "MEDIA_IMAGE" do
  image("ca14a303-be30-4741-bd5c-6c4836387e1e-Módulo6_Noestassola.png")
  text("")
  then(Sticker_5)
end

```

<!-- { section: "34b3899a-a4cb-4e12-85f8-604206bf368a", x: 18888, y: 960} -->

```stack
card Sticker_5, "Sticker_5", code_generator: "MEDIA_IMAGE" do
  image("5a6dd323-24a2-427b-8a78-33db08dd84e6-Módulo6_Selfcare.png")
  text("")
  then(Mesage_22)
end

```

<!-- { section: "be50064b-656c-4eb9-8ea0-6c5161cc6a40", x: 12216, y: 1248} -->

**@Buhle**

Please save insights here

<!-- { section: "3d6da37c-b0cf-4164-8919-bdfa61b4905d", x: -2616, y: 528} -->

**@Buhle**

Please add in the other thingies here ^

<!-- { section: "3ade50e9-495b-47c5-873c-34e167c5daff", x: -1464, y: 288} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

DS note: Flow result: module6_started (yes)

<!-- { section: "0fe93923-c61b-4bce-8998-cd0e0f6e70af", x: -744, y: 408} -->

**@Buhle**

Please save the insights here

<!-- { section: "d9e25899-030f-432b-b5b9-69f3581d3867", x: 3744, y: 576} -->

**@Buhle**

Please save this for DS, I added a code block just in case that would be easier

**DS note:** Flow result: module6_beliefs {user input}

<!-- { section: "421404a1-21ba-4fdf-b649-28b682b0df7b", x: 6816, y: 744} -->

**@Buhle**

Please save insights here

<!-- { section: "0e7f4eb6-114e-4779-a2d9-6b80b4d50a07", x: 14208, y: 1392} -->

**@Buhle**

Please save insights here

<!-- { section: "8ddbe36a-c534-4965-b60d-33a431af3bd0", x: 15624, y: 1368} -->

**@Buhle**

Please save the user response here, its a DS thing so I added a code block below for you incase that is what you need.

**DS note:** Flow result: module6_action_planning {user input}

<!-- { section: "7e988dd1-5569-471d-bc2e-694e9e1347e9", x: 17256, y: 1416} -->

**@Tam**

**Stickers are pngs**

<!-- { section: "89033a98-ed7c-4746-af57-8fc29f75f7e5", x: 19344, y: 1392} -->

**@buhle**

Please save insights here

<!-- { section: "9e562d58-fe57-401b-b824-61a3c0842320", x: 21984, y: 1176} -->

update contact field, contact module = module 6 ✅

<!-- { section: "6591d732-0980-4bf2-a088-1d2a4cbfc23b", x: 22752, y: 1128} -->

**@Buhle**

DS note: Flow result: module6_completed (yes)

I added in a code block for you below, please dlt the one you arent using

<!-- { section: "3eddae03-9549-4f67-875c-49c99029d1a3", x: 10296, y: 1200} -->

**@Buhle**

Please save insights here

<!-- { section: "ddb89de4-b59d-49d9-9062-c72e93051092", x: -1488, y: -48} -->

```stack
card Message1 do
  write_result("module6_started", "yes")
  then(Message_2)
end

```

<!-- { section: "bc527275-deb6-4f99-885a-61a48d8b2377", x: 3768, y: 144} -->

```stack
card Message8 do
  write_result("module6_beliefs2", "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "40b238e3-9234-49fe-9ff9-9d8836196429", x: 15816, y: 936} -->

```stack
card Message19 do
  write_result("module6_action_planning", "@ref_message_19")
  then(Message_20)
end

```

<!-- { section: "56d5ad72-f0d4-49ff-9d07-68a3967f93ac", x: 14640, y: 1272} -->

```stack
card Message18_3 do
  write_result("module6_behavioral_activation", "c")
  then(Message_19)
end

```

<!-- { section: "ad1372dc-949f-44f7-84e4-f97f9d72fc34", x: 20016, y: 1512} -->

```stack
card Message22_3 do
  write_result("module6_behavioral_activation2", "c")
  then(Message_23)
end

```

<!-- { section: "df32e34b-fa7e-4e88-9ac8-9888fa68f009", x: -120, y: -192} -->

```stack
card Message2_1 do
  write_result("module6_challenge_followup", "a")
  then(Message_3_1)
end

```

<!-- { section: "c26af495-6c93-4f20-8c4e-604bcf4c88a9", x: -96, y: 240} -->

```stack
card Message2_2 do
  write_result("module6_challenge_followup", "b")
  then(Message_3_2)
end

```

<!-- { section: "cf919b35-7a91-4aa0-a664-c33aef122f7a", x: 5112, y: -120} -->

```stack
card Message9_1 do
  write_result("module2_beliefs", "a")
  then(Message_10_1)
end

```

<!-- { section: "2f70282b-ae6b-49f1-9edb-84c6cc116698", x: 5136, y: 288} -->

```stack
card Message9_2 do
  write_result("module6_beliefs2", "b")
  then(Message_10_1)
end

```

<!-- { section: "f469af6b-0993-4c8b-a0dc-0bc8e44e515e", x: 5136, y: 648} -->

```stack
card Message9_3 do
  write_result("module6_beliefs2", "c")
  then(Message_10_2)
end

```

<!-- { section: "670abce7-3196-4fc5-b2a8-3cb6b84b183f", x: 7248, y: -192} -->

```stack
card Message11_1 do
  write_result("module2_beliefs", "a")
  then(Message_12_1)
end

```

<!-- { section: "37090bf0-7866-481d-8beb-e1428e4d787e", x: 7320, y: 168} -->

```stack
card Message11_2 do
  write_result("module2_beliefs", "b")
  then(Message_12_2)
end

```

<!-- { section: "07f894b2-c903-4dc1-a88c-d20985381c42", x: 7344, y: 600} -->

```stack
card Message11_3 do
  write_result("module6_attitudes", "c")
  then(Message_12_3)
end

```

<!-- { section: "f61ce0af-674c-465d-8f5c-a20c64e04ebd", x: 10752, y: 384} -->

```stack
card Message14_1 do
  write_result("module6_knowledge", "a")
  then(Message_15)
end

```

<!-- { section: "525d7385-a2f1-4291-ba0f-1bfd991d711e", x: 10728, y: 720} -->

```stack
card Message14_2 do
  write_result("module6_knowledge", "b")
  then(Message_15)
end

```

<!-- { section: "ec2aadee-6bc1-425b-a08b-c6c94067cdb1", x: 10728, y: 1056} -->

```stack
card Message14_3 do
  write_result("module6_knowledge", "c")
  then(Message_15)
end

```

<!-- { section: "51aa90f8-79f9-415e-9a65-f2122991e818", x: 12816, y: 480} -->

```stack
card Message16_1 do
  write_result("module6_social_norms", "a")
  then(Message_17_1)
end

```

<!-- { section: "fe56c243-cb8c-45f3-afa9-7c8b8e3e8c99", x: 12816, y: 816} -->

```stack
card Message16_2 do
  write_result("module6_social_norms", "b")
  then(Message_17_2)
end

```

<!-- { section: "a83e1137-e8a1-420d-ad75-b798dd6aefec", x: 12792, y: 1200} -->

```stack
card Message16_3 do
  write_result("module6_social_norms", "c")
  then(Message_17_3)
end

```

<!-- { section: "e1dbbad9-95cd-403d-841c-c2cbe7e06446", x: 14592, y: 528} -->

```stack
card Message18_1 do
  write_result("module6_behavioral_activation", "a")
  then(Message_19)
end

```

<!-- { section: "e0f33452-4815-438c-b6d4-21f21135aa49", x: 14616, y: 936} -->

```stack
card Message18_2 do
  write_result("module6_behavioral_activation", "b")
  then(Message_19)
end

```

<!-- { section: "44de88ce-caf5-4adb-aea7-4f0b51aca134", x: 22608, y: 816} -->

```stack
card QuizComplete do
  write_result("module6_completed", "yes")
  then(Message_25)
end

```

<!-- { section: "9b42478d-2da6-42d1-8fbe-bd70dfcdd7e7", x: 20040, y: 720} -->

```stack
card Message22_1 do
  write_result("module6_behavioral_activation2", "a")
  then(Message_23)
end

```

<!-- { section: "3c00ecfc-7e7e-4cb0-a303-a52decbaeda6", x: 20040, y: 1128} -->

```stack
card Message22_2 do
  write_result("module6_behavioral_activation2", "b")
  then(Message_23)
end

```

<!-- { section: "7297b375-cdbd-46ae-941b-d61bc0f8aded", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
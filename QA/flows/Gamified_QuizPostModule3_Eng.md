<!-- { section: "2b342a75-5896-4c3f-84d3-3e1a302eca47", x: -1800, y: -48} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.quiz_post_module3_complete == false and contact.contact_module == "MODULE_3" and
       contact.arm == "GAMIFIED" and contact.onboarding_complete == true

```

<!-- { section: "cf6e6fd8-1d41-4f89-a3f9-4adb23f01b51", x: -168, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_1 =
    buttons(["Tell me more!"]) do
      text("Hello! 👋 Let's start the day with a mini test: what kind of friend are you?")
    end

  then(Message1 when ref_Message_1 == "Tell me more!")
  then(Catch_all_1)
end

```

<!-- { section: "636cd8dc-b6d4-4d3d-ad57-4fcdb2c32c85", x: 456, y: 720} -->

```stack
card Branch_18a38a, "Branch_18a38a", code_generator: "CONDITIONALS" do
  then(
    RESERVED_DEFAULT_CARD
    when contact.contact_module == "MODULE_3" and contact.arm == "GAMIFIED" and
           contact.onboarding_complete == true
  )

  then(RESERVED_DEFAULT_CARD)
end

```

<!-- { section: "cba701b0-fbc0-4610-aad6-d7f000cc1c3f", x: 1392, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["Brilliant!"]) do
      text(
        "We want to be best friends but sometimes our friends' problems are too much 🔥 and we don't know how to help 🧯, or they get on our nerves 🙄. Let's see what kind of friend you are!"
      )
    end

  then(Message_3 when ref_Message_2 == "Brilliant!")
  then(Catch_all_2)
end

```

<!-- { section: "50c88763-6051-46ea-8cf0-daa9bad3f776", x: -168, y: -600} -->

```stack
card Catch_all_1, "Catch_all_1", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_1)
end

```

<!-- { section: "0b2b8f89-82c9-4fde-a716-f133fff839f9", x: 1392, y: -672} -->

```stack
card Catch_all_2, "Catch_all_2", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_2)
end

```

<!-- { section: "084aab97-fd2d-454f-b12a-8c80aa934919", x: 2208, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
end

```

<!-- { section: "7b4d730e-338b-476c-aa4f-8a5d681fc043", x: 3024, y: -72} -->

```stack
card Message_3, "Message_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["A", "B", "C"]) do
      text(
        "A friend tells you that she had a big fight with her boyfriend😡 She is crying a lot and tells you every last detail that, honestly, leaves you speechless! 

How do you react? 
A. You are in shock and say \"How so? I don't believe you!\"😮 
B. You hug her while you think of something to say 🤗😶 
C. You tell him \"What happened is not your fault\" 😔"
      )
    end

  then(Message3_1 when ref_Message_3 == "A")
  then(Message3_2 when ref_Message_3 == "B")
  then(Message3_3 when ref_Message_3 == "C")
  then(Catch_all_4)
end

```

<!-- { section: "73f297ce-f97b-403d-a9e1-2cd8e191e119", x: 2976, y: -672} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_3)
end

```

<!-- { section: "d61839b7-418e-4bdb-bb97-f2f7def5157a", x: 4584, y: -432} -->

```stack
card Message_4_1, "Message_4_1", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Although it is a common expression, \"I don't believe you\" can make your friend feel questioned. The best thing is to let her know that you are there for her and that you believe her, no matter what happens."
  )

  then(Message_5)
end

```

<!-- { section: "bae76967-bc24-4800-89a1-202f7d0c2d06", x: 4560, y: 144} -->

```stack
card Message_4_2, "Message_4_2", code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Good! If she feels comfortable, holding her hand or hugging her can make her feel like she is not alone. You can also later tell him that it is not his fault what they did to him."
  )

  then(Message_5)
end

```

<!-- { section: "055fe967-d787-4579-945f-36c759aa8684", x: 4560, y: 720} -->

```stack
card Message_4_3, "Message_4_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Correct! It is important for her to know that she is not responsible for what others do to her. If she feels comfortable you can also hug her."
  )

  then(Message_5)
end

```

<!-- { section: "1784167a-3b27-4155-ab4e-cd1526d77275", x: 5472, y: 120} -->

```stack
card Message_5, "Message_5", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["A", "B", "C"]) do
      text(
        "You go on Telegram and see that they pass the package of a girl from your classroom. They are not very close, but they sit together from time to time and they are good people. 

How do you react? 
A. You call your best friend to comment 📳 
B. You comment \"that's what happens to her because she's stupid and easygoing\" 🙄 
C. You sit next to her the next day to accompany her, so you don't say anything 🪑"
      )
    end

  then(Message5_1 when ref_Message_5 == "A")
  then(Message5_2 when ref_Message_5 == "B")
  then(Message5_3 when ref_Message_5 == "C")
  then(Catch_all_5)
end

```

<!-- { section: "0441c207-9fbf-42fa-ba68-12026e691523", x: 6840, y: -384} -->

```stack
card Message_6_1, "Message_6_1", code_generator: "TEXT_MESSAGE" do
  text(
    "🤔- I understand the temptation to comment on the latest news, but you have to be careful not to spread gossip. Imagine how that girl is feeling, and gossip is only going to make her worse 😦 We don't know the details of the situation, maybe she confided in someone she loved or it could even be a false image!"
  )

  then(Message_7)
end

```

<!-- { section: "1e132075-acb2-41cc-b60a-a051561425a5", x: 6840, y: 120} -->

```stack
card Message_6_2, "Message_6_2", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ You have to be careful not to fall into gossip. Imagine how that girl is feeling, and gossip is only going to complicate things😦. We don't know the details of the situation, maybe he trusted someone he loved or it could even be a fake image!"
  )

  then(Message_7)
end

```

<!-- { section: "f8e2aeff-15ec-4ed9-a8da-94a21f5a69fe", x: 6840, y: 528} -->

```stack
card Message_6_3, "Message_6_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ - Very good! It's good for her to know that her friends are not going to abandon her or judge her. We don't know the details of the situation, maybe he trusted someone he wanted or it could even be a fake image!"
  )

  then(Message_7)
end

```

<!-- { section: "262408fd-b9e8-4760-84cc-8bf50311b469", x: 5424, y: -1080} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_5)
end

```

<!-- { section: "0bd6b88f-d225-4982-85e8-b0127b1788d8", x: 7704, y: 144} -->

```stack
card Message_7, "Message_7", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["A", "B", "C"]) do
      text(
        "A friend calls you to tell you that she screwed up🫣. She was having a sexy video call with her boyfriend and he recorded it without her realizing it. Now she's worried what he can do with it! 

What do you say to him? 
A. Let's get help to delete it 🔍 
B. I always knew I was weird! 😫 
C. Who tells you to do those things 🫠"
      )
    end

  then(Message7_1 when ref_Message_7 == "A")
  then(Message7_2 when ref_Message_7 == "B")
  then(Message7_3 when ref_Message_7 == "C")
  then(Catch_all_6)
end

```

<!-- { section: "6612728f-639c-4277-882b-a0e50ee8eb67", x: 7320, y: -1128} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_7)
end

```

<!-- { section: "e767928f-9a9b-43f8-b963-4f2337652888", x: 9096, y: -360} -->

```stack
card Message_8_1, "Message_8_1", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Correct! He broke her trust by recording her without permission. Instead of judging her, it is better to help her find a solution."
  )

  then(Message_9)
end

```

<!-- { section: "f87db9a0-001a-451f-9d89-a0b7be344f4e", x: 9096, y: 144} -->

```stack
card Message_8_2, "Message_8_2", code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Even if you don't like her boyfriend, it's better not to judge her, especially when she is feeling bad. There are better ways and times to communicate your concerns about your partner. Better, help her find a solution."
  )

  then(Message_9)
end

```

<!-- { section: "c6eb1bdc-486a-43a8-b538-69461a061aa2", x: 9096, y: 600} -->

```stack
card Message_8_3, "Message_8_3", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ We all have different tastes and, even when we make mistakes, it's not worth judging. He broke her trust by recording her without permission, better to help her find a solution."
  )

  then(Message_9)
end

```

<!-- { section: "e424813f-5bd3-4da8-994a-4d9435dbf7cf", x: 10392, y: -120} -->

```stack
card Message_9, "Message_9", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Super good! 👍", "I can improve 🙃"]) do
      text("How did you do on the mini test? 👀")
    end

  then(Message9_1 when ref_Message_9 == "Super good! 👍")
  then(Message9_2 when ref_Message_9 == "I can improve 🙃")
  then(Catch_all_8)
end

```

<!-- { section: "f1253b20-2c95-468f-a185-77e84723a304", x: 10368, y: -1056} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_9)
end

```

<!-- { section: "8583814f-6a96-4d15-af59-83a1e94deffc", x: 11664, y: -264} -->

```stack
card Message_10_1, "Message_10_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Incredible, you are a super friend. Keep showing the world how we are stronger together 💪🏼"
  )

  then(Message_11)
end

```

<!-- { section: "cd756325-d6bb-417a-8e48-1d606be800ee", x: 11688, y: 264} -->

```stack
card Message_10_2, "Message_10_2", code_generator: "TEXT_MESSAGE" do
  text("There's still a little work to do to become your friends' \"shoulder to cry on\" 🙌")
  then(Message_11)
end

```

<!-- { section: "022e6bf5-c43e-451c-adfd-19a50d35b3ea", x: 12408, y: -96} -->

```stack
card Message_11, "Message_11", code_generator: "TEXT_MESSAGE" do
  text(
    "Remember. When you see someone in trouble, the important thing is to comply with the three NO's: 
🚫 Don't judge ☝🏼 
🚫 Do not question ⁉️ 
🚫 Don't gossip 🙊
"
  )

  then(QuizCompleted)
end

```

<!-- { section: "813adf80-eefe-42cc-9aba-585166959996", x: 13848, y: -48} -->

```stack
card RunStack_b8be21, "RunStack_b8be21", code_generator: "RUN_STACK" do
  run_stack("6c86c38c-3c45-4ac4-b5a6-292ec6fbd6d4")
end

```

<!-- { section: "4d11a993-ed03-408d-91f5-77dc65da13cf", x: 3168, y: 744} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "10ddfc30-726b-4ec1-9880-b0c0f3f97b56", x: 3936, y: -144} -->

opt a = 0

<!-- { section: "f71771bc-5dff-4dd2-99ff-8ea609717ec6", x: 3936, y: 456} -->

opt b = 1

<!-- { section: "72c63982-e262-4342-926c-54f1ee6ac9b5", x: 3960, y: 960} -->

opt c = 2

<!-- { section: "282fcbe1-7c40-4fd2-99a4-c89978ab91a5", x: 5664, y: 744} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "e0d132f0-faa8-4578-a79d-a77253817d5e", x: 6264, y: -120} -->

opt a = 1

<!-- { section: "bf25cf1e-9525-46d1-8a4a-9d51acf21180", x: 6288, y: 384} -->

opt b = 0

<!-- { section: "e322852d-ba88-428e-ae7f-dc7796d4cfdb", x: 6264, y: 840} -->

opt c = 2

<!-- { section: "e8e01be9-b923-4bf0-9812-12bea2510ea2", x: 8112, y: 792} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "aca1a9d2-6883-4aeb-a243-a8a75de33ead", x: 8616, y: -120} -->

opt a =

<!-- { section: "16672b83-5d7c-443c-ab95-ed2bd7c8636b", x: 8592, y: 408} -->

opt b =

<!-- { section: "8ab3b3c3-26a5-4276-9071-dfe8b68f3f44", x: 8640, y: 816} -->

opt c =

<!-- { section: "07e9c2d6-2b49-4906-beb6-b66ec07bb0c9", x: 7464, y: 600} -->

emojis do not show up

<!-- { section: "4dd9a827-d32b-4ccb-9295-2a8f2a2e32ce", x: -1200, y: 456} -->

**@Buhle**

please add in the other thingies here ^

<!-- { section: "f35a11c3-6201-4a86-b266-5ccef1561774", x: 456, y: 360} -->

**@Buhle,**

Not sure which was right for the DS note so have both code and save insight here, dlt the one you dont need please.

DS note: Flow result: quiz_pm3_started (yes)

<!-- { section: "73797d95-1a3e-4a1d-934b-a3af283a162b", x: 10944, y: 432} -->

**@buhle**

Please save the insights here

code block is here if you need that

<!-- { section: "e9eb8a92-d329-44c3-97b9-c14f9d6f9d5a", x: 12840, y: 552} -->

~~Update contact field, contact module =
Quiz Post module 3 ✅~~

<!-- { section: "2b2f331e-d514-435b-9f78-d7c8a7c2ce74", x: 13416, y: 528} -->

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

<!-- { section: "fe30df7e-a39c-42f1-98fe-019abb2dd2cd", x: 14040, y: 240} -->

**DS note:** Flow result: quiz_pm3_completed (yes)

**Eng note:** Update contact.next*engagement_time*

([Buhle](https://www.figma.com/files/1174087528366850825/user/1364872052852176049) this might be obsolete as we send the user to module 4 straight after)_

<!-- { section: "1dc71cf8-b3dd-4bbf-ace3-a3c524fa15ca", x: 6384, y: 408} -->

I think there is a typo here

<!-- { section: "2b19938f-6f92-42c9-ba8d-6dc6fa65da3b", x: 5640, y: 984} -->

```stack
card CodeBlock_804d50 do
  text("some text")
end

```

<!-- { section: "ca075569-4258-4ff2-a2ba-95976b312d3c", x: 8112, y: 984} -->

```stack
card CodeBlock_e12bc0 do
  text("some text")
end

```

<!-- { section: "a9428d3b-d248-424c-a71e-35bcb750b595", x: 11112, y: -288} -->

```stack
card Message9_1 do
  write_result("quiz_pm3_endline", "a")
  then(Message_10_1)
end

```

<!-- { section: "66c52ca7-1d48-410a-9fb1-45d164412be0", x: 480, y: -24} -->

```stack
card Message1 do
  write_result("quiz_pm3_started", "yes")
  then(Message_2)
end

```

<!-- { section: "9456d81c-dca2-4002-b195-98e4921836a1", x: 13008, y: -120} -->

```stack
card QuizCompleted do
  update_contact(quiz_post_module3_complete: "true")
  write_result("quiz_pm3_completed", "yes")
  then(RunStack_b8be21)
end

```

<!-- { section: "053d7c79-34f6-4412-a29c-a4c42f2c1115", x: 3792, y: -504} -->

```stack
card Message3_1 do
  write_result("quiz_pm3_q1_value", "a")
  write_result("quiz_pm3_q1_score", "0")
  then(Message_4_1)
end

```

<!-- { section: "ad2ff397-5b5b-417c-a676-645549a70720", x: 3816, y: 24} -->

```stack
card Message3_2 do
  write_result("quiz_pm3_q1_value", "b")
  write_result("quiz_pm3_q1_score", "1")
  then(Message_4_2)
end

```

<!-- { section: "dc869d47-d780-406b-8cd3-c200b8d25080", x: 3864, y: 600} -->

```stack
card Message3_3 do
  write_result("quiz_pm3_q1_value", "c")
  write_result("quiz_pm3_q1_score", "2")
  then(Message_4_3)
end

```

<!-- { section: "0bc76e47-cea9-4e70-88f1-7c2c1d787230", x: 6144, y: -432} -->

```stack
card Message5_1 do
  write_result("quiz_pm3_q2_value", "a")
  write_result("quiz_pm3_q2_score", "0")
  then(Message_6_1)
end

```

<!-- { section: "cad6f149-f02a-464b-ad8a-5de502c857e3", x: 6192, y: 48} -->

```stack
card Message5_2 do
  write_result("quiz_pm3_q2_value", "b")
  write_result("quiz_pm3_q2_score", "1")
  then(Message_6_2)
end

```

<!-- { section: "3d4aa9d1-958b-4216-97dd-30de75e47f8a", x: 6216, y: 528} -->

```stack
card Message5_3 do
  write_result("quiz_pm3_q2_value", "c")
  write_result("quiz_pm3_q2_score", "2")
  then(Message_6_3)
end

```

<!-- { section: "0aee106c-0333-4297-9a13-157491b5029f", x: 8496, y: -456} -->

```stack
card Message7_1 do
  write_result("quiz_pm3_q3_value", "a")
  write_result("quiz_pm3_q3_score", "0")
  then(Message_8_1)
end

```

<!-- { section: "b33fcb89-8e13-4270-8936-662c49183b11", x: 8496, y: 72} -->

```stack
card Message7_2 do
  write_result("quiz_pm3_q3_value", "b")
  write_result("quiz_pm3_q3_score", "1")
  then(Message_8_2)
end

```

<!-- { section: "d1646d9c-9b19-4fa2-9dc2-ece428e5016f", x: 8496, y: 504} -->

```stack
card Message7_3 do
  write_result("quiz_pm3_q3_value", "c")
  write_result("quiz_pm3_q3_score", "2")
  then(Message_8_3)
end

```

<!-- { section: "305408a9-392d-4750-a74c-0c09e6e8c437", x: 11112, y: 48} -->

```stack
card Message9_2 do
  write_result("quiz_pm3_endline", "b")
  then(Message_10_2)
end

```

<!-- { section: "676c0223-98ad-4449-a9e0-44e16485c204", x: -1080, y: -264} -->

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
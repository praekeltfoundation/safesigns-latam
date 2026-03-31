<!-- { section: "595340ec-bce6-4eb8-8c68-42def336d76e", x: -1224, y: -24} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.quiz_post_module5_complete_ == false and contact.contact_module == "MODULE_5" and
       contact.arm == "NARRATIVE"

```

<!-- { section: "36635e66-8540-49b5-8a26-a9f020b81e74", x: 288, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_1 =
    buttons(["Tell me more!"]) do
      text("Hello! 👋 

Let's start the day with a mini test: How is your conversation thermometer?")
    end

  then(Message1 when ref_Message_1 == "Tell me more!")
  then(Catch_all_1)
end

```

<!-- { section: "cba701b0-fbc0-4610-aad6-d7f000cc1c3f", x: 1392, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["Brilliant!"]) do
      text(
        "Sometimes when we fight, the conversation gets hot, very hot. So much so that it stops being productive and becomes unhealthy. I'm going to tell you three situations and you tell me if the character managed to keep a cool head 🥶 or if we got too hot 🌶️"
      )
    end

  then(Message_3 when ref_Message_2 == "Brilliant!")
  then(Catch_all_2)
end

```

<!-- { section: "b5f3db58-ea23-4b7f-a5cc-b0bcee16ead7", x: 456, y: -696} -->

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
        "He told me that he loved me so much that he wanted us to be more intimate. I love him, but I don't feel comfortable with that 🤔 What do I answer? 

A. It depends on how much you love me 😍 
B. I love you too, but I'm not comfortable with it yet. I know that, if you really love me, you will understand me 🫶 
C. Go to hell 👿"
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
    "❌ You don't need to do something you don't feel comfortable with because of pressure. If you don't want to do something, tell him, and if he really loves you, he'll understand!"
  )

  then(Message_5)
end

```

<!-- { section: "bae76967-bc24-4800-89a1-202f7d0c2d06", x: 4560, y: 144} -->

```stack
card Message_4_2, "Message_4_2", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Correct! You don't need to do something you don't feel comfortable with because of pressure. If you don't want to do something, tell him, and if he really loves you, he'll understand!"
  )

  then(Message_5)
end

```

<!-- { section: "055fe967-d787-4579-945f-36c759aa8684", x: 4560, y: 720} -->

```stack
card Message_4_3, "Message_4_3", code_generator: "TEXT_MESSAGE" do
  text(
    "🧐 You don't need to do something you don't feel comfortable with because of pressure. However, there are better ways to react. Suffice it to say that you don't want to do that."
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
        "He told me that he was going to leave me if we didn't have the same interest in doing sexy things 😮. What do I answer? 

A. I will do it as a proof of love 😍 
B. I don't feel comfortable with that. I know that if you really love me, you will understand 🫂 
C. I'm so sorry, I'm failing you 😭"
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
    "❌ If someone threatens you, they are trying to manipulate you! You can set boundaries and you shouldn't feel bad about it."
  )

  then(Message_7)
end

```

<!-- { section: "1e132075-acb2-41cc-b60a-a051561425a5", x: 6840, y: 120} -->

```stack
card Message_6_2, "Message_6_2", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Correct! If someone threatens you, they are trying to manipulate you! You can set boundaries and you shouldn't feel bad about it."
  )

  then(Message_7)
end

```

<!-- { section: "f8e2aeff-15ec-4ed9-a8da-94a21f5a69fe", x: 6840, y: 528} -->

```stack
card Message_6_3, "Message_6_3", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ You don't have to apologize. If someone threatens you, they are trying to manipulate you! You can set boundaries and you shouldn't feel bad about it."
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
      text("You're fighting and they record a video of you. What is seen in the video? 📹

A. I slap him 👋 
B. I have my arms crossed, I look away and I roll my eyes 🙄 
C. I look him in the eyes and speak assertively 🗣️")
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
    "❌ They don't need to fall into shouting or insults to send aggressive vibes. Slapping, pushing, or body language that says \"I'm not listening to you\" are signs of aggression. The thermometer went too hot!"
  )

  then(Message_9)
end

```

<!-- { section: "f87db9a0-001a-451f-9d89-a0b7be344f4e", x: 9096, y: 144} -->

```stack
card Message_8_2, "Message_8_2", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ They don't need to fall into shouting or insults to send aggressive vibes. If your body language says \"I'm not hearing you,\" the thermometer has gone too hot."
  )

  then(Message_9)
end

```

<!-- { section: "c6eb1bdc-486a-43a8-b538-69461a061aa2", x: 9096, y: 600} -->

```stack
card Message_8_3, "Message_8_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Correct! They don't need to resort to shouting or insults to send aggressive vibes. If body language is calm and people can listen to each other despite emotions, the thermometer has not gone too hot."
  )

  then(Message_9)
end

```

<!-- { section: "3333efb1-d2d3-4286-858f-c7cd11f61b49", x: 12720, y: -120} -->

```stack
card Message_12, "Message_12", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Super good! 👍", "I can improve 🙃"]) do
      text("How did you do on the mini test? 👀")
    end

  then(Message12_1 when ref_Message_12 == "Super good! 👍")
  then(Message12_2 when ref_Message_12 == "I can improve 🙃")
  then(Catch_all_8)
end

```

<!-- { section: "30eafa2d-62e1-4d7c-9012-2d3ae7e8a797", x: 11904, y: -1032} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "ee1ea4cc-78cc-45b6-ab28-33bfbeea3970", x: 14112, y: -240} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text(
    "You are very good at setting limits and you know it💫 You can share your experience with friends who need a little push to assert themselves💪🏼🫣"
  )

  then(Message_14)
end

```

<!-- { section: "30e9df33-e5e8-4892-9aea-85602429733c", x: 14064, y: 336} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Your limits are sometimes still made of jelly 🍮 Have more confidence in yourself! It's okay to say what you want and need as long as you do it with respect and assertiveness 👀"
  )

  then(Message_14)
end

```

<!-- { section: "5e096b31-9bf0-4b34-a9e7-ce3209bf9644", x: 14784, y: -48} -->

```stack
card Message_14, "Message_14", code_generator: "TEXT_MESSAGE" do
  text(
    "Remember healthy limits are pure love, love for yourself and for others ✨ You can't love or make anyone happy, while you make us happy. It all starts with security and self-love!"
  )

  then(Profile_6481b5)
end

```

<!-- { section: "0da0b28e-7ffc-4c25-b100-706d7c1cb5c2", x: 16704, y: -168} -->

```stack
card RunStack_b8be21, "RunStack_b8be21", code_generator: "RUN_STACK" do
  run_stack("238fea00-6805-4e90-80a7-d530ccd435c3")
end

```

<!-- { section: "e23cb69e-8cae-4aa2-aa07-afc3e3b32a23", x: 9816, y: -24} -->

```stack
card Message_9, "Message_9", code_generator: "TEXT_MESSAGE" do
  text(
    "Having good communication is hearing and saying what you want in an assertive and concise way 👌🏼"
  )

  then(Message_10)
end

```

<!-- { section: "03e683d8-88fb-41be-95d4-81b324ab1c7d", x: 10296, y: -24} -->

```stack
card Message_10, "Message_10", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["A", "B", "C"]) do
      text(
        "Your boyfriend sends you a shirtless photo and asks you for one in return. You tell him that you don't feel comfortable and he responds \"if you don't trust me, this is going nowhere!😡\" What do you say? 

A. It's not a matter of trust, but rather what I like to do 💁🏽‍♀️ 
B. If that's what you like, then we better leave it here 🙅🏽‍♀️ 
C. I do trust you, here is the photo 🤳🏼"
      )
    end

  then(Message10_1 when ref_Message_10 == "A")
  then(Message10_2 when ref_Message_10 == "B")
  then(Message10_3 when ref_Message_10 == "C")
end

```

<!-- { section: "8caa24ee-0f90-45cd-9827-4a6ec9a6fc03", x: 11736, y: -360} -->

```stack
card Message_11_1, "Message_11_1", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Okay! No one - least of all someone who claims to love you - can force you to do something you don't feel comfortable with. You would be right to be worried, and it is not a lack of confidence; No matter how careful your boyfriend is with the photo, he never knows if his cell phone could be stolen or hacked."
  )

  then(Message_12)
end

```

<!-- { section: "96320ddf-26e4-4461-a61a-04e034a8e022", x: 11712, y: 144} -->

```stack
card Message_11_2, "Message_11_2", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ No one - least of all someone who says they love you - can force you to do something you don't feel comfortable about. You would be right to be worried, and it is not a lack of confidence; No matter how careful your boyfriend is with the photo, he never knows if his cell phone could be stolen or hacked."
  )

  then(Message_12)
end

```

<!-- { section: "954797df-f8bb-4fa9-98c7-263543f3478e", x: 11712, y: 672} -->

```stack
card Message_11_3, "Message_11_3", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No one - least of all someone who says they love you - can force you to do something you don't feel comfortable about. You would be right to be worried, and it is not a lack of confidence; No matter how careful your boyfriend is with the photo, he never knows if his cell phone could be stolen or hacked."
  )

  then(Message_12)
end

```

<!-- { section: "ce28eb69-65d9-4493-886f-2511abcdcc73", x: 15272, y: -48} -->

```stack
card Profile_6481b5, "Profile_6481b5", code_generator: "UPDATE_CONTACT" do
  update_contact(quiz_post_module5_complete_: "true")
  then(QuizComplete)
end

```

<!-- { section: "35948745-b26a-4e89-be4b-de127dbfa3e1", x: 3168, y: 576} -->

**@Buhle**

Please save insights here

code block is here if you need that

<!-- { section: "10ddfc30-726b-4ec1-9880-b0c0f3f97b56", x: 3936, y: -144} -->

opt a = 0

<!-- { section: "f71771bc-5dff-4dd2-99ff-8ea609717ec6", x: 3936, y: 456} -->

opt b = 2

<!-- { section: "72c63982-e262-4342-926c-54f1ee6ac9b5", x: 3960, y: 960} -->

opt c = 1

<!-- { section: "ef26e5fa-5843-405d-b683-8dd9c1a5601c", x: 5616, y: 792} -->

code block is here  if you need that

<!-- { section: "e0d132f0-faa8-4578-a79d-a77253817d5e", x: 6264, y: -120} -->

opt a = 0

<!-- { section: "bf25cf1e-9525-46d1-8a4a-9d51acf21180", x: 6288, y: 384} -->

opt b = 2

<!-- { section: "e322852d-ba88-428e-ae7f-dc7796d4cfdb", x: 6264, y: 840} -->

opt c = 0

<!-- { section: "805ea77c-b877-4f21-89ac-c11bae23fae3", x: 7920, y: 720} -->

**@Buhle**

Please update the insights here

Also there is a code block is here  if you need that

<!-- { section: "aca1a9d2-6883-4aeb-a243-a8a75de33ead", x: 8616, y: -120} -->

opt a = 0

<!-- { section: "16672b83-5d7c-443c-ab95-ed2bd7c8636b", x: 8592, y: 408} -->

opt b = 0

<!-- { section: "8ab3b3c3-26a5-4276-9071-dfe8b68f3f44", x: 8640, y: 816} -->

opt c = 2

<!-- { section: "ce3c27c7-a896-4bab-8edd-0e1feba54f20", x: 2736, y: 168} -->

Emoji does not show up here

<!-- { section: "f2e662e4-4311-4550-b387-c0a59c91f6cb", x: 5232, y: 480} -->

emoji does not show up

<!-- { section: "abf79712-d2bf-41cc-afc0-b6a5f93ea467", x: 14040, y: 0} -->

emoji does not show up here

<!-- { section: "08c4681d-bf90-4ecd-92b5-cea7e1f50113", x: 11088, y: -96} -->

opt a = 2

<!-- { section: "24291e3c-412b-49f8-8a6e-a9d96e6e3302", x: 10392, y: 744} -->

**@Buhle**

Please update the insights here

Also there is a code block is here  if you need that

<!-- { section: "992f3ed4-a51e-419a-b918-ecc0b997edec", x: 11088, y: 432} -->

opt b = 2

<!-- { section: "9f993d2c-5e2a-459c-aaac-acdd61fbe101", x: 11088, y: 912} -->

opt c = 0

<!-- { section: "7810599e-fd52-4aa4-b31a-6ea14d2ee7f3", x: -120, y: 672} -->

**@Buhle**

Please add the other thingies here^

<!-- { section: "5a1e7dbd-d5f8-4b0c-8069-6bdef18f04fc", x: 816, y: 648} -->

**@buhle**

Please save the DS note here, not sure which block you needed so I gave you both, please dlt the one you dont need and make sure the other is hooked up

**DS note:** Flow result: quiz_pm5_started (yes)

<!-- { section: "7389f6ab-2262-4c27-a018-960504479c71", x: 5664, y: 648} -->

**@Buhle**\
Please save insights here

<!-- { section: "8c22bd05-fd04-4401-8fb2-e09619153ca0", x: 12864, y: 264} -->

**@Buhle**

Please update the insights here

<!-- { section: "867c120e-ced5-4d22-a447-b22039956923", x: 15216, y: 240} -->

Update contact field, Quiz Post Module 5 completed = yes ✅

<!-- { section: "107a7baa-1da9-4d29-b2f8-d65d1377105b", x: 16248, y: 192} -->

DS note: Flow result: quiz_pm5_completed (yes)

Eng note: Update contact.nextengagement_time

(Buhle this might be obsolete as we send the user to module 6 straight after)_

<!-- { section: "aeea27dd-b57f-417f-bbbc-c5dc933e518e", x: 15792, y: 192} -->

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

<!-- { section: "5e54dd15-a79e-4512-8ecf-888b38456afe", x: 6216, y: 480} -->

```stack
card Message5_3 do
  write_result("quiz_pm5_q2_value", "c")
  write_result("quiz_pm5_q2_score", "0")
  then(Message_6_3)
end

```

<!-- { section: "f067afb4-feee-443e-b545-8d0817dcac64", x: 8472, y: 480} -->

```stack
card Message7_3 do
  write_result("quiz_pm5_q3_value", "c")
  write_result("quiz_pm5_q3_score", "2")
  then(Message_8_3)
end

```

<!-- { section: "7f8bffce-0ce9-4ccd-82e5-e7e24d99a56a", x: 864, y: 96} -->

```stack
card Message1 do
  update_contact(quiz_post_module5_complete_: "false")
  write_result("quiz_pm5_started", "yes")
  then(Message_2)
end

```

<!-- { section: "6e815c89-a347-4c5d-9a78-b327cce62136", x: 15912, y: -168} -->

```stack
card QuizComplete do
  update_contact(quiz_post_module5_complete_: "true")
  write_result("quiz_pm1_completed", "yes")
  then(RunStack_b8be21)
end

```

<!-- { section: "0dd020b5-0fe4-4e8b-9064-467420a68c49", x: 3816, y: -504} -->

```stack
card Message3_1 do
  write_result("quiz_pm5_q1_value", "a")
  write_result("quiz_pm5_q1_score", "0")
  then(Message_4_1)
end

```

<!-- { section: "dd92a34f-e02b-48d1-960f-c81187bd0e52", x: 3816, y: 24} -->

```stack
card Message3_2 do
  write_result("quiz_pm5_q1_value", "b")
  write_result("quiz_pm5_q1_score", "2")
  then(Message_4_2)
end

```

<!-- { section: "37db9ecd-f304-4591-a99d-9bc7301d145e", x: 3816, y: 552} -->

```stack
card Message3_3 do
  write_result("quiz_pm5_q1_value", "c")
  write_result("quiz_pm5_q1_score", "1")
  then(Message_4_3)
end

```

<!-- { section: "9c3b26e5-3344-4755-b9fe-18724d51f905", x: 6144, y: -504} -->

```stack
card Message5_1 do
  write_result("quiz_pm5_q2_value", "a")
  write_result("quiz_pm5_q2_score", "0")
  then(Message_6_1)
end

```

<!-- { section: "1c6baede-897e-4534-838f-579c923b91e1", x: 6216, y: 24} -->

```stack
card Message5_2 do
  write_result("quiz_pm5_q2_value", "b")
  write_result("quiz_pm5_q2_score", "2")
  then(Message_6_2)
end

```

<!-- { section: "593c56c4-e635-4d37-aef1-33d7f0d0b198", x: 8520, y: 48} -->

```stack
card Message7_2 do
  write_result("quiz_pm5_q3_value", "b")
  write_result("quiz_pm5_q3_score", "0")
  then(Message_8_2)
end

```

<!-- { section: "065cb2c3-d6eb-48b2-9ee5-74aca876f59f", x: 8496, y: -552} -->

```stack
card Message7_1 do
  write_result("quiz_pm5_q3_value", "a")
  write_result("quiz_pm5_q3_score", "0")
  then(Message_8_1)
end

```

<!-- { section: "3eb59815-3dc0-4821-b8af-125bdd40894c", x: 13392, y: -384} -->

```stack
card Message12_1 do
  write_result("quiz_pm5_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "97347468-ea0b-4652-864b-4601472743a5", x: 13368, y: 72} -->

```stack
card Message12_2 do
  write_result("quiz_pm5_endline", "b")
  then(Message_13_2)
end

```

<!-- { section: "1309527a-1b15-459f-ae77-b02f2155c553", x: 11040, y: -504} -->

```stack
card Message10_1 do
  write_result("quiz_pm5_q4_value", "a")
  write_result("quiz_pm5_q4_score", "2")
  then(Message_11_1)
end

```

<!-- { section: "493075e1-7920-42cf-9d23-cd6f379123bb", x: 11064, y: 24} -->

```stack
card Message10_2 do
  write_result("quiz_pm5_q4_value", "b")
  write_result("quiz_pm5_q4_score", "2")
  then(Message_11_2)
end

```

<!-- { section: "ee3ce35e-977c-4e4a-8594-40fa9dc38605", x: 11088, y: 528} -->

```stack
card Message10_3 do
  write_result("quiz_pm5_q4_value", "c")
  write_result("quiz_pm5_q4_score", "0")
  then(Message_11_3)
end

```

<!-- { section: "08eb608e-e78f-4f18-b05f-664c0cb81ed1", x: -816, y: 48} -->

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
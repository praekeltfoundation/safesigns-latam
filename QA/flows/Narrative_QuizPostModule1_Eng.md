<!-- { section: "43084e90-e3ab-4978-97a2-502783cbd514", x: -480, y: -48} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.contact_module == "MODULE_1" and contact.quiz_post_module1_complete == false and
       contact.arm == "NARRATIVE"

```

<!-- { section: "cfcd17f6-4c1d-4067-a42f-7e6bb43600ff", x: 432, y: 0} -->

```stack
card Message_1, "Message_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_1 =
    buttons(["Tell me more!"]) do
      text("Hi friend! 👋 Let's start the day with a mini test: Toxic or cute?")
    end

  then(Message1 when ref_Message_1 == "Tell me more!")
  then(Catch_all_1)
end

```

<!-- { section: "cba701b0-fbc0-4610-aad6-d7f000cc1c3f", x: 1392, y: 0} -->

```stack
card Message_2, "Message_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_2 =
    buttons(["🤔"]) do
      text(
        "When we fall in love, we love everything our story does🥰 But... is everything it does healthy?"
      )
    end

  then(Message_3 when ref_Message_2 == "🤔")
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

<!-- { section: "0bd8a08d-bcbe-42d9-97c7-24b466fcc827", x: 2208, y: -24} -->

```stack
card Message_3, "Message_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["Brilliant!"]) do
      text(
        "I tell you the story of my friend Luisa and her boyfriend Mario. Let's help her detect when her cupid crosses the line 🎯"
      )
    end

  then(Message_4 when ref_Message_3 == "Brilliant!")
  then(Catch_all_3)
end

```

<!-- { section: "084aab97-fd2d-454f-b12a-8c80aa934919", x: 2208, y: -672} -->

```stack
card Catch_all_3, "Catch_all_3", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_3)
end

```

<!-- { section: "7b4d730e-338b-476c-aa4f-8a5d681fc043", x: 3024, y: -72} -->

```stack
card Message_4, "Message_4", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Cute, jealous of 💖", "She asked for it", "Toxic, too far"]) do
      text(
        "The other day, Luisa went out all afternoon with a friend and her cell phone battery ran out. Mario tried to call her and wrote to her all afternoon, but nothing at all. 

He became furious and wrote to all of his friends demanding that they tell him where Luisa was, and also left her inappropriate messages. Luisa got angry 😡 

Mario told Luisa that if she didn't disappear, he wouldn't be so crazy, but that he loves her a lot, and that's why he gets jealous. 

What do you think? 🤔"
      )
    end

  then(Message4_1 when ref_Message_4 == "Cute, jealous of 💖")
  then(Message4_2 when ref_Message_4 == "She asked for it")
  then(Message4_3 when ref_Message_4 == "Toxic, too far")
  then(Catch_all_4)
end

```

<!-- { section: "73f297ce-f97b-403d-a9e1-2cd8e191e119", x: 2976, y: -672} -->

```stack
card Catch_all_4, "Catch_all_4", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "d61839b7-418e-4bdb-bb97-f2f7def5157a", x: 4584, y: -432} -->

```stack
card Message_5_1, "Message_5_1", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ The situation may make Mario jealous, but does it justify him being this angry and also making her feel guilty? Maybe Luisa could have communicated better, but it is not her responsibility how Mario reacts."
  )

  then(Message_6)
end

```

<!-- { section: "bae76967-bc24-4800-89a1-202f7d0c2d06", x: 4560, y: 144} -->

```stack
card Message_5_2, "Message_5_2", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ It is not worth blaming others for our actions. Perhaps Luisa could have communicated better, but it is not her responsibility how Mario reacts."
  )

  then(Message_6)
end

```

<!-- { section: "055fe967-d787-4579-945f-36c759aa8684", x: 4560, y: 720} -->

```stack
card Message_5_3, "Message_5_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Okay! It is not worth blaming others for our actions. Perhaps Luisa could have communicated better, but it is not her responsibility how Mario reacts.
"
  )

  then(Message_6)
end

```

<!-- { section: "1784167a-3b27-4155-ab4e-cd1526d77275", x: 5472, y: 120} -->

```stack
card Message_6, "Message_6", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6 =
    buttons(["Protects her 💖", "I'm not sure 😕", "He controls her 🚫"]) do
      text(
        "There is a group of Luisa's friends who smoke and go out late 🪩 Mario doesn't want Luisa to go out with them because he thinks they are a bad influence. Luisa isn't sure what to say..."
      )
    end

  then(Message6_1 when ref_Message_6 == "Protects her 💖")
  then(Message6_2 when ref_Message_6 == "I'm not sure 😕")
  then(Message6_3 when ref_Message_6 == "He controls her 🚫")
  then(Catch_all_5)
end

```

<!-- { section: "0441c207-9fbf-42fa-ba68-12026e691523", x: 6840, y: -384} -->

```stack
card Message_7_1, "Message_7_1", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ This is not easy. Generally, a partner shouldn't pressure you to leave your friends. Only you can decide who you spend time with. Likewise, when you're with friends, you should only do things that you feel comfortable doing."
  )

  then(Message_8)
end

```

<!-- { section: "1e132075-acb2-41cc-b60a-a051561425a5", x: 6840, y: 120} -->

```stack
card Message_7_2, "Message_7_2", code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 In general, a partner should not pressure you to leave your friends. Only you can decide who you spend time with. Likewise, when you're with friends, you should only do things that you feel comfortable doing."
  )

  then(Message_8)
end

```

<!-- { section: "f8e2aeff-15ec-4ed9-a8da-94a21f5a69fe", x: 6840, y: 528} -->

```stack
card Message_7_3, "Message_7_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Okay! A partner shouldn't pressure you to leave your friends. Only you can decide who you spend time with. Likewise, when you're with friends, you should only do things that you feel comfortable doing."
  )

  then(Message_8)
end

```

<!-- { section: "262408fd-b9e8-4760-84cc-8bf50311b469", x: 5424, y: -1080} -->

```stack
card Catch_all_5, "Catch_all_5", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_6)
end

```

<!-- { section: "0bd6b88f-d225-4982-85e8-b0127b1788d8", x: 7704, y: 144} -->

```stack
card Message_8, "Message_8", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_8 =
    buttons(["Poor Mario 💖", "I'm not sure 😕", "Manipulator 🚫"]) do
      text(
        "Mario sent Luisa a photo where he was shirtless 🤳 and asked Luisa to send him one of hers. 

Luisa was worried that someone else could see that photo😳 Mario told her that it is one by one, and that it is wrong that he does trust her and she doesn't trust him."
      )
    end

  then(Message8_1 when ref_Message_8 == "Poor Mario 💖")
  then(Message8_2 when ref_Message_8 == "I'm not sure 😕")
  then(Message8_3 when ref_Message_8 == "Manipulator 🚫")
  then(Catch_all_6)
end

```

<!-- { section: "6612728f-639c-4277-882b-a0e50ee8eb67", x: 7320, y: -1128} -->

```stack
card Catch_all_6, "Catch_all_6", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_8)
end

```

<!-- { section: "e767928f-9a9b-43f8-b963-4f2337652888", x: 9096, y: -360} -->

```stack
card Message_9_1, "Message_9_1", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ No one - least of all someone who says they love you - can force you to do something you don't feel comfortable with. Luisa is right to be worried, and it is not a lack of confidence; No matter how careful Mario is with the photo, he never knows if his cell phone could be stolen or hacked.
"
  )

  then(Message_10)
end

```

<!-- { section: "f87db9a0-001a-451f-9d89-a0b7be344f4e", x: 9096, y: 144} -->

```stack
card Message_9_2, "Message_9_2", code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 No one - least of all someone who says they love you - can force you to do something you don't feel comfortable with. Luisa is right to be worried, and it is not a lack of confidence; No matter how careful Mario is with the photo, he never knows if his cell phone could be stolen or hacked."
  )

  then(Message_10)
end

```

<!-- { section: "c6eb1bdc-486a-43a8-b538-69461a061aa2", x: 9096, y: 600} -->

```stack
card Message_9_3, "Message_9_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Okay! No one - least of all someone who claims to love you - can force you to do something you don't feel comfortable with. Luisa is right to be worried, and it is not a lack of confidence; No matter how careful Mario is with the photo, he never knows if his cell phone could be stolen or hacked."
  )

  then(Message_10)
end

```

<!-- { section: "f08dda3e-c263-4c71-9c6b-16f5fd104952", x: 10416, y: 120} -->

```stack
card Message_10, "Message_10", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_10 =
    buttons(["Nice! give him them", "It's complicated 🤔", "Half controller 🚩"]) do
      text(
        "Luisa has different passwords on her social networks. He gave Mario his Snapchat password but not his Insta password📲 Mario asked him for it and offered him his password in exchange. What should Luisa do?"
      )
    end

  then(Message10_1 when ref_Message_10 == "Nice! give him them")
  then(Message10_2 when ref_Message_10 == "It's complicated 🤔")
  then(Message10_3 when ref_Message_10 == "Half controller 🚩")
  then(Catch_all_7)
end

```

<!-- { section: "2da312fb-df3f-463d-bca5-c3861d4e4a3c", x: 10320, y: -1248} -->

```stack
card Catch_all_7, "Catch_all_7", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_10)
end

```

<!-- { section: "38d177c3-bc07-45bc-b7f1-082d394840f6", x: 11784, y: -168} -->

```stack
card Message_11_1, "Message_11_1", code_generator: "TEXT_MESSAGE" do
  text(
    "❌ Your passwords are part of your privacy. You shouldn't share them if you don't feel comfortable about it. Think of it like your diary: no matter how much trust Luisa may have with Mario, there is nothing wrong with her wanting to keep a separate space."
  )

  then(Message_12)
end

```

<!-- { section: "0a06563a-05ea-431f-9540-e7ca4a56b527", x: 11760, y: 264} -->

```stack
card Message_11_2, "Message_11_2", code_generator: "TEXT_MESSAGE" do
  text(
    "🤔 Your passwords are part of your privacy. You shouldn't share them if you don't feel comfortable about it. Think of it like your diary: no matter how much trust Luisa may have with Mario, there is nothing wrong with her wanting to keep a separate space."
  )

  then(Message_12)
end

```

<!-- { section: "9cb1d1eb-cf71-43c7-ba14-edbca0429271", x: 11736, y: 672} -->

```stack
card Message_11_3, "Message_11_3", code_generator: "TEXT_MESSAGE" do
  text(
    "✅ Okay! Your passwords are part of your privacy. You shouldn't share them if you don't feel comfortable about it. Think of it like your diary: no matter how much trust Luisa may have with Mario, there is nothing wrong with her wanting to keep a separate space."
  )

  then(Message_12)
end

```

<!-- { section: "ddab208a-2a97-4964-afda-96f0a9299d39", x: 12888, y: 264} -->

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

<!-- { section: "85cd598b-e147-4446-b9f9-feecccc33a41", x: 12768, y: -1104} -->

```stack
card Catch_all_8, "Catch_all_8", code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "48279c97-64e7-48b0-9298-f339c626273c", x: 13776, y: 120} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Incredible, your radar is very accurate. Now, make sure you accompany your friends so they don't go overboard with them 💪🏼"
  )

  then(Message_14)
end

```

<!-- { section: "b24d6545-9eb7-42ec-9877-dd828e7f63b7", x: 13824, y: 456} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Sometimes it is not easy to detect when they seek to control or protect because we tend to associate pressure with love. Let's continue fine-tuning that radar 🫶"
  )

  then(Message_14)
end

```

<!-- { section: "c8e0a643-c679-4dd7-9fa4-19eec158a260", x: 14256, y: 264} -->

```stack
card Message_14, "Message_14", code_generator: "TEXT_MESSAGE" do
  text("Here's the trick💡 If someone feels pressured or uncomfortable, something is not right.")
  then(Profile_e835f8)
end

```

<!-- { section: "af2462ac-9d9a-440d-a2d7-511aee6aabe9", x: 15720, y: 264} -->

```stack
card RunStack_b8be21, "RunStack_b8be21", code_generator: "RUN_STACK" do
  run_stack("564e2738-5ebd-4d8b-83cc-de9e68e3688b")
end

```

<!-- { section: "fa90a9fd-0c64-4e98-b10d-17bbc2283e61", x: 14744, y: 264} -->

```stack
card Profile_e835f8, "Profile_e835f8", code_generator: "UPDATE_CONTACT" do
  update_contact(contact_module: "QUIZ_POST_MODULE_1")
  then(QuizComplete)
end

```

<!-- { section: "51e724b7-7e08-4824-922b-802100ebcba5", x: 14736, y: 480} -->

need a variable /insight name based on the grading, see notes under each

code block is here if you need that

opt a = 0

opt b = 0

opt c = 2

need a variable /insight name based on the grading, see notes under each

code block is here  if you need that

opt a = 0

opt b = 1

opt c = 2

need a variable /insight name based on the grading, see notes under each

code block is here  if you need that

opt a = 0

opt b = 1

opt c = 2

need a variable /insight name based on the grading, see notes under each

code block is here  if you need that

opt a = 0

opt b = 1

opt c = 2

<!-- { section: "f30a6823-384c-4e2b-a315-9b8da75169c1", x: 6144, y: 1128} -->

```stack
card CodeBlock_804d50 do
  text("some text")
end

```

<!-- { section: "eced14b3-17cc-407f-b931-6a588fdc51b7", x: 8256, y: 1200} -->

```stack
card CodeBlock_e12bc0 do
  text("some text")
end

```

<!-- { section: "f1c07217-49de-477a-9776-6ae92bd628ab", x: 10680, y: 1200} -->

```stack
card CodeBlock_6379ad do
  text("some text")
end

```

<!-- { section: "ebfc56ca-2ad6-43db-8b90-1d4a6ef5c9fc", x: 912, y: -24} -->

```stack
card Message1 do
  update_contact(quiz_post_module1_complete: "false")
  write_result("quiz_pm1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "1c260742-9ecd-4704-97f0-d8a0f6678ff1", x: 3864, y: 120} -->

```stack
card Message4_2 do
  write_result("quiz_pm1_q1_value", "b")
  write_result("quiz_pm1_q1_score", "0")
  then(Message_5_2)
end

```

<!-- { section: "b80179fb-6df2-4abc-9cda-e89f0b9c981f", x: 3864, y: -480} -->

```stack
card Message4_1 do
  write_result("quiz_pm1_q1_value", "a")
  write_result("quiz_pm1_q1_score", "0")
  then(Message_5_1)
end

```

<!-- { section: "b9fa4eca-7537-47df-b720-6193e6dc50d1", x: 3888, y: 600} -->

```stack
card Message4_3 do
  write_result("quiz_pm1_q1_value", "c")
  write_result("quiz_pm1_q1_score", "2")
  then(Message_5_3)
end

```

<!-- { section: "55a19b11-0ed2-47bd-bc7e-2e8910d643ee", x: 6192, y: -504} -->

```stack
card Message6_1 do
  write_result("quiz_pm1_q2_value", "a")
  write_result("quiz_pm1_q2_score", "0")
  then(Message_7_1)
end

```

<!-- { section: "7a861888-f16f-436e-a648-61e95b75d8bc", x: 6192, y: 0} -->

```stack
card Message6_2 do
  write_result("quiz_pm1_q2_value", "b")
  write_result("quiz_pm1_q2_score", "1")
  then(Message_7_2)
end

```

<!-- { section: "1a99e896-2538-47f6-bc46-e0cd01637068", x: 6192, y: 432} -->

```stack
card Message6_3 do
  write_result("quiz_pm1_q2_value", "c")
  write_result("quiz_pm1_q2_score", "2")
  then(Message_7_1)
end

```

<!-- { section: "2f92f679-698d-4b7c-ad70-32d0aea49ad2", x: 8472, y: -504} -->

```stack
card Message8_1 do
  write_result("quiz_pm1_q3_value", "a")
  write_result("quiz_pm1_q3_score", "0")
  then(Message_9_2)
end

```

<!-- { section: "cc1f4abd-c058-4ef1-9092-212b7457856c", x: 8520, y: -24} -->

```stack
card Message8_2 do
  write_result("quiz_pm1_q3_value", "b")
  write_result("quiz_pm1_q3_score", "1")
  then(Message_9_2)
end

```

<!-- { section: "ef8200cc-57ea-414f-a415-95064856a07f", x: 8568, y: 480} -->

```stack
card Message8_3 do
  write_result("quiz_pm1_q3_value", "c")
  write_result("quiz_pm1_q3_score", "2")
  then(Message_9_3)
end

```

<!-- { section: "c92d9086-327f-4f26-9792-d35baa97dfac", x: 11088, y: -288} -->

```stack
card Message10_1 do
  write_result("quiz_pm1_q4_value", "a")
  write_result("quiz_pm1_q4_score", "0")
  then(Message_11_1)
end

```

<!-- { section: "f9d882e6-7573-481a-b31a-6d2351f51de1", x: 11088, y: 168} -->

```stack
card Message10_2 do
  write_result("quiz_pm1_q4_value", "b")
  write_result("quiz_pm1_q4_score", "1")
  then(Message_11_2)
end

```

<!-- { section: "8a4af672-d4b6-441e-a0c8-f1f19ac3f0b8", x: 11088, y: 576} -->

```stack
card Message10_3 do
  write_result("quiz_pm1_q4_value", "c")
  write_result("quiz_pm1_q4_score", "2")
  then(Message_11_3)
end

```

<!-- { section: "a08bc838-658a-43bb-9f5f-40c5992a7747", x: 13296, y: 24} -->

```stack
card Message12_1 do
  write_result("quiz_pm1_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "71d45828-2100-4500-8a90-77512d6045c0", x: 13320, y: 384} -->

```stack
card Message12_2 do
  write_result("quiz_pm1_endline", "b")
  then(Message_13_2)
end

```

<!-- { section: "c1141239-63bb-42ae-83d8-db3e1e04e1cf", x: 15240, y: 192} -->

```stack
card QuizComplete do
  update_contact(quiz_post_module1_complete: "true")
  write_result("quiz_pm1_completed", "yes")
  then(RunStack_b8be21)
end

```

<!-- { section: "d08648f8-025b-427a-aff0-49a0d01a2c9a", x: -24, y: 192} -->

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
<!-- { section: "a7f2b862-817a-4fb5-a264-41bf445f645e", x: -1032, y: 96} -->

```stack
trigger(interval: "+1m", relative_to: "contact.next_engagement_time")
when contact.quiz_post_module1_complete == false and contact.contact_module == "MODULE_1" and
       contact.arm == "GAMIFIED" and contact.onboarding_complete == true

```

<!-- { section: "3d4c991d-3761-4a9e-a207-3aa46461bb50", x: 384, y: -24} -->

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

<!-- { section: "ec1c022c-adc0-4853-b41d-f066efc76aad", x: -240, y: 408} -->

```stack
card Branch_338047, "Branch_338047", code_generator: "CONDITIONALS" do
  then(
    RESERVED_DEFAULT_CARD
    when contact.arm == "GAMIFIED" and contact.contact_module == "MODULE_1" and
           contact.onboarding_complete == true
  )

  then(RunStack_fbd510 when contact.arm == "GAMIFIED" and contact.onboarding_complete == true)
  then(RESERVED_DEFAULT_CARD)
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

<!-- { section: "ed779c28-e256-4f42-bab3-3f2a72f00cf5", x: 744, y: -696} -->

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

<!-- { section: "c9920261-bc9d-43d9-a9f4-eeb715e2f630", x: 4632, y: 720} -->

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

<!-- { section: "70e0b134-699f-469e-8668-b5bfc07d5a13", x: 14136, y: 96} -->

```stack
card Message_13_1, "Message_13_1", code_generator: "TEXT_MESSAGE" do
  text(
    "Incredible, your radar is very accurate. Now, make sure you accompany your friends so they don't go overboard with them 💪🏼"
  )

  then(Message_14)
end

```

<!-- { section: "d678a5be-89de-49df-b333-b752eda64af4", x: 14088, y: 600} -->

```stack
card Message_13_2, "Message_13_2", code_generator: "TEXT_MESSAGE" do
  text(
    "Sometimes it is not easy to detect when they seek to control or protect because we tend to associate pressure with love. Let's continue fine-tuning that radar 🫶"
  )

  then(Message_14)
end

```

<!-- { section: "3730b9a6-49d0-49c2-9a76-c4a90f681a35", x: 14904, y: 264} -->

```stack
card Message_14, "Message_14", code_generator: "TEXT_MESSAGE" do
  text("Here's the trick💡 If someone feels pressured or uncomfortable, something is not right.")
  then(Message14)
end

```

<!-- { section: "d841a11f-a2c8-4aca-b332-837851d0b268", x: 312, y: 384} -->

```stack
card RunStack_fbd510, "RunStack_fbd510", code_generator: "RUN_STACK" do
  run_stack("05fc89de-144d-4685-8454-fb9dfe1ed2f5")
end

```

<!-- { section: "75d5b624-b862-4692-b485-df7208479806", x: 15840, y: 264} -->

```stack
card RunStack_9eaf87, "RunStack_9eaf87", code_generator: "RUN_STACK" do
  run_stack("e80863c0-a2b9-4cf7-b7e2-f8e083d9f0f3")
end

```

<!-- { section: "3f9af8af-e418-4a94-a518-b69a1a2a8910", x: 648, y: 480} -->

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 0

opt c = 2

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 1

opt c = 2

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 1

opt c = 2

**@buhle**

Please save the insights here

I added a code block is here if you need that, if not please delete it

opt a = 0

opt b = 1

opt c = 2

**@Buhle**

Please add in the other thingies here^

**@Buhle,**

Not sure which was right for the DS note so have both code and save insight here, dlt the one you dont need please.

DS note: Flow result: quiz_pm1_started (yes)

**@Buhle**

Save insights for DS note

Please save these insights here, its a DS note so not sure if you need a save insight or code block, so I have both here, please dlt the one you dont need

**@Buhle**

Please update these, the DS note so I added in both code and variable for you to choose.

Also there is an Eng note here, please add it too, I have put them both in the next note -->

Update contact field, contact
module : Quiz post module 1 ✅

DS note: Flow result: quiz_pm1_completed (yes)

~~Update contact.next_engagement_time~~

<!-- { section: "9f4c6f2b-701b-4ddd-92f2-6a79f05ae601", x: -768, y: -48} -->

Don't Panic!

The journey will just ignore this and continue with the next block

<!-- { section: "3640ac66-ab8a-4351-bdb4-164afadebb4c", x: 3864, y: -120} -->

a = 0

<!-- { section: "85f9a4d8-43bc-4aab-81aa-f9a99f1f81ed", x: 3840, y: 432} -->

b = 0

<!-- { section: "b316b0e3-6a64-4355-93c8-1aa2acfc6ed8", x: 3888, y: 888} -->

c = 2

<!-- { section: "ab1e0450-bccd-4573-aeda-b8640688792a", x: 6528, y: -216} -->

a = 0

<!-- { section: "2c24a8bb-f87d-4277-931e-3928ff52ec6b", x: 6504, y: 264} -->

b = 1

<!-- { section: "12867d60-582a-4a8f-902c-5ca799b9de2c", x: 6528, y: 816} -->

c = 2

<!-- { section: "532fbd80-a32e-4740-9c85-80c452918a01", x: 8736, y: -48} -->

a = 0

<!-- { section: "b2d4c37c-7902-4aa2-8dc7-d61231767aca", x: 8880, y: 432} -->

b = 1

<!-- { section: "7c9affc9-cea5-4ad3-b489-058074ee4bf0", x: 8736, y: 864} -->

c = 2

<!-- { section: "effd72ef-2721-4979-a539-e0804dd96c21", x: 11544, y: 96} -->

a = 0

<!-- { section: "5aff5ae5-65d6-4c87-be24-b153108d3428", x: 11472, y: 456} -->

b = 1

<!-- { section: "55d89592-ab3d-426f-8ee0-2a511e0f5ce0", x: 11520, y: 888} -->

c = 2

<!-- { section: "7b3cc2b4-2c7c-4739-b467-aa12a77fb742", x: 3264, y: 1008} -->

```stack
card CodeBlock_1fee90 do
  text("some text")
end

```

<!-- { section: "0ad18861-87c6-4753-894c-6d23de046930", x: 15360, y: 216} -->

```stack
card Message14 do
  update_contact(quiz_post_module1_complete: "true")
  write_result("quiz_pm1_completed", "yes")
  then(RunStack_9eaf87)
end

```

<!-- { section: "2f4e219b-2bdd-42b5-b6ba-41a2f62d489f", x: 888, y: -96} -->

```stack
card Message1 do
  write_result("quiz_pm1_started", "yes")
  then(Message_2)
end

```

<!-- { section: "4e093ef6-a74a-455c-8a67-83cb5d4563c5", x: 3840, y: -504} -->

```stack
card Message4_1 do
  write_result("quiz_pm1_q1_value", "a")
  write_result("quiz_pm1_q1_score", "0")
  then(Message_5_1)
end

```

<!-- { section: "bae536be-328b-45df-b2c5-afc3bfef90ce", x: 3864, y: 48} -->

```stack
card Message4_2 do
  write_result("quiz_pm1_q1_value", "b")
  write_result("quiz_pm1_q1_score", "1")
  then(Message_5_2)
end

```

<!-- { section: "672228db-060f-4230-a704-64ab187a575c", x: 3912, y: 552} -->

```stack
card Message4_3 do
  write_result("quiz_pm1_q1_value", "c")
  write_result("quiz_pm1_q1_score", "2")
  then(Message_5_3)
end

```

<!-- { section: "3786011f-f79b-49b0-80d0-5c08810ea322", x: 6096, y: -456} -->

```stack
card Message6_1 do
  opt_a = 0
  write_result("quiz_pm1_q2_value", "a")
  write_result("quiz_pm1_q2_score", "0")
  then(Message_7_1)
end

```

<!-- { section: "8881d63e-ba9c-471b-b22f-413592cf0efc", x: 6120, y: 0} -->

```stack
card Message6_2 do
  write_result("quiz_pm1_q2_value", "b")
  write_result("quiz_pm1_q2_score", "1")
  then(Message_7_2)
end

```

<!-- { section: "4e922942-b1bd-491d-9cd4-bab3e0dfa47d", x: 6144, y: 504} -->

```stack
card Message6_3 do
  write_result("quiz_pm1_q2_value", "c")
  write_result("quiz_pm1_q2_score", "2")
  then(Message_7_3)
end

```

<!-- { section: "7a1d406c-bb96-472f-b83b-60f3e22ec000", x: 8496, y: -504} -->

```stack
card Message8_1 do
  write_result("quiz_pm1_q3_value", "a")
  write_result("quiz_pm1_q3_score", "0")
  then(Message_9_1)
end

```

<!-- { section: "d57ab59b-e7cc-4d6a-b012-f5981d7ffc1b", x: 8496, y: 72} -->

```stack
card Message8_2 do
  write_result("quiz_pm1_q3_value", "b")
  write_result("quiz_pm1_q3_score", "1")
  then(Message_9_2)
end

```

<!-- { section: "5c03ad6f-281c-41f9-ae8b-39a48e9d4f59", x: 8496, y: 480} -->

```stack
card Message8_3 do
  write_result("quiz_pm1_q3_value", "c")
  write_result("quiz_pm1_q3_score", "2")
  then(Message_9_3)
end

```

<!-- { section: "fee95c3a-133a-440a-928e-ec09865adbc7", x: 11064, y: -240} -->

```stack
card Message10_1 do
  write_result("quiz_pm1_q4_value", "a")
  write_result("quiz_pm1_q4_score", "0")
  then(Message_11_1)
end

```

<!-- { section: "94bb9fc4-de86-46df-b75d-e3b1b424ced8", x: 11088, y: 144} -->

```stack
card Message10_2 do
  write_result("quiz_pm1_q4_value", "b")
  write_result("quiz_pm1_q4_score", "1")
  then(Message_11_2)
end

```

<!-- { section: "ab177615-d86f-4ded-9a9d-2eada29d8158", x: 11088, y: 552} -->

```stack
card Message10_3 do
  write_result("quiz_pm1_q4_value", "c")
  write_result("quiz_pm1_q4_score", "2")
  then(Message_11_3)
end

```

<!-- { section: "6a4d0ad6-087d-4b95-a2a7-8aad0d5697b8", x: 13464, y: 72} -->

```stack
card Message12_1 do
  write_result("quiz_pm1_endline", "a")
  then(Message_13_1)
end

```

<!-- { section: "c32d9f17-a6b6-485d-bf5a-1d9bb8f4599a", x: 13488, y: 528} -->

```stack
card Message12_2 do
  write_result("quiz_pm1_endline", "b")
  then(Message_13_2)
end

```

<!-- { section: "", x: -624, y: 312} -->

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
<!-- { section: "f4d9074c-7c98-42d6-a995-fc8c47467172", x: -960, y: -72} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "game_english")

```

<!-- { section: "e827e3d7-2d52-47a2-aa30-207104737862", x: -432, y: -72} -->

```stack
card Message_1, "Message_1",
  version: "1",
  uuid: "7a2e24a8-3596-5d7f-9b55-fb20a9b387f8",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Hello! 👋 I'm LíA, a digital friend with whom you can talk about relationships🌟 But be careful! You don't have to be or have been in a relationship to talk to me."
  )

  then(Message1)
end

```

<!-- { section: "8475232d-21bb-4fec-95a3-f83d690f0cdc", x: 816, y: -72} -->

```stack
card Message_2, "Message_2",
  version: "1",
  uuid: "9f7ec5da-1d07-583c-8c4e-847caa0447ff",
  code_generator: "TEXT_MESSAGE" do
  text(
    "I'm a robot, so don't be embarrassed or worry about what you tell me, your secrets will be kept between you and me! 🤐"
  )

  then(Message_3)
end

```

<!-- { section: "5d5daa2e-990b-4d97-98ae-9e570492c2ce", x: 1464, y: -72} -->

```stack
card Message_3, "Message_3",
  version: "1",
  uuid: "f7dbc4a3-b010-5972-84cb-dfcf14b04af1",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_3 =
    buttons(["Understood 🌸"]) do
      text(
        "Although I would like to, I do not have the power to answer questions 🥲, so our interaction will only be through your responses to the options that I show you when I ask you a question"
      )
    end

  then(Message_4 when ref_Message_3 == "Understood 🌸")
  then(Catch_all_1)
end

```

<!-- { section: "58204a70-f8b6-42f9-8625-1be15fdacf04", x: 1464, y: -312} -->

```stack
card Catch_all_1, "Catch_all_1",
  version: "1",
  uuid: "1c65817f-cc27-50da-888a-b426cf4cefbf",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_3)
end

```

<!-- { section: "7fd55d3a-0c68-4878-bc0b-2c0db9ca2484", x: 1968, y: -72} -->

```stack
card Message_4, "Message_4",
  version: "1",
  uuid: "e8ffc3d7-a274-524e-a474-3dc731d91083",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_4 =
    buttons(["Understood 🌸"]) do
      text(
        "Pilar and Mari are my creators. They are girls like you, they like to go out, joke and dance. They live in Bogotá. Together they have a podcast in which they talk about topics that interest us all ❤️"
      )
    end

  then(Message_5 when ref_Message_4 == "Understood 🌸")
  then(Catch_all_2)
end

```

<!-- { section: "abacb3e9-fcbe-4a86-998f-9ebe08c1a218", x: 1968, y: -312} -->

```stack
card Catch_all_2, "Catch_all_2",
  version: "1",
  uuid: "02396d13-4223-582c-8356-803cf5fe9f3f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_4)
end

```

<!-- { section: "9fe8f760-cb7f-483b-9463-a32e488d99d1", x: 2520, y: -72} -->

```stack
card Message_5, "Message_5",
  version: "1",
  uuid: "9726f5d1-d71c-534b-8a5a-0aeb175b7cae",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_5 =
    buttons(["Tell me more! 🎧"]) do
      text(
        "For the next 6 days you will listen to Pilar and Mari's podcast. Each day they will touch on a specific topic in which, through audios and questions, we will be able to interact and learn much more about romantic relationships. It won't take you more than 10 minutes a day ⏱️"
      )
    end

  then(Message_6 when ref_Message_5 == "Tell me more! 🎧")
  then(Catch_all_3)
end

```

<!-- { section: "5923fbe4-41a1-4d74-8ed8-fb6126024827", x: 2520, y: -312} -->

```stack
card Catch_all_3, "Catch_all_3",
  version: "1",
  uuid: "5048ef9e-f568-5fcf-91c8-482c9e1eb1ab",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_5)
end

```

<!-- { section: "2592f130-7adc-4db4-b2fc-2f72cf6c56d1", x: 3000, y: -72} -->

```stack
card Message_6, "Message_6",
  version: "1",
  uuid: "940e045e-d663-5ad9-aa1d-73d9e9e3af89",
  code_generator: "TEXT_MESSAGE" do
  text("*Audio file-Send podcast intro audio - INTRO Option 2*")
  then(Message_6_1)
end

```

<!-- { section: "7c7d1e17-6092-48cf-bb13-da4d4066dd78", x: 3504, y: -72} -->

```stack
card Message_6_1, "Message_6_1",
  version: "1",
  uuid: "6b6b9c02-132b-5be6-8e42-efa85fd5a4d4",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_6_1 =
    buttons(["I heard the audio!"]) do
      text("When the audio ends, press the I heard the audio button.")
    end

  then(Message_7 when ref_Message_6_1 == "I heard the audio!")
  then(Catch_all_4)
end

```

<!-- { section: "0ef740e2-545b-4215-ade8-9c63a4d025cb", x: 4008, y: -72} -->

```stack
card Message_7, "Message_7",
  version: "1",
  uuid: "41e37d86-5d9d-5348-b4f6-11efd73050e2",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_7 =
    buttons(["Understood 🌸"]) do
      text(
        "But before we start, I want to remind you something... 

Our podcast and our questions talk about daily life and relationships. But if there is something that Pilar and Mari talk about or a question that makes you feel uncomfortable, you can close the conversation. For us the most important thing is that you feel good!"
      )
    end

  then(Message_8 when ref_Message_7 == "Understood 🌸")
  then(Catch_all_5)
end

```

<!-- { section: "eb6c4440-6eee-4050-80c8-e2c1c2209893", x: 3504, y: -312} -->

```stack
card Catch_all_4, "Catch_all_4",
  version: "1",
  uuid: "33ab2a9e-29f1-5c94-ad10-a1d74ef38186",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_6_1)
end

```

<!-- { section: "2b9bfb22-f52d-41a9-a6a1-3090a6d39544", x: 4008, y: -312} -->

```stack
card Catch_all_5, "Catch_all_5",
  version: "1",
  uuid: "4d2962be-6850-500d-b8d5-df3162098b68",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_7)
end

```

<!-- { section: "0adff9da-ed5b-4bd3-9804-3499c5e8f319", x: 4560, y: -72} -->

```stack
card Message_8, "Message_8",
  version: "1",
  uuid: "20bab473-95ec-59b0-9098-c8341ca65398",
  code_generator: "QUESTION" do
  ref_Message_8 = ask("Can you tell me your name or what you want me to call you? 🤩")
  update_contact(name: "@ref_Message_8")
  then(Profile_5651c6)
end

```

<!-- { section: "aded55f8-d9fd-4cd7-a2a8-29a970b84231", x: 5592, y: -72} -->

```stack
card Message_9, "Message_9",
  version: "1",
  uuid: "3bfae072-3443-5819-b544-830334fa1fe0",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_9 =
    buttons(["Yes ✅", "No ❌"]) do
      text("Did I understand correctly that I can call you @contact.name? 👀")
    end

  then(Message_11 when ref_Message_9 == "Yes ✅")
  then(Message_10 when ref_Message_9 == "No ❌")
  then(Catch_all_6)
end

```

<!-- { section: "925af20c-02fe-4380-a7cd-83a913b6922e", x: 5640, y: -768} -->

```stack
card Catch_all_6, "Catch_all_6",
  version: "1",
  uuid: "f75f2f87-6113-5f10-91c5-a593027ffe42",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_9)
end

```

<!-- { section: "17bfb8ea-3e11-4742-93ea-343a610e809f", x: 4944, y: 456} -->

```stack
card Message_10, "Message_10",
  version: "1",
  uuid: "f2c0c14d-6e2f-503c-b326-7af1749d8bb5",
  code_generator: "QUESTION" do
  ref_Message_10 = ask("Let's try again! Write the name you want me to call you by 🤩")
  update_contact(name: "@ref_Message_10")
  then(Profile_5259a4)
end

```

<!-- { section: "58a9c45d-36db-4d50-a544-bc0faadb04a2", x: 6216, y: -72} -->

```stack
card Message_11, "Message_11",
  version: "1",
  uuid: "c1150661-f277-52ed-8552-5bdd4fec91b5",
  code_generator: "QUESTION" do
  ref_Message_11 = ask("Can you write your ID card number?")
  then(IDCard)
end

```

<!-- { section: "ea821f0b-2c27-4480-9fbd-96e971909e2f", x: 7344, y: 0} -->

```stack
card Message_12, "Message_12",
  version: "1",
  uuid: "ff7a633a-e913-5416-be74-9c2b279e6491",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_12 =
    buttons(["Yes ✅", "No ❌"]) do
      text("Did I understand correctly that your ID card number is @contact.idcard? 👀")
    end

  then(Message_14 when ref_Message_12 == "Yes ✅")
  then(Message_13 when ref_Message_12 == "No ❌")
  then(Catch_all_7)
end

```

<!-- { section: "7df556bd-7f55-450d-a811-acbadc3fa2f1", x: 7272, y: -672} -->

```stack
card Catch_all_7, "Catch_all_7",
  version: "1",
  uuid: "41a6a70c-2236-5c31-8025-51c95fb6765f",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_12)
end

```

<!-- { section: "a8ccbd34-7f55-4828-bd04-96dfc6ee1cfb", x: 6888, y: 552} -->

```stack
card Message_13, "Message_13",
  version: "1",
  uuid: "e9f2a183-4f31-505d-828d-a00cf6ed37b2",
  code_generator: "QUESTION" do
  ref_Message_13 = ask("Let's try again! Write your ID card number 🤩")
  then(IDCard)
end

```

<!-- { section: "042b577e-b0c9-447d-9c39-4eb721a58c04", x: 7968, y: 0} -->

```stack
card Message_14, "Message_14",
  version: "1",
  uuid: "c18ddaee-a707-51d7-b0f4-d49666081a9d",
  code_generator: "TEXT_MESSAGE" do
  text("Nice to meet you, @contact.name😜")
  then(Message14)
end

```

<!-- { section: "5f2b8d58-a9dc-4daf-8d02-927e5c91e237", x: 9144, y: 0} -->

```stack
card Message_15, "Message_15",
  version: "1",
  uuid: "0a762502-2877-5dbc-8002-bd4447233d62",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Message_15 =
    buttons(["Let's go ✅"]) do
      text("Ready to listen to Pilar y Mari's podcast? Join me to listen to them this week ❤️")
    end

  then(RunStack_65436a when ref_Message_15 == "Let's go ✅")
  then(Catch_all_8)
end

```

<!-- { section: "1444507d-3806-4c9b-8c00-f8cab796defb", x: 9768, y: 0} -->

```stack
card RunStack_65436a, "RunStack_65436a",
  version: "1",
  uuid: "d8800400-eeef-5894-ba0e-64bbe4db71b3",
  code_generator: "RUN_STACK" do
  run_stack("1e5522f4-3d24-488d-92a8-8110a5e67489")
end

```

<!-- { section: "0d3e12af-8528-4855-a405-56b35fb66e29", x: 9144, y: -288} -->

```stack
card Catch_all_8, "Catch_all_8",
  version: "1",
  uuid: "f51e6f73-cd5f-5cd6-bb7a-3dee8b6a0084",
  code_generator: "TEXT_MESSAGE" do
  text("I didn't understand that very well. Please try again using my buttons")
  then(Message_15)
end

```

<!-- { section: "f2f65e17-01de-4cd2-8fb0-338ca83f2bbb", x: 4944, y: -72} -->

```stack
card Profile_5651c6, "Profile_5651c6",
  version: "1",
  uuid: "0f20c229-6876-586c-8bb0-6a159b0c15be",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_8")
  then(Message_9)
end

```

<!-- { section: "f875a0c9-2d02-4e7c-aaa7-21d982c1212d", x: 4944, y: 168} -->

```stack
card Profile_5259a4, "Profile_5259a4",
  version: "1",
  uuid: "dfcb7e74-f5c2-5c4e-891f-93df3e7d2c85",
  code_generator: "UPDATE_CONTACT" do
  update_contact(name: "@ref_message_10")
  then(Message_9)
end

```

<!-- { section: "9aa7b0b0-7e5a-4ea6-82fd-708837818ddc", x: -960, y: 120} -->

arm = gamified

<!-- { section: "a60fba1a-0b4b-42b1-9ef4-00411c18e27f", x: 192, y: 264} -->

onboarding_complete = no

<!-- { section: "071d4ab1-4939-46d4-b840-d0064fb7b4ab", x: 192, y: 360} -->

**DS note:**

Contact field: arm (gamified)

Flow result: onboarding_started (yes)

<!-- { section: "40c306bb-ee45-4727-b55d-7ad8644ec878", x: 192, y: 528} -->

link this in to the above flow when done & dlt this note

<!-- { section: "86c128ba-3ec1-4343-9578-9f43468cf125", x: 6264, y: 432} -->

**@Eng we need a check here**

The LATAM ID number has 10 numbers, please set up a check here to confirm that the id they have given us is valid.

Use code block below if needed, if not please delete it

<!-- { section: "ce0a7fd6-7673-4af3-b9ab-3ead91f67f0f", x: 8520, y: 360} -->

**@Buhle**

Update contact field:\
onboarding_completed =yes**

DS note:**

~~Contact field: id_card {user input}~~

Flow result: onboarding_completed (yes)

**@Tam**

Is this different from the idcard that we are using for updating contact field after user validation? **Contact field: id_card {user input} ✅**

<!-- { section: "12773617-e5b8-4725-8e66-69292704c92f", x: 192, y: -72} -->

```stack
card Message1 do
  update_contact(arm: "gamified")
  update_contact(onboarding_complete: "false")
  write_result("onboarding_started", "yes")
  then(Message_2)
end

```

<!-- { section: "cdceeee7-2b44-4864-98fa-4e0653966947", x: 6792, y: -72} -->

```stack
card IDCard
     when isnumber(@ref_message_11) and
            len(@ref_message_11) == 10 and
            is_nil_or_empty(@ref_message_13) do
  log("ID updated to @ref_message_11 from message 11")
  update_contact(idcard: "@ref_message_11")
  then(Message_12)
end

card IDCard
     when isnumber(@ref_message_13) and
            len(@ref_message_13) == 10 do
  log("ID updated to @ref_message_13 from message 13")
  update_contact(idcard: "@ref_message_13")
  then(Message_12)
end

card IDCard do
  log("Incorrect ID")
  then(Message_13)
end

```

<!-- { section: "0a0a1fe1-2d0c-4fd2-b345-ab7363f8776c", x: 8496, y: 0} -->

```stack
card Message14 do
  update_contact(onboarding_complete: "true")
  write_result("onboarding_completed", "yes")
  then(Message_15)
end

```

<!-- { section: "b57e1e1a-5905-4821-8742-d7e4d8aa264e", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```

<!-- { section: "INTERACTION_TIMEOUT_CELL", x: 0, y: 0} -->

```stack
interaction_timeout(300)

```
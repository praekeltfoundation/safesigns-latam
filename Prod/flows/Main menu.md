<!-- { section: "c886321e-3ced-4cd0-a6bb-580b7edcfc0c", x: -792, y: -1728} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_any_exact_phrase(event.message.text.body, ["menu", "hi", "hello"])

```

<!-- { section: "074f5a88-7fd8-4e20-a6e8-ddf0bb6b7a74", x: -384, y: -1728} -->

```stack
card Menu, "Menu", code_generator: "LIST" do
  ref_Menu =
    list("Menu", ["❓ I've got a question", "🧑 Chat to an expert", "ℹ️ About us", "🚪Exit"]) do
      text("What would you like to do today @contact.name?")
    end

  then(FAQ when ref_Menu == "❓ I've got a question")
  then(Chat_to_expert when ref_Menu == "🧑 Chat to an expert")
  then(About_us when ref_Menu == "ℹ️ About us")
  then(Exit when ref_Menu == "🚪Exit")
end

```

<!-- { section: "8ecc1a87-87c9-4171-82b5-5641a2317b95", x: 864, y: -2712} -->

```stack
card Question_1, "Question_1", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Question_1 =
    buttons(["⬅️ Back"]) do
      text("*Question 1*

Write the answer to question 1 here. ")
    end

  then(FAQ when ref_Question_1 == "⬅️ Back")
end

```

<!-- { section: "d7b7674a-ba01-4696-afdb-bff0ef06adeb", x: 864, y: -2400} -->

```stack
card Question_2, "Question_2", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Question_2 =
    buttons(["⬅️ Back"]) do
      text("*Question 2*

Write the answer to question 2 here. ")
    end

  then(FAQ when ref_Question_2 == "⬅️ Back")
end

```

<!-- { section: "893ed2ed-a232-4c9f-bd53-41266a36af19", x: 864, y: -2064} -->

```stack
card Question_3, "Question_3", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Question_3 =
    buttons(["⬅️ Back"]) do
      text("*Question 3*

Write the answer to question 3 here. ")
    end

  then(FAQ when ref_Question_3 == "⬅️ Back")
end

```

<!-- { section: "7a38bec4-69bc-4df5-b6a1-10a2754a2894", x: 216, y: -624} -->

````stack
card Exit, "Exit", code_generator: "TEXT_MESSAGE" do
  text("I hope you found the information you were looking for.

If you have more questions or need further assistance, feel free to ask. Just type ```menu```.

We're here to help! 👋😊")
end

````

<!-- { section: "2a5503a7-8c52-4815-9168-0a4fe83599b5", x: 216, y: -2712} -->

```stack
card FAQ, "FAQ", code_generator: "LIST" do
  ref_FAQ =
    list("Select a question", ["Question 1", "Question 2", "Question 3", "🏠 Back to main menu"]) do
      text("*Topic 1 FAQ*

We're here to help you find answers to common questions.

Please select a question to find the answer.")
    end

  then(Question_1 when ref_FAQ == "Question 1")
  then(Question_2 when ref_FAQ == "Question 2")
  then(Question_3 when ref_FAQ == "Question 3")
  then(Menu when ref_FAQ == "🏠 Back to main menu")
end

```

<!-- { section: "ea166fd0-f50c-4013-b49a-15972f5711ba", x: 240, y: -1728} -->

```stack
card Chat_to_expert, "Chat_to_expert", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Chat_to_expert =
    buttons(["Chat now", "🏠 Back to main menu"]) do
      text("*Chat to an expert* 👩‍⚕️

We have experts online from 9:00am to 5:00 pm weekdays to answer your questions.")
    end

  then(Expert_question when ref_Chat_to_expert == "Chat now")
  then(Menu when ref_Chat_to_expert == "🏠 Back to main menu")
end

```

<!-- { section: "9f761a1b-f0a7-4449-9612-ff0b4d91d750", x: 672, y: -1728} -->

```stack
card Expert_question, "Expert_question", code_generator: "QUESTION" do
  ref_Expert_question = ask("So we can help you faster, what's your question?")
  then(Route_to_operator)
end

```

<!-- { section: "a39cbc04-c02a-4b54-b019-913dae27500c", x: 240, y: -1224} -->

```stack
card About_us, "About_us", code_generator: "REPLY_BUTTON_TEXT" do
  ref_About_us =
    buttons(["🏠 Back to main menu"]) do
      text("*About us ℹ️*

[Name of Organisation's] mission to improve the lives of [target audience].

We do so by providing X, Y and Z.

Find out more on our website:
www.impactorg.org")
    end

  then(Menu when ref_About_us == "🏠 Back to main menu")
end

```

<!-- { section: "e6e94cd6-7afd-43bb-a7a9-d8bfaa7f287c", x: 1056, y: -1728} -->

```stack
card Route_to_operator, "Route_to_operator", code_generator: "HANDOVER_STARTS" do
  send_content("1ffa350e-27d1-74ff-0362-590d8621099c", true)
  then(HANDOVER_HOLD_75e262)
end

card HANDOVER_HOLD_75e262, "HANDOVER_HOLD_75e262", code_generator: "HANDOVER_HOLD" do
  send_content("68e05dd9-5b30-0ec6-6324-d03de0676725")
  add_label("Requested help")
end

```

<!-- { section: "be9b8261-9701-4917-ad61-09b8f1852317", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
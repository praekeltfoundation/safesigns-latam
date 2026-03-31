<!-- { section: "40d22ba0-898c-4499-b3ff-568529b4b144", x: 500, y: 0} -->

```stack
card Event, "Event", code_generator: "QUESTION" do
  ref_Event = ask("Hello this is my first text. respond with a text or voice note.")
  then(Branch_3f9c46)
end

```

<!-- { section: "23c73b63-d394-47cc-bdaf-80f0082a86cf", x: 960, y: 0} -->

```stack
card Branch_3f9c46, "Branch_3f9c46", code_generator: "CONDITIONALS" do
  then(CodeBlock_45d18c when @event.message.type == "audio")
  then(CodeBlock_45d18c when @event.message.type == "text")
  then(Text_ed4111)
end

```

<!-- { section: "ab4ae0c1-0466-4b47-bbc6-838fb97f20d7", x: 1440, y: -192} -->

```stack
card Text_7d2ee1, "Text_7d2ee1", code_generator: "TEXT_MESSAGE" do
  text("Is a audio")
end

```

<!-- { section: "03bbdeee-78c2-4003-ace9-679243f7ed14", x: 1440, y: -96} -->

```stack
card Text_cc73d6, "Text_cc73d6", code_generator: "TEXT_MESSAGE" do
  text("Is a text")
end

```

<!-- { section: "c6124e02-9558-418c-8a3b-c3bd970d3e92", x: 816, y: 384} -->

```stack
card Text_ed4111, "Text_ed4111", code_generator: "TEXT_MESSAGE" do
  text("Retry format not allowed")
  then(Event)
end

```

<!-- { section: "a67a47c4-e615-4e78-995f-f34bbddfd11c", x: 576, y: 504} -->

```stack
card TestDate do
  weekdays = ["sunday", "monday", "tuesday", "wednesday", "thursday", "friday", "saturday"]
  log("@weekdays")

  tomorrow_date = datetime_add(now(), 1, "D")
  text("2mr Date: @tomorrow_date")

  tomorrow_day_number = weekday(tomorrow_date)
  text("tomorrow_day_number: @tomorrow_day_number")

  tomorrow_day = weekdays[tomorrow_day_number - 1]
  text("Day: @tomorrow_day")

  time_to_send = datetime_next(tomorrow_day, "13:00")
  text("To send: @time_to_send")
end

```

<!-- { section: "c8e14f86-7596-4455-9f53-349c5a942d44", x: 240, y: 360} -->

```stack
card Validate when isstring(@q1) do
  text("it can be saved some text @q1")
end

card Validate when @q1.message.type == "audio" do
  text("some text @q1")
end

card Validate do
  text("Format is not allowed @q1, message: @q1.message, @q1.message.type")
end

```

<!-- { section: "ab3514ab-a961-4489-b08c-7183496ec5e2", x: 1464, y: 48} -->

```stack
card CodeBlock_45d18c do
  text("correct format")
  write_result("test", "@event")
end

```

<!-- { section: "630cbec3-ebbc-46c2-9506-5bb45e1e4838", x: 0, y: 48} -->

```stack
card RESERVED_TRIGGER, "RESERVED_TRIGGER", code_generator: "RESERVED_TRIGGER" do
  # placeholder_trigger
end

```

<!-- { section: "1c583a95-96c4-48a8-ae69-01f0e688ce06", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
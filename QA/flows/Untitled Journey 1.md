<!-- { section: "4d959c8f-94f6-4510-a720-c5491f6f28ed", x: 0, y: 0} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "!test time")

```

<!-- { section: "0956de01-6d05-4655-ace5-e23f83264760", x: 500, y: 0} -->

```stack
card Text_1, "Text_1", code_generator: "TEXT_MESSAGE" do
  text("Hello this is my first text.")
  then(CodeBlock_024d6a)
end

```

<!-- { section: "d40d0681-2536-418a-8e0a-9a5377947e19", x: 1296, y: 72} -->

```stack
card CodeBlock_1217d7 do
  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_evening = datevalue("@tomorrow_date", "%Y-%m-%dT18:00:00.000000z")
  parsed_date = parse_datevalue(tomorrow_evening, "%FT%T%.000000z")
  next_day = datetime_add(parsed_date, 1, "D")
  text("@tomorrow_date")
  text("@tomorrow_evening")
  text("@parsed_date")
  text("@next_day")
end

```

<!-- { section: "32f4bbf0-a5fa-469f-ac55-ce502d9b8d86", x: 840, y: 120} -->

```stack
card CodeBlock_024d6a do
  weekdays = ["sunday", "monday", "tuesday", "wednesday", "thursday", "friday", "saturday"]

  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day_number = weekday(tomorrow_date)
  tomorrow_day = weekdays[tomorrow_day_number - 1]
  text("@tomorrow_date")
  next_engagement_time = datetime_next(tomorrow_day, "13:00")
  text("@next_engagement_time")
end

```

<!-- { section: "97b33754-93c1-4557-b4bf-0ed4015840fe", x: 1104, y: -432} -->

```stack
card CodeBlock_ac0ff5 do
  tomorrow_date = datetime_add(now(), 1, "D")
  tomorrow_day = day(tomorrow_date)
  tomorrow_month = month(tomorrow_date)
  tomorrow_year = year(tomorrow_date)
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  tomorrow_afternoon = datetime_add(tomorrow, 13, "h")
  text("@tomorrow")
  text("@tomorrow_afternoon")
  next_day = datetime_add(tomorrow_afternoon, 1, "D")
  text("@next_day")
end

```

<!-- { section: "3b8baa1c-98f5-4b11-8ba1-b43b655fcf78", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
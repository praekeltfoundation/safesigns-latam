<!-- { section: "05fd3aa8-dcdd-4dc2-8381-6204d7ad422e", x: 984, y: -24} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "!test sticker")

```

<!-- { section: "39280dc3-0d95-4358-85ca-1c0cfc81f373", x: 1544, y: -24} -->

```stack
card Buttons_202eb5, "Buttons_202eb5", code_generator: "REPLY_BUTTON_TEXT" do
  ref_Buttons_202eb5 =
    buttons(["Button 1"]) do
      text("wesfwsefr")
    end

  update_contact(idcard: "@ref_Buttons_202eb5")
  then(RESERVED_DEFAULT_CARD when ref_Buttons_202eb5 == "Button 1")
  then(Text_3db280)
end

```

<!-- { section: "22472ae2-40a4-48b4-b7c7-e870dbcf5f40", x: 2032, y: -24} -->

```stack
card Text_3db280, "Text_3db280", code_generator: "TEXT_MESSAGE" do
  text("@contact.idcard 
")
  then(Image_2b4515)
end

```

<!-- { section: "8a533d84-d355-4d81-bf3b-96ee72b7bf50", x: 2520, y: -24} -->

```stack
card Image_2b4515, "Image_2b4515", code_generator: "MEDIA_IMAGE" do
  image("ba7934b6-526c-4b99-b320-a6895eb08d1c-Módulo1__Ubi.webp")
  text("a sticker")
end

```

<!-- { section: "88c40048-526a-4738-9848-79f1500eaaa9", x: 1608, y: 384} -->

```stack
card CodeBlock_a4c11d do
  image("97dd9744-3b37-fdb8-a049-7c54290ac52b")
end

```

<!-- { section: "3604b197-fd1d-4284-9b9d-4635001f303b", x: 648, y: 624} -->

```stack
card CodeBlock_aecb07 do
  text("""
    {"recipient_type": "individual",
  "to": "@contact.whatsapp_id",
  "type": "sticker",
  "sticker": {
  "id": "97dd9744-3b37-fdb8-a049-7c54290ac52b"
  }}
  """)

  post_response =
    post("https://whatsapp.turn.io/v1/messages",
      timeout: 5_000,
      body: """
        {"recipient_type": "individual",
      "to": "@contact.whatsapp_id",
      "type": "sticker",
      "sticker": {
      "id": "97dd9744-3b37-fdb8-a049-7c54290ac52b"
      }}
      """,
      headers: [
        ["content-type", "application/json"],
        [
          "Authorization",
          "Bearer eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJhdWQiOiJUdXJuIiwiZXhwIjoxNzMyMTg1MDM4LCJpYXQiOjE3MzIwMTIyODUsImlzcyI6IlR1cm4iLCJqdGkiOiIyZGZiNDRmNy03YTRhLTRlYTEtYWU0NC0yNWY1ZWQxNTA3MWUiLCJuYmYiOjE3MzIwMTIyODQsInN1YiI6Im51bWJlcjo2Mzc1IiwidHlwIjoiYWNjZXNzIn0.QJDF8RXidDFxEWWLBlvi3kIX4IlTSoyWJ80ZLyLONCeOvE0GgIhdcuxyMBFSx1VZIrJ5RR0aAzc3rZvcgrRqYA"
        ]
      ]
    )

  log("@post_response")
end

```

<!-- { section: "0acc5d0d-ced8-452f-bd59-169274c5783c", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
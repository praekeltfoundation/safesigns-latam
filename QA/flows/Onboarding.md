<!-- { section: "12a32097-f1c6-446e-8b51-d79518fb4fa4", x: -1344, y: -648} -->

```stack
trigger(on: "MESSAGE RECEIVED")
when has_any_phrase(event.message.text.body, "Hi, hi, Hola, hola") or
       has_only_phrase(event.message.text.body, "ob_english")

```

<!-- { section: "faf49a68-1eca-4d84-963d-48287673f019", x: -984, y: -648} -->

```stack
card Start, "Start",
  version: "1",
  uuid: "d13a5c78-821f-5eca-adac-d8ee6c46553d",
  code_generator: "REPLY_BUTTON_IMAGE" do
  ref_Start =
    buttons(["Start ➡️"]) do
      image("1dd6e95d-07e0-44cb-8ab7-4e259f9dc283-0f19b38e-01c1-435e-abee-9060f09ffc3d-Smile.png")

      text("Hello and welcome to our service! 👋

Let's get you registered.

🕘 It will take less than 2 minutes.")
    end

  then(Name when ref_Start == "Start ➡️")
end

```

<!-- { section: "127ea6f9-ff6d-4ba6-8a2b-65345ffb5e4b", x: -576, y: -648} -->

```stack
card Name, "Name",
  version: "1",
  uuid: "0dcddf99-cec3-5fe6-a8f8-8970e9aa6128",
  code_generator: "QUESTION" do
  ref_Name = ask("🟢 ⚪️ ⚪️

What's your name?")
  update_contact(name: "@ref_Name")
  then(Language)
end

```

<!-- { section: "34ee4d2d-8cc3-4cac-a2fe-6bffe2365598", x: 144, y: -648} -->

```stack
card Consent, "Consent",
  version: "1",
  uuid: "a9110cc5-3aaa-586d-b4dd-c13a16418ce5",
  code_generator: "REPLY_BUTTON_TEXT" do
  ref_Consent =
    buttons(["Yes", "No"]) do
      text("🟢 🟢 🟢

Final question: would you like to receive important notifications from us?")
      footer("You can change this preference at any time")
    end

  write_result("Opted In", ref_Consent)
  then(Profile_4355d1 when ref_Consent == "Yes")
  then(Profile_4355d1_1d6caf when ref_Consent == "No")
end

```

<!-- { section: "ec407ee1-ef0b-41fb-960b-bdf5c6514070", x: 912, y: -648} -->

```stack
card ConsentYes, "ConsentYes",
  version: "1",
  uuid: "96f01ef4-86d2-5cd3-8934-de38a8e00dbd",
  code_generator: "TEXT_MESSAGE" do
  text(
    "Thank you for your consent, @contact.name! You will start receiving important notifications from us on WhatsApp."
  )

  then(Confirmation)
end

```

<!-- { section: "5d4023f9-f380-44cb-9085-96b736c30d6a", x: 912, y: -312} -->

```stack
card ConsentNo, "ConsentNo",
  version: "1",
  uuid: "a2a3ac2b-4fb6-5cfd-bd27-c4075186fdf3",
  code_generator: "TEXT_MESSAGE" do
  text("No problem @contact.name. We respect your choice. You will not receive notifications.

We won't message you unless you message us!")
  then(Confirmation)
end

```

<!-- { section: "57a27917-62ec-4845-a393-406cd3a2ee55", x: -216, y: -648} -->

```stack
card Language, "Language",
  version: "1",
  uuid: "73de74da-f872-5387-aec3-679f6e708879",
  code_generator: "QUESTION" do
  ref_Language = ask("🟢 🟢 ⚪️

Nice to meet you @contact.name 👋

What's your preferred language?")
  update_contact(language: "")
  then(Consent)
end

```

<!-- { section: "6dd54120-9920-489d-86ac-c27050b4050e", x: 1296, y: -648} -->

```stack
card Confirmation, "Confirmation",
  version: "1",
  uuid: "47739a5f-bcd3-56b7-a90a-ae54e29aec08",
  code_generator: "TEXT_MESSAGE" do
  text("Your registration is complete ✅

Let's get started! 🚀 ")
  then(RunStack_58a6b7)
end

```

<!-- { section: "1bc8109a-ff66-4c40-9efd-7dbaea5c3f39", x: 1656, y: -648} -->

```stack
card RunStack_58a6b7, "RunStack_58a6b7",
  version: "1",
  uuid: "ef0ef44c-755b-5049-b5b9-743a30f358ca",
  code_generator: "RUN_STACK" do
  run_stack("859a3671-352b-4cee-8cce-0cad94dd896e")
end

```

<!-- { section: "5a352aff-ea22-40b7-a89f-4647a9ba759d", x: 528, y: -648} -->

```stack
card Profile_4355d1, "Profile_4355d1",
  version: "1",
  uuid: "5fd42a87-9c6b-5de9-b9da-d53d9b164cb9",
  code_generator: "UPDATE_CONTACT" do
  update_contact(opted_in: "true")
  then(ConsentYes)
end

```

<!-- { section: "4125949d-9ba6-4cc2-b38d-510834f5d1e4", x: 552, y: -360} -->

```stack
card Profile_4355d1_1d6caf, "Profile_4355d1_1d6caf",
  version: "1",
  uuid: "b790fb83-444f-5b00-b335-f1e62ae9795a",
  code_generator: "UPDATE_CONTACT" do
  update_contact(opted_in: "false")
  then(ConsentNo)
end

```

<!-- { section: "28a68f78-e449-4401-b383-f68256011417", x: -1344, y: -984} -->

**Trigger**

Triggers allow you to define rules on which your journeys trigger.

In this case, it triggers when you receive a message that says "hi", "hello" or "hey".

There's a multitude of ways to trigger journeys, such as schedules, based on people's profiles and much more.

<!-- { section: "5ec9f1f7-7380-4f88-bdf0-dadd49d4edb7", x: -624, y: -888} -->

**Registration**

You can also collect information from people and save that against their profile. If you select the *Name* block, you can see that it's updating the person's profile with their response.

<!-- { section: "f71ad233-f356-43e8-8787-fdefbfe67bba", x: 504, y: -840} -->

**Consent**

To respect people's privacy and for legal purposes, it's important you get consent from the people using your service.

<!-- { section: "466f2480-f8ad-44f6-ac48-1dd5a6d30759", x: 1656, y: -840} -->

**Go to Menu**

Now that the registration is done, and we've received consent from people, we take them to the main menu.

<!-- { section: "b5f3b646-ed04-4c25-bd91-e3bf5b5a1f44", x: -216, y: -792} -->

If you run a multilingual service, you could branch it based on the user's preferred language.

<!-- { section: "75fa4ce8-4c7c-4c6e-b209-3b2895d8d094", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```

<!-- { section: "INTERACTION_TIMEOUT_CELL", x: 0, y: 0} -->

```stack
interaction_timeout(300)

```
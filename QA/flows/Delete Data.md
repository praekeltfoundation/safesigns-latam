<!-- { section: "3be6258b-16a0-49b1-b816-bc047c262915", x: -648, y: -192} -->

```stack
trigger(on: "MESSAGE RECEIVED") when has_only_phrase(event.message.text.body, "delete_data")

```

<!-- { section: "9c8b7578-b15e-457d-9975-ac28a10d8b4a", x: 72, y: -216} -->

```stack
card Text_1, "Text_1",
  version: "1",
  uuid: "dc24ea0d-8f6e-514c-aaf9-c1a4d79c9898",
  code_generator: "TEXT_MESSAGE" do
  text("Your data is being deleted. This may take up to 5 minutes.
Note: You will not get a confirmation message.")
  then(CodeBlock_7d17a8)
end

```

<!-- { section: "ebe2612d-2e57-43a9-b52a-2471ccb80c51", x: 560, y: -216} -->

```stack
card CodeBlock_7d17a8 do
  cull_data()
  then(Text_005f28)
end

```

<!-- { section: "30278e53-a8da-48dd-8d7c-a3db240b988b", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
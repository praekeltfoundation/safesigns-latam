<!-- { section: "2fea4c36-96ee-4f07-84f4-b11ccfc45663", x: 552, y: 0} -->

```stack
trigger(interval: "+1h", relative_to: "contact.first_message_received_at")

```

<!-- { section: "94b91f49-5b7d-46d3-b7cc-8475b6c673e0", x: 960, y: 0} -->

```stack
card WHATSAPP_TEMPLATE_MESSAGE_b57b74, "WHATSAPP_TEMPLATE_MESSAGE_b57b74",
  code_generator: "WHATSAPP_TEMPLATE_MESSAGE" do
  send_message_template("feedback", "en", ["@contact.name ", "our service"], buttons: [CSAT])
end

```

<!-- { section: "d08ea380-5a9d-4879-a58a-a580f3cf2dd4", x: 1344, y: 0} -->

```stack
card CSAT, "CSAT", code_generator: "LIST" do
  ref_CSAT =
    list("Select answer", ["1️⃣  Very unhelpful", "2️⃣", "3️⃣", "4️⃣", "5️⃣ Very helpful"]) do
      text("Was this conversation helpful?")
    end

  then(Insight_4f5ed8 when ref_CSAT == "1️⃣  Very unhelpful")
  then(Insight_4f5ed8_044640 when ref_CSAT == "2️⃣")
  then(Insight_4f5ed8_3cc3d4 when ref_CSAT == "3️⃣")
  then(Insight_4f5ed8_3cc3d4_70c960 when ref_CSAT == "4️⃣")
  then(Insight_4f5ed8_3cc3d4_20956b when ref_CSAT == "5️⃣ Very helpful")
end

```

<!-- { section: "a7927462-f8ff-4fc3-ac01-82605f67c18c", x: 2184, y: 0} -->

```stack
card One_to_three, "One_to_three", code_generator: "QUESTION" do
  ref_One_to_three =
    ask("Thank you for your feedback, though we're sorry to hear this conversation wasn't helpful.

Could you please tell us what we can do better?

Your input is incredibly valuable to us.")

  write_result("Feedback Answer", ref_One_to_three)
  then(Anything_else)
end

```

<!-- { section: "3a7bcadf-fe50-45b4-baf3-af87a684949d", x: 2184, y: 456} -->

```stack
card Four, "Four", code_generator: "QUESTION" do
  ref_Four =
    ask(
      "Thank you for your feedback! We're glad you find our chatbot helpful.

Is there anything specific you'd like to suggest for improvement, or any comments you'd like to share with us?"
    )

  write_result("Feedback Answer", ref_Four)
  then(Anything_else)
end

```

<!-- { section: "b8fa2f2d-4979-4950-8c4d-02c973da1a17", x: 2184, y: 816} -->

```stack
card Five, "Five", code_generator: "QUESTION" do
  ref_Five =
    ask("That's fantastic to hear! 😊 We're thrilled that you're satisfied with our chatbot.

If you have any additional comments or suggestions, please feel free to share them with us.

Your feedback helps us continue providing a great experience.")

  write_result("Feedback Answer", ref_Five)
  then(Anything_else)
end

```

<!-- { section: "c007bd74-7b5e-44aa-9b89-b371e13e7b63", x: 2712, y: 408} -->

```stack
card Anything_else, "Anything_else", code_generator: "QUESTION" do
  ref_Anything_else = ask("Is there anything else you'd like to share?")
  write_result("Feedback Anything else", ref_Anything_else)
  then(Thank_you)
end

```

<!-- { section: "f68a64b1-3adc-49c4-a4af-f15603b95aec", x: 3024, y: 0} -->

````stack
card Thank_you, "Thank_you", code_generator: "TEXT_MESSAGE" do
  text("Thank you so much for taking the time to provide feedback 🙏

Your input is invaluable as we work to make our chatbot even better.

If you want to continue chatting with us, type ```menu```.

Have a wonderful day! 👋😊")
end

````

<!-- { section: "05124a24-9fa3-47a1-9584-4562651e1ebd", x: 1728, y: 0} -->

```stack
card Insight_4f5ed8, "Insight_4f5ed8", code_generator: "WRITE_RESULTS" do
  write_result("Feedback Score", "1")
  then(One_to_three)
end

```

<!-- { section: "ea492410-4971-45ae-881a-6105ece2e41d", x: 1728, y: 168} -->

```stack
card Insight_4f5ed8_044640, "Insight_4f5ed8_044640", code_generator: "WRITE_RESULTS" do
  write_result("Feedback Score", "2")
  then(One_to_three)
end

```

<!-- { section: "67a28946-b4c2-46ca-b622-db8a6d6d7cf0", x: 1728, y: 360} -->

```stack
card Insight_4f5ed8_3cc3d4, "Insight_4f5ed8_3cc3d4", code_generator: "WRITE_RESULTS" do
  write_result("Feedback Score", "3")
  then(One_to_three)
end

```

<!-- { section: "23f86d2c-7082-448e-9dba-ced8f2835523", x: 1728, y: 528} -->

```stack
card Insight_4f5ed8_3cc3d4_70c960, "Insight_4f5ed8_3cc3d4_70c960", code_generator: "WRITE_RESULTS" do
  write_result("Feedback Score", "4")
  then(Four)
end

```

<!-- { section: "23bc51f2-6215-448d-936f-b07dd31210eb", x: 1728, y: 816} -->

```stack
card Insight_4f5ed8_3cc3d4_20956b, "Insight_4f5ed8_3cc3d4_20956b", code_generator: "WRITE_RESULTS" do
  write_result("Feedback Score", "5")
  then(Five)
end

```

<!-- { section: "5dc57c39-bffb-44bd-ae03-1f45b8f1b196", x: 1728, y: -336} -->

**Saving Insights**

To save your user's response and refer to them later, you can use the Save insights block. Alternatively, select the block you want to save the results for, scroll down to "Write results" and you can save the there.

To see the results, click on "Export insights" on the top right — and we'll email you a spreadsheet.

<!-- { section: "567bf197-15b8-4f17-b4c4-30bac39373d0", x: 552, y: -336} -->

**Trigger journeys based on time**

You can start journeys based on any date field on a person's profile.

This example waits an hour from the first message received and sends users a feedback journey.

Send appointment reminders, birthday messages and much more!

<!-- { section: "debd96c5-7d58-4150-b8ed-53560a79af4f", x: 960, y: -336} -->

**Message Templates**

WhatsApp has restrictions on how you can contact people 24 hours after they last messaged you.

To do so, you need to use a Message Template — message that has been pre-approved by Meta.

Then, for your journey to continue, people need to response to that message — we suggest a button with a clear call to action.

<!-- { section: "6b27eed0-e473-4a6e-ab96-a9df979c7888", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```
<!-- { section: "b3bcc77e-aafb-4104-bd66-6b29c2b63e6f", x: -192, y: 0} -->

```stack
trigger(on: "MESSAGE RECEIVED", global: true)
when has_any_exact_phrase(event.message.text.body, [
       "Ayuda",
       "ayuda",
       "AYUDA",
       "ayúdame",
       "Ayúdame",
       "AYUDAME"
     ])

```

<!-- { section: "beb1a160-c968-4a12-9e87-fd7a4ecc6836", x: 408, y: 0} -->

```stack
card Ayuda_01, "Ayuda_01",
  version: "1",
  uuid: "dc24ea0d-8f6e-514c-aaf9-c1a4d79c9898",
  code_generator: "TEXT_MESSAGE" do
  text("¿Necesitas hablar con alguien? ✉️

Aquí tienes algunos puntos de contacto muy útiles:

*• Línea MAAD*: lineamaad@uniandes.edu.co
*• Ombudsperson*: ombudsperson@uniandes.edu.co
*• Decanatura de Estudiantes*: centrodeapoyo@uniandes.edu.co
*• Consejerxs MAAD*: ombudsperson.uniandes.edu.co/maqd1/consejerxs-maad

⭐")
end

```

<!-- { section: "cfc02d52-c006-48a5-b972-a773fc371ec6", x: 360, y: -120} -->

We need to add a button here that returns the user to the last module they were busy with.

<!-- { section: "503831b9-19b4-451f-9a38-dcd903d32fa7", x: -240, y: -120} -->

Help information provided when users send in a global trigger word "ayuda":

<!-- { section: "a01c01a4-e008-44e5-82ff-94211e4d5465", x: -1000, y: 0} -->

```stack
card RESERVED_DEFAULT_CARD, "RESERVED_DEFAULT_CARD", code_generator: "RESERVED_DEFAULT_CARD" do
  # RESERVED_DEFAULT_CARD
end

```

<!-- { section: "INTERACTION_TIMEOUT_CELL", x: 0, y: 0} -->

```stack
interaction_timeout(300)

```
# Wavify

Logo

2 paragraphs exaplining why i made this

software architscture diagram

describe the app

code snipet to highlight and describe @ high level

flowchart LR
  User[User]

  subgraph Frontend[Frontend]
    App[React Vite App]
    UI[Shared Components]
    State[App State]
    SDK[Cloud Client SDK]
  end

  subgraph Backend[Lovable Cloud Backend]
    Auth[Authentication]
    Database[Database with RLS]
    Realtime[Realtime Updates]
    Storage[File Storage]
    Functions[Backend Functions]
  end

  subgraph External[External Services]
    Stripe[Stripe PIX]
    Social[Google and Apple Login]
  end

  User --> App
  App --> UI
  App --> State
  App --> SDK
  UI --> State
  UI --> SDK
  State --> SDK

  SDK --> Auth
  SDK --> Database
  SDK --> Realtime
  SDK --> Storage
  SDK --> Functions

  Social --> Auth
  Auth --> Database
  Database --> Realtime
  Realtime --> State

  Functions --> Stripe
  Stripe --> Functions
  Functions --> Database




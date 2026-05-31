# Wavify

Logo

2 paragraphs exaplining why i made this

software architscture diagram

describe the app

code snipet to highlight and describe @ high level


graph LR
    User((User))

```mermaid
[Uplograph LR
    User((User))

    subgraph FE["Frontend — React + Vite SPA"]
        Pages["Pages / Routes"]
        UI["Shared Components"]
        State["Auth, Language, Favorites, Unread"]
        Client["Supabase Client SDK"]
    end

    subgraph BE["Backend — Lovable Cloud"]
        Auth["Auth / Email + OAuth"]
        DB[("PostgreSQL — RLS")]
        RT["Realtime"]
        Storage["File Storage"]
        EF["Edge Functions"]
    end

    subgraph EXT["External"]
        Stripe["Stripe — PIX"]
        OAuth["Google / Apple OAuth"]
    end

    User --> Pages
    Pages --> UI
    Pages --> State
    UI --> State
    State --> Client
    Pages --> Client
    UI --> Client

    Client -->|Auth| Auth
    Client -->|CRUD| DB
    Client -->|Subscribe| RT
    Client -->|Upload| Storage
    Client -->|Invoke| EF

    Auth <-->|OIDC| OAuth
    Auth -->|Auto-profile| DB

    DB -.-> RT
    RT -->|Push| State

    EF -->|Session| Stripe
    Stripe -->|Webhook| EF
    EF --> DB

    style FE fill:#e0f2fe,stroke:#0369a1
    style BE fill:#f3e8ff,stroke:#7c3aed
    style EXT fill:#fee2e2,stroke:#dc2626
ading wavify-architecture-simple.mmd…]()

```

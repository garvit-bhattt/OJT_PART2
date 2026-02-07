backend/
│
├── src/
│   ├── app.ts                         # Express app config
│   ├── server.ts                      # HTTP server + WebSocket attach
│
│   ├── config/
│   │   ├── env.ts                     # Environment variables
│   │   ├── db.ts                      # MySQL connection
│   │   ├── redis.ts                   # Redis client
│   │   └── jwt.ts                     # JWT secret & config
│
│   ├── http/                          # REST APIs (Express)
│   │   ├── routes/
│   │   │   └── auth.routes.ts         # /login /logout
│   │   ├── controllers/
│   │   │   └── auth.controller.ts
│   │   └── middleware/
│   │       └── auth.middleware.ts     # JWT verification (HTTP)
│
│   ├── websocket/
│   │   ├── index.ts                   # WebSocket initialization
│   │   ├── socket.ts                  # onConnection handler
│   │   ├── middleware.ts              # JWT verification (WebSocket)
│   │   ├── rooms.ts                   # Join / leave poll rooms
│   │   ├── events.ts                  # JOIN_POLL / VOTE routing
│   │   └── disconnect.ts              # Cleanup on disconnect
│
│   ├── modules/
│   │   ├── user/
│   │   │   ├── user.model.ts          # User DB model
│   │   │   ├── user.service.ts        # User business logic
│   │   │   └── user.types.ts          # User types
│   │   │
│   │   └── poll/
│   │       ├── poll.model.ts          # Poll DB model
│   │       ├── poll.service.ts        # Poll business logic
│   │       ├── poll.controller.ts     # Poll WebSocket handlers
│   │       ├── poll.validator.ts      # Poll input validation
│   │       └── poll.types.ts          # Poll types
│
│   ├── services/
│   │   ├── auth.service.ts            # JWT helpers
│   │   ├── vote.service.ts            # One-vote-per-user logic
│   │   ├── redis.service.ts           # Redis counters + Pub/Sub
│   │   └── broadcast.service.ts       # Emit updates to rooms
│
│   ├── workers/
│   │   └── vote.worker.ts             # Async DB writes
│
│   ├── utils/
│   │   ├── logger.ts
│   │   ├── errors.ts
│   │   └── constants.ts
│
│   └── types/
│       └── socket.d.ts                # WebSocket type extensions
│
├── migrations/                        # DB migrations
│
├── tests/                             # Unit / integration tests
│
├── .env                               # Environment variables
├── package.json
└── tsconfig.json

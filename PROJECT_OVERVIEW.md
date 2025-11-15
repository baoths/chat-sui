# SUI MESSENGER - Ứng Dụng Chat Phi Tập Trung Trên Blockchain Sui

## Tên Đề Án
**Sui Messenger** - Decentralized Chat Application on Sui Blockchain

---

## 1. Mục Tiêu

### Mục tiêu chính:
- Xây dựng một nền tảng chat **phi tập trung, minh bạch và bảo mật** trên blockchain Sui
- Cung cấp khả năng giao tiếp **không bị kiểm duyệt** và **không phụ thuộc vào máy chủ tập trung**
- Tạo ra một hệ thống chat với **quyền sở hữu dữ liệu hoàn toàn** thuộc về người dùng
- Chứng minh khả năng ứng dụng blockchain Sui vào các ứng dụng thực tế hàng ngày

### Mục tiêu phụ:
- Tích hợp wallet Sui một cách liền mạch cho trải nghiệm người dùng tối ưu
- Xây dựng UI/UX thân thiện, dễ sử dụng cho người dùng không chuyên về blockchain
- Tối ưu hóa chi phí gas và hiệu suất transaction trên Sui
- Tạo nền tảng mở rộng cho các tính năng nâng cao như group chat, file sharing, v.v.

---

## 2. Vấn Đề Hiện Tại / Tính Ứng Dụng Vào Hệ Sinh Thái Sui

### Vấn đề của các ứng dụng chat tập trung hiện tại:
1. **Kiểm duyệt và giám sát**: Các nền tảng chat tập trung (WhatsApp, Telegram, Discord) có thể kiểm duyệt nội dung, xóa tài khoản, hoặc chặn người dùng
2. **Rủi ro bảo mật**: Dữ liệu chat lưu trữ trên máy chủ tập trung, dễ bị tấn công hoặc rò rỉ
3. **Thiếu quyền sở hữu**: Người dùng không sở hữu dữ liệu của mình, phụ thuộc hoàn toàn vào nhà cung cấp dịch vụ
4. **Thiếu minh bạch**: Không thể xác minh cách dữ liệu được xử lý và lưu trữ
5. **Single point of failure**: Khi server trung tâm gặp sự cố, toàn bộ hệ thống ngừng hoạt động

### Tính ứng dụng vào hệ sinh thái Sui:

#### A. Khai thác ưu điểm của Sui:
- **Tốc độ cao**: Sui có khả năng xử lý giao dịch song song, phù hợp cho ứng dụng chat real-time
- **Chi phí thấp**: Gas fee trên Sui rất thấp, phù hợp cho các transaction nhỏ như gửi tin nhắn
- **Object model độc đáo**: Sui's object-centric model cho phép quản lý messages, rooms, profiles một cách hiệu quả
- **Finality nhanh**: Transaction finality nhanh giúp messages xuất hiện gần như tức thì

#### B. Đóng góp cho hệ sinh thái Sui:
- **Showcase use case thực tế**: Chứng minh Sui không chỉ phù hợp cho DeFi/NFT mà còn cho social apps
- **Tăng số lượng người dùng**: Ứng dụng chat dễ tiếp cận, thu hút người dùng mới vào Sui ecosystem
- **Tăng transaction volume**: Chat app tạo ra lượng lớn transactions, tăng network activity
- **Developer template**: Cung cấp template mã nguồn mở cho các developers khác học hỏi và phát triển

#### C. Tính thực tiễn:
- **Community chat**: Các DAO, NFT projects trên Sui có thể sử dụng để giao tiếp nội bộ
- **Customer support**: Dự án blockchain có thể tích hợp để hỗ trợ khách hàng
- **Private messaging**: Giao tiếp riêng tư cho các giao dịch OTC, thương mại
- **Governance discussions**: Thảo luận về proposals, voting trong các tổ chức phi tập trung

---

## 3. Tính Độc Đáo

### Điểm khác biệt so với các ứng dụng chat blockchain khác:

1. **Object-Centric Architecture**:
   - Mỗi message, room, profile là một object độc lập trên Sui
   - Cho phép ownership rõ ràng và transfer nếu cần
   - Khác với các blockchain khác chỉ lưu hash hoặc pointer

2. **Registry-Based Discovery System**:
   - Sử dụng 4 registry riêng biệt: ProfileRegistry, RoomRegistry, MessageRegistry, RoomMemberRegistry
   - Cho phép query hiệu quả và scalable
   - Thiết kế module hóa, dễ mở rộng

3. **Hybrid On-chain/Off-chain Design**:
   - Metadata và ownership: on-chain
   - Content có thể mở rộng lên IPFS/Arweave cho messages dài (future feature)
   - Cân bằng giữa decentralization và practicality

4. **Username Uniqueness với Case-Insensitive**:
   - Hệ thống username unique case-insensitive (hiếm thấy trong Move smart contracts)
   - Tránh confusion và squatting attacks

5. **Real-time Membership Tracking**:
   - Track members trong room real-time through events
   - Member count on-chain để tính toán incentives (future)

6. **Gas-Optimized Design**:
   - Sử dụng Sui's parallel execution
   - Batch operations có thể thực hiện independent
   - Event-driven architecture giảm số lượng queries

### So sánh với giải pháp tương tự:

| Tính năng | Sui Messenger | Traditional Web2 | Other Blockchain Chat |
|-----------|--------------|------------------|---------------------|
| **Decentralization** | ✅ Fully | ❌ No | ⚠️ Partial |
| **Transaction Speed** | ✅ <1s | ✅ <1s | ❌ 10-60s |
| **Gas Cost** | ✅ $0.0001-0.001 | ✅ Free | ❌ $0.1-1.0 |
| **Censorship Resistant** | ✅ Yes | ❌ No | ✅ Yes |
| **Data Ownership** | ✅ User | ❌ Platform | ✅ User |
| **Privacy** | ⚠️ Pseudonymous | ⚠️ Varies | ⚠️ Pseudonymous |
| **Scalability** | ✅ High | ✅ High | ❌ Limited |

---

## 4. Ứng Dụng Công Nghệ

### A. Blockchain Technology (Sui Network):
- **Move Language**: Smart contracts được viết bằng Move, ngôn ngữ an toàn và hiệu quả
- **Object Model**: Tận dụng object-centric model của Sui cho data management
- **Parallel Execution**: Messages từ khác rooms có thể xử lý song song
- **Events System**: Event emission cho real-time updates

### B. Frontend Technologies:
- **React 18.3**: Modern UI framework với hooks và concurrent features
- **TypeScript**: Type safety cho code quality
- **Vite**: Lightning-fast build tool và HMR
- **TanStack Router**: Type-safe routing với code splitting
- **TanStack Query**: Data fetching và caching optimization

### C. Sui Integration:
- **@mysten/dapp-kit**: Official Sui dApp development kit
- **@mysten/sui**: Sui SDK cho blockchain interactions
- **Wallet Integration**: Hỗ trợ multiple Sui wallets (Sui Wallet, Suiet, Ethos, etc.)

### D. UI/UX Technologies:
- **Radix UI**: Accessible, customizable UI components
- **Tailwind CSS 4**: Utility-first CSS framework
- **Lucide React**: Beautiful icon system
- **React Hook Form + Zod**: Form validation và type safety

### E. Development Tools:
- **Biome**: Fast Rust-based linter và formatter
- **Ultracite**: Zero-config code quality preset
- **Lefthook**: Git hooks cho code quality automation
- **pnpm**: Fast, disk space efficient package manager

---

## 5. Tính Năng Chính

### Hiện tại (MVP):

#### A. User Management:
1. **Create Profile**:
   - Tạo profile với username unique (case-insensitive)
   - Validation: 3-50 characters, không chỉ whitespace
   - Profile ownership trên blockchain

2. **Update Username**:
   - Thay đổi username bất kỳ lúc nào
   - Kiểm tra uniqueness real-time
   - History tracking thông qua events

3. **Profile View**:
   - Hiển thị username, address, created/updated timestamps
   - View profile của users khác

#### B. Room Management:
1. **Create Room**:
   - Tạo chat room với name và description
   - Room name: 1-100 characters
   - Description: tối đa 500 characters
   - Creator tự động join room

2. **List Rooms**:
   - Browse tất cả rooms có sẵn
   - Hiển thị room name, description, creator, member count
   - Real-time updates

3. **Join/Leave Room**:
   - Join room bất kỳ
   - Leave room bất kỳ lúc nào
   - Member count tự động cập nhật

#### C. Messaging:
1. **Send Message**:
   - Gửi text messages (1-2000 characters)
   - Chỉ members mới có thể gửi message
   - Message ownership trên blockchain

2. **View Messages**:
   - Hiển thị messages theo thứ tự chronological
   - Show author username và timestamp
   - Auto-scroll to latest message
   - Real-time refresh (3s interval)

3. **Message List**:
   - Pagination-ready design
   - Efficient loading với event-based queries
   - Author information display

#### D. Security & Validation:
1. **Input Validation**:
   - String validation (không chỉ whitespace)
   - Length constraints
   - Character encoding validation

2. **Authorization Checks**:
   - Profile ownership verification
   - Room membership verification
   - Transaction sender authentication

3. **Error Handling**:
   - Descriptive error codes
   - User-friendly error messages
   - Transaction failure recovery

### Planned Features (Roadmap):

#### Phase 2:
- **Direct Messages (DM)**: 1-to-1 private chat
- **Room Categories**: Organize rooms by topics
- **Room Search**: Search rooms by name/description
- **Member List**: View all members in a room
- **Admin Controls**: Room creator có quyền kick/ban members

#### Phase 3:
- **File Sharing**: Upload images, files (IPFS integration)
- **Reactions**: React to messages with emojis
- **Thread Replies**: Reply to specific messages
- **Notifications**: On-chain notification system
- **Read Receipts**: Track message read status

#### Phase 4:
- **Encryption**: End-to-end encryption for private rooms
- **Voice Messages**: Record và send audio
- **Video Calls**: P2P video chat integration
- **Bot Integration**: Allow bots in rooms for automation
- **Token-gated Rooms**: Rooms requiring NFT/token ownership

#### Phase 5:
- **Mobile App**: React Native app cho iOS/Android
- **Desktop App**: Electron-based desktop application
- **Bridge Integration**: Cross-chain messaging
- **Monetization**: Creator tips, premium features
- **AI Assistant**: AI-powered chat features

---

## 6. Công Nghệ Chính (Chi Tiết)

### A. Move Smart Contract Architecture

#### Contract Structure:
```
chat::chat module
├── Structs (Data Models)
│   ├── ProfileRegistry: Global user directory
│   ├── RoomRegistry: Global room directory
│   ├── MessageRegistry: Message tracking by room
│   ├── RoomMemberRegistry: Membership tracking
│   ├── UserProfile: User identity object
│   ├── Room: Chat room object
│   └── Message: Message object
│
├── Entry Functions (Public API)
│   ├── create_profile()
│   ├── update_username()
│   ├── create_room()
│   ├── join_room()
│   ├── leave_room()
│   └── send_message()
│
├── View Functions (Read-only)
│   ├── get_profile_summary()
│   ├── get_room_summary()
│   ├── get_message_summary()
│   ├── is_member_of_room()
│   ├── get_room_message_count()
│   └── is_username_taken()
│
└── Helper Functions
    ├── is_valid_string()
    └── to_lowercase()
```

#### Data Models Deep Dive:

**1. ProfileRegistry (Shared Object)**:
```move
public struct ProfileRegistry has key, store {
    id: UID,
    profiles: Table<address, ID>,           // address -> profile_id
    usernames: Table<String, address>,      // lowercase_username -> address
}
```
- **Purpose**: Track tất cả users và enforce username uniqueness
- **Design Choice**: Shared object cho phép multiple users create profile song song
- **Uniqueness**: Username lowercase để case-insensitive check

**2. UserProfile (Owned Object)**:
```move
public struct UserProfile has key {
    id: UID,
    owner: address,
    username: String,
    created_at: u64,
    updated_at: u64,
}
```
- **Purpose**: Represent user identity on-chain
- **Ownership**: Owned by user, có thể transfer
- **Timestamp**: Milliseconds từ Unix epoch

**3. RoomRegistry (Shared Object)**:
```move
public struct RoomRegistry has key, store {
    id: UID,
    rooms: Table<ID, bool>,    // room_id -> exists flag
    room_count: u64,            // total rooms
}
```
- **Purpose**: Track all rooms for discovery
- **Scalability**: Bool placeholder để save storage, có thể mở rộng

**4. Room (Shared Object)**:
```move
public struct Room has key, store {
    id: UID,
    name: String,
    description: String,
    creator: address,
    created_at: u64,
    updated_at: u64,
    member_count: u64,
}
```
- **Purpose**: Represent chat room
- **Shared**: Cho phép multiple users interact đồng thời
- **Member Count**: Denormalized để performance, synced với RoomMemberRegistry

**5. MessageRegistry (Shared Object)**:
```move
public struct MessageRegistry has key, store {
    id: UID,
    messages_by_room: Table<ID, Bag>,     // room_id -> Bag<message_id, bool>
    message_counts: Table<ID, u64>,       // room_id -> count
}
```
- **Purpose**: Track messages per room
- **Bag**: Dynamic collection cho flexible message storage
- **Count**: Denormalized cho pagination

**6. Message (Owned Object)**:
```move
public struct Message has key, store {
    id: UID,
    room_id: ID,
    author: address,
    content: String,
    created_at: u64,
}
```
- **Purpose**: Represent single message
- **Ownership**: Owned by author
- **Reference**: room_id link message to room

**7. RoomMemberRegistry (Shared Object)**:
```move
public struct RoomMemberRegistry has key, store {
    id: UID,
    members_by_room: Table<ID, Table<address, bool>>,  // room_id -> members
    member_counts: Table<ID, u64>,                      // room_id -> count
}
```
- **Purpose**: Track room memberships
- **Nested Table**: Efficient membership lookup
- **Count**: Fast member count queries

#### Key Functions Explained:

**create_profile()**:
- Validates username length (3-50 chars)
- Checks string validity (not just whitespace)
- Converts username to lowercase cho uniqueness check
- Creates UserProfile object, transfers to sender
- Updates ProfileRegistry với profile_id và username mapping
- Emits ProfileCreated event

**create_room()**:
- Requires profile existence
- Validates room name và description
- Creates Room as shared object
- Registers room trong RoomRegistry
- Initializes empty member table
- Auto-joins creator vào room
- Emits RoomCreated và UserJoinedRoom events

**send_message()**:
- Validates sender has profile
- Checks room existence
- Verifies sender is room member
- Validates message content (1-2000 chars)
- Creates Message object owned by sender
- Adds message_id to MessageRegistry
- Increments message count
- Emits MessageSent event

**join_room()**:
- Validates profile existence
- Adds user to members table
- Increments member count (Registry + Room)
- Idempotent: safe to call multiple times
- Emits UserJoinedRoom event

**leave_room()**:
- Removes user từ members table
- Decrements member count
- Idempotent: safe to call multiple times
- Emits UserLeftRoom event

### B. Frontend Architecture

#### Component Hierarchy:
```
App (main.tsx)
├── Router Setup (@tanstack/router)
│   ├── __root.tsx (Layout wrapper)
│   ├── index.tsx (Home/Chat page)
│   ├── counter.tsx (Demo page)
│   └── about.tsx (About page)
│
└── ChatApp.tsx (Main chat interface)
    ├── CreateProfile (if no profile)
    ├── ProfileView (if has profile)
    ├── Tabs Navigation
    │   ├── Profile Tab
    │   │   ├── CreateProfile
    │   │   ├── ProfileView
    │   │   └── UpdateUsername
    │   │
    │   ├── Rooms Tab
    │   │   ├── CreateRoom
    │   │   └── RoomList
    │   │
    │   └── Chat Tab
    │       ├── Room Header (name + Leave button)
    │       ├── Join Button (if not member)
    │       ├── MessageList
    │       └── SendMessage (if member)
    │
    └── Custom Hooks
        ├── useChatRegistry
        └── useRoomMembership
```

#### State Management:
- **TanStack Query**: Server state caching và synchronization
  - Query keys cho invalidation
  - Automatic refetch intervals
  - Background refetching
  - Optimistic updates ready

- **React State**: UI state management
  - Selected room tracking
  - Active tab state
  - Refresh triggers
  - Form states

#### Data Flow:

**1. Profile Creation Flow**:
```
User Input → Form Validation → Transaction Building → 
Wallet Signing → Blockchain Execution → Event Emission → 
Query Invalidation → UI Update
```

**2. Message Sending Flow**:
```
Type Message → Validation → Check Membership → 
Sign Transaction → On-chain Execution → Message Object Created → 
MessageSent Event → Query Refresh → UI Update với new message
```

**3. Room Discovery Flow**:
```
Query RoomRegistry → Get all Room Objects → 
Filter & Sort → Display trong RoomList → 
User Select → Set selectedRoomId → Load Messages
```

#### Real-time Updates:
- **Polling Strategy**: 3-second interval refetch cho messages
- **Event Listening**: Subscribe to events cho instant updates (future)
- **Optimistic Updates**: Immediate UI feedback, rollback on error (future)

### C. Blockchain Integration Layer

#### Sui Client Configuration:
```typescript
// Network config với environment-based package IDs
networks: {
  devnet: { ... },
  testnet: { 
    url: getFullnodeUrl('testnet'),
    variables: {
      chatPackageId: TESTNET_CHAT_PACKAGE_ID,
      profileRegistryId: TESTNET_PROFILE_REGISTRY_ID,
      // ... other registries
    }
  },
  mainnet: { ... }
}
```

#### Transaction Building:
```typescript
// Example: Send message transaction
const tx = new Transaction();
tx.moveCall({
  target: `${chatPackageId}::chat::send_message`,
  arguments: [
    tx.object(profileRegistryId),
    tx.object(roomRegistryId),
    tx.object(roomId),
    tx.object(messageRegistryId),
    tx.object(memberRegistryId),
    tx.pure.string(content),
    tx.object('0x6'), // Clock object
  ],
});
```

#### Event Processing:
```typescript
// Query events và extract data
const events = await suiClient.queryEvents({
  query: {
    MoveEventType: `${packageId}::chat::MessageSent`
  }
});

// Process events
events.data.forEach(event => {
  const { message_id, room_id, author } = event.parsedJson;
  // Update UI
});
```

#### Object Queries:
```typescript
// Multi-object batch query
const messagePromises = messageIds.map(id =>
  suiClient.getObject({
    id,
    options: { showContent: true, showOwner: true }
  })
);
const messages = await Promise.all(messagePromises);
```

### D. Security Measures

#### Smart Contract Level:
1. **Access Control**:
   - Owner verification cho profile updates
   - Membership verification cho messaging
   - Registry integrity checks

2. **Input Validation**:
   - Length constraints enforcement
   - String validity checks
   - Numeric overflow protection

3. **State Consistency**:
   - Atomic operations
   - Count synchronization checks
   - Idempotent operations

#### Frontend Level:
1. **Input Sanitization**:
   - HTML escape user input
   - Length validation before submission
   - Type validation với Zod schemas

2. **Transaction Safety**:
   - Dry-run before execution
   - Gas estimation
   - Error handling và user feedback

3. **Data Validation**:
   - Response type checking
   - Null/undefined guards
   - TypeScript strict mode

### E. Performance Optimizations

#### Smart Contract:
- **Parallel Execution**: Độc lập operations có thể execute song song
- **Event-Driven**: Emit events thay vì store redundant data
- **Shared Objects**: Multiple users interact không conflict
- **Table/Bag**: O(1) lookups thay vì vector iterations

#### Frontend:
- **Code Splitting**: Route-based chunking
- **Lazy Loading**: Components load on demand
- **Query Caching**: TanStack Query cache strategy
- **Debouncing**: Search inputs debounced
- **Virtual Scrolling**: (Planned) cho long message lists

#### Network:
- **Batch Queries**: Multiple objects queried cùng lúc
- **Query Deduplication**: TanStack Query prevents duplicate requests
- **Prefetching**: Prefetch likely-needed data
- **Background Refetch**: Stale-while-revalidate pattern

---

## 7. Mô Hình

### A. System Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                         USER LAYER                          │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │ Browser  │  │ Mobile   │  │ Desktop  │  │  Wallet  │   │
│  │   App    │  │   App    │  │   App    │  │Extension │   │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘   │
└───────┼─────────────┼─────────────┼─────────────┼──────────┘
        │             │             │             │
        └─────────────┴─────────────┴─────────────┘
                      │
┌─────────────────────┼─────────────────────────────────────┐
│                FRONTEND LAYER                             │
│     ┌───────────────▼─────────────────┐                   │
│     │   React Application (Vite)      │                   │
│     ├─────────────────────────────────┤                   │
│     │  - TanStack Router              │                   │
│     │  - TanStack Query (Cache)       │                   │
│     │  - Radix UI Components          │                   │
│     │  - Form Validation (Zod)        │                   │
│     └───────────────┬─────────────────┘                   │
│                     │                                      │
│     ┌───────────────▼─────────────────┐                   │
│     │  @mysten/dapp-kit Integration   │                   │
│     ├─────────────────────────────────┤                   │
│     │  - Wallet Connection            │                   │
│     │  - Transaction Builder          │                   │
│     │  - Query Hooks                  │                   │
│     └───────────────┬─────────────────┘                   │
└─────────────────────┼─────────────────────────────────────┘
                      │
┌─────────────────────┼─────────────────────────────────────┐
│              SUI BLOCKCHAIN LAYER                         │
│     ┌───────────────▼─────────────────┐                   │
│     │    Sui Full Node (RPC)          │                   │
│     ├─────────────────────────────────┤                   │
│     │  - JSON-RPC API                 │                   │
│     │  - WebSocket (Events)           │                   │
│     │  - Object Queries               │                   │
│     │  - Transaction Execution        │                   │
│     └───────────────┬─────────────────┘                   │
│                     │                                      │
│     ┌───────────────▼─────────────────┐                   │
│     │    Move Smart Contracts         │                   │
│     │      (chat::chat module)        │                   │
│     ├─────────────────────────────────┤                   │
│     │  Shared Objects:                │                   │
│     │  ├─ ProfileRegistry             │                   │
│     │  ├─ RoomRegistry                │                   │
│     │  ├─ MessageRegistry             │                   │
│     │  ├─ RoomMemberRegistry          │                   │
│     │  └─ Room Objects                │                   │
│     │                                 │                   │
│     │  Owned Objects:                 │                   │
│     │  ├─ UserProfile                 │                   │
│     │  └─ Message                     │                   │
│     └───────────────┬─────────────────┘                   │
│                     │                                      │
│     ┌───────────────▼─────────────────┐                   │
│     │    Sui Storage Layer            │                   │
│     ├─────────────────────────────────┤                   │
│     │  - Object Store                 │                   │
│     │  - Event Store                  │                   │
│     │  - Transaction History          │                   │
│     └─────────────────────────────────┘                   │
└───────────────────────────────────────────────────────────┘
```

### B. Data Flow Model

#### 1. Profile Creation Flow
```
┌─────────┐    1. Input    ┌─────────────┐
│  User   │───────────────>│CreateProfile│
│Interface│                │  Component  │
└─────────┘                └──────┬──────┘
                                  │ 2. Validate
                                  ▼
                           ┌─────────────┐
                           │Form Handler │
                           │   (Zod)     │
                           └──────┬──────┘
                                  │ 3. Build TX
                                  ▼
                           ┌─────────────┐
                           │Transaction  │
                           │   Builder   │
                           └──────┬──────┘
                                  │ 4. Sign
                                  ▼
                           ┌─────────────┐
                           │   Wallet    │
                           └──────┬──────┘
                                  │ 5. Execute
                                  ▼
                    ┌──────────────────────────┐
                    │  Sui Blockchain          │
                    │  create_profile()        │
                    ├──────────────────────────┤
                    │ 1. Validate username     │
                    │ 2. Check uniqueness      │
                    │ 3. Create UserProfile    │
                    │ 4. Update Registry       │
                    │ 5. Emit Event            │
                    └──────────┬───────────────┘
                               │ 6. Events
                               ▼
                    ┌────────────────────┐
                    │  Frontend Query    │
                    │    Refetch         │
                    └──────────┬─────────┘
                               │ 7. Display
                               ▼
                    ┌────────────────────┐
                    │   Updated UI       │
                    │ (Profile View)     │
                    └────────────────────┘
```

#### 2. Messaging Flow
```
User Types Message
       │
       ▼
[Content Validation]
       │
       ▼
[Check Room Membership] ◄──── Query RoomMemberRegistry
       │
       ▼
[Build send_message TX]
       │
       ├─── profileRegistryId
       ├─── roomRegistryId
       ├─── roomId
       ├─── messageRegistryId
       ├─── memberRegistryId
       ├─── content
       └─── clock
       │
       ▼
[Wallet Signs TX]
       │
       ▼
[Blockchain Executes]
       │
       ├─► Create Message Object (owned by sender)
       ├─► Add to MessageRegistry
       ├─► Increment message count
       └─► Emit MessageSent event
       │
       ▼
[Event Captured]
       │
       ▼
[Query Invalidation]
       │
       ▼
[Refetch Messages]
       │
       ▼
[UI Updates with New Message]
```

### C. Object Relationship Model

```
                    ┌────────────────────┐
                    │  ProfileRegistry   │
                    │   (Shared Object)  │
                    ├────────────────────┤
                    │ profiles: Table    │
                    │ usernames: Table   │
                    └──────────┬─────────┘
                               │ 1:N
                               │ maps to
                               ▼
                    ┌────────────────────┐
                    │   UserProfile      │
                    │  (Owned Object)    │
                    ├────────────────────┤
                    │ id: UID            │
                    │ owner: address     │
                    │ username: String   │
                    │ created_at: u64    │
                    └────────────────────┘
                               │
                               │ N:M
                               │ (via RoomMemberRegistry)
                               │
┌────────────────────┐         │         ┌────────────────────┐
│   RoomRegistry     │         │         │RoomMemberRegistry  │
│  (Shared Object)   │         │         │  (Shared Object)   │
├────────────────────┤         │         ├────────────────────┤
│ rooms: Table       │         │         │ members_by_room    │
│ room_count: u64    │         │         │ member_counts      │
└────────┬───────────┘         │         └─────────┬──────────┘
         │ 1:N                 │                   │
         │ tracks              │                   │ tracks
         ▼                     │                   │ membership
┌────────────────────┐         │                   │
│      Room          │◄────────┴───────────────────┘
│ (Shared Object)    │
├────────────────────┤
│ id: UID            │
│ name: String       │
│ description: String│
│ creator: address   │
│ member_count: u64  │
└────────┬───────────┘
         │ 1:N
         │ contains
         │
         ▼
┌────────────────────┐         ┌────────────────────┐
│ MessageRegistry    │         │     Message        │
│  (Shared Object)   │         │  (Owned Object)    │
├────────────────────┤         ├────────────────────┤
│ messages_by_room   │◄────────│ id: UID            │
│ message_counts     │  tracks │ room_id: ID        │
└────────────────────┘         │ author: address    │
                               │ content: String    │
                               │ created_at: u64    │
                               └────────────────────┘
```

### D. Component Interaction Model

```
                    ┌──────────────────┐
                    │    ChatApp       │
                    │  (Main Container)│
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
    ┌─────────────┐  ┌─────────────┐  ┌─────────────┐
    │Profile Tab  │  │ Rooms Tab   │  │  Chat Tab   │
    └──────┬──────┘  └──────┬──────┘  └──────┬──────┘
           │                │                 │
           │                │                 │
    ┌──────▼──────┐  ┌──────▼──────┐   ┌─────▼──────┐
    │CreateProfile│  │ CreateRoom  │   │ MessageList│
    └─────────────┘  └─────────────┘   └─────┬──────┘
           │                │                 │
    ┌──────▼──────┐  ┌──────▼──────┐   ┌─────▼──────┐
    │ProfileView  │  │  RoomList   │   │SendMessage │
    └─────────────┘  └──────┬──────┘   └────────────┘
           │                │                 │
    ┌──────▼──────┐         │           ┌─────▼──────┐
    │UpdateUsername│        │           │ JoinRoom   │
    └─────────────┘         │           └────────────┘
                            │                 │
                            │           ┌─────▼──────┐
                            │           │ LeaveRoom  │
                            │           └────────────┘
                            │
              ┌─────────────┴─────────────┐
              │                           │
        ┌─────▼──────┐            ┌───────▼────────┐
        │useChatRegistry│          │useRoomMembership│
        │   (Hook)    │            │     (Hook)      │
        └─────────────┘            └─────────────────┘
              │                           │
              └───────────┬───────────────┘
                          │
                   ┌──────▼──────┐
                   │ @mysten/    │
                   │ dapp-kit    │
                   └──────┬──────┘
                          │
                   ┌──────▼──────┐
                   │Sui Blockchain│
                   └─────────────┘
```

### E. Deployment Model

```
┌─────────────────────────────────────────────────────────┐
│                    DEVELOPMENT                          │
├─────────────────────────────────────────────────────────┤
│  Developer Machine                                      │
│  ├─ Source Code (Git)                                   │
│  ├─ Local Sui CLI                                       │
│  ├─ Local Node (optional)                               │
│  └─ Development Server (Vite)                           │
└──────────────────┬──────────────────────────────────────┘
                   │
                   │ git push
                   ▼
┌─────────────────────────────────────────────────────────┐
│                   BUILD & TEST                          │
├─────────────────────────────────────────────────────────┤
│  CI/CD Pipeline (GitHub Actions)                        │
│  ├─ Code Quality (Biome)                                │
│  ├─ Type Checking (TypeScript)                          │
│  ├─ Build (Vite)                                        │
│  ├─ Unit Tests                                          │
│  └─ Smart Contract Tests                                │
└──────────────────┬──────────────────────────────────────┘
                   │
                   │ on success
                   ▼
┌─────────────────────────────────────────────────────────┐
│              SMART CONTRACT DEPLOYMENT                  │
├─────────────────────────────────────────────────────────┤
│  Sui Testnet/Mainnet                                    │
│  ├─ sui client publish                                  │
│  ├─ Get Package ID                                      │
│  ├─ Shared Objects created:                             │
│  │   ├─ ProfileRegistry                                 │
│  │   ├─ RoomRegistry                                    │
│  │   ├─ MessageRegistry                                 │
│  │   └─ RoomMemberRegistry                              │
│  └─ Update .env with IDs                                │
└──────────────────┬──────────────────────────────────────┘
                   │
                   │ configure
                   ▼
┌─────────────────────────────────────────────────────────┐
│              FRONTEND DEPLOYMENT                        │
├─────────────────────────────────────────────────────────┤
│  Hosting Platform (Vercel/Netlify/IPFS)                 │
│  ├─ Build Production Bundle                             │
│  ├─ Environment Variables:                              │
│  │   ├─ VITE_TESTNET_CHAT_PACKAGE_ID                    │
│  │   ├─ VITE_TESTNET_PROFILE_REGISTRY_ID                │
│  │   └─ ... other registry IDs                          │
│  ├─ Deploy Static Assets                                │
│  └─ CDN Distribution                                    │
└──────────────────┬──────────────────────────────────────┘
                   │
                   │ access via
                   ▼
┌─────────────────────────────────────────────────────────┐
│                 PRODUCTION                              │
├─────────────────────────────────────────────────────────┤
│  Users Access Via:                                      │
│  ├─ Web Browser (https://app.example.com)               │
│  ├─ IPFS Gateway (decentralized hosting)                │
│  └─ Local Build (self-hosted)                           │
│                                                         │
│  Connects To:                                           │
│  ├─ Sui Mainnet RPC (fullnode.mainnet.sui.io)          │
│  └─ Deployed Smart Contracts                            │
└─────────────────────────────────────────────────────────┘
```

### F. Security Model

```
┌─────────────────────────────────────────────────────────┐
│                    SECURITY LAYERS                      │
└─────────────────────────────────────────────────────────┘

Layer 1: Smart Contract Security
├─ Access Control
│  ├─ Owner-only operations (update_username)
│  ├─ Member-only operations (send_message)
│  └─ Registry integrity checks
│
├─ Input Validation
│  ├─ Length constraints (MIN/MAX constants)
│  ├─ String validation (is_valid_string)
│  ├─ Type safety (Move's type system)
│  └─ Overflow protection (u64 checks)
│
├─ State Consistency
│  ├─ Atomic operations
│  ├─ Count synchronization (member_count)
│  ├─ Idempotent functions (join/leave)
│  └─ Assert-based guards
│
└─ Audit Trail
   ├─ All actions emit events
   ├─ Immutable transaction history
   └─ On-chain timestamp records

Layer 2: Blockchain Security
├─ Sui Consensus
│  ├─ Byzantine Fault Tolerance
│  ├─ Validator network
│  └─ Fast finality
│
├─ Cryptography
│  ├─ Ed25519 signatures
│  ├─ Object ownership proofs
│  └─ Transaction authenticity
│
└─ Network Security
   ├─ DDoS protection
   ├─ Rate limiting
   └─ Node redundancy

Layer 3: Frontend Security
├─ Input Sanitization
│  ├─ XSS prevention (React auto-escaping)
│  ├─ Form validation (Zod schemas)
│  └─ Type checking (TypeScript)
│
├─ Transaction Safety
│  ├─ User confirmation dialogs
│  ├─ Gas estimation display
│  ├─ Error handling
│  └─ Rollback on failure
│
└─ Wallet Security
   ├─ Private key in wallet only
   ├─ Transaction signing in wallet
   └─ No private key exposure

Layer 4: Infrastructure Security
├─ HTTPS/TLS encryption
├─ Environment variable protection
├─ Dependency security scanning
└─ Regular security updates
```

---

## Tổng Kết

**Sui Messenger** là một dự án đột phá trong việc ứng dụng blockchain Sui vào mục đích giao tiếp hàng ngày. Với kiến trúc object-centric độc đáo, smart contracts được tối ưu hóa, và frontend hiện đại, dự án này không chỉ chứng minh khả năng kỹ thuật của Sui mà còn mở ra hướng đi mới cho các ứng dụng phi tập trung.

### Điểm Mạnh:
✅ **Decentralized**: Hoàn toàn phi tập trung, không phụ thuộc máy chủ  
✅ **Fast**: Sub-second transaction finality  
✅ **Cheap**: Gas fees cực thấp cho messaging  
✅ **Scalable**: Parallel execution, efficient data structures  
✅ **Developer-Friendly**: Clean code, comprehensive documentation  
✅ **Open Source**: Minh bạch, có thể audit  

### Roadmap:
🚀 **Phase 2**: DMs, Room categories, Admin controls  
🚀 **Phase 3**: File sharing, Reactions, Threads  
🚀 **Phase 4**: E2E encryption, Voice/Video  
🚀 **Phase 5**: Mobile apps, Cross-chain, AI features  

### Links:
- **Repository**: [GitHub repo URL]
- **Live Demo**: [Deployment URL]
- **Smart Contract**: [Sui Explorer package link]
- **Documentation**: [Docs URL]

---

**Built with ❤️ on Sui Blockchain**

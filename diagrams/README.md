# PlantUML Diagrams - Sui Messenger

Thư mục này chứa tất cả các sơ đồ kiến trúc của dự án Sui Messenger được vẽ bằng PlantUML.

## Yêu Cầu

- **VS Code Extension**: [PlantUML by jebbs](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml)
- **Graphviz** (optional, cho local rendering): [Download Graphviz](https://graphviz.org/download/)

## Cài Đặt Extension

```bash
# Trong VS Code, mở Command Palette (Ctrl+Shift+P hoặc Cmd+Shift+P)
# Gõ: "Extensions: Install Extensions"
# Tìm kiếm: "PlantUML"
# Cài đặt extension của "jebbs"
```

## Cách Xem Diagrams

### 1. Preview trong VS Code

1. Mở bất kỳ file `.puml` trong thư mục này
2. Nhấn `Alt+D` (Windows/Linux) hoặc `Option+D` (Mac)
3. Hoặc click chuột phải và chọn **"PlantUML: Preview Current Diagram"**

### 2. Export sang PNG/SVG

1. Mở file `.puml`
2. Nhấn `Ctrl+Shift+P` (hoặc `Cmd+Shift+P` trên Mac)
3. Gõ: "PlantUML: Export Current Diagram"
4. Chọn format (PNG, SVG, PDF, etc.)

## Danh Sách Diagrams

### 1. System Architecture (`system-architecture.puml`)
**Mô tả**: Kiến trúc tổng thể của hệ thống
- User Layer: Browser, Mobile, Desktop apps
- Frontend Layer: React + dApp-kit
- Blockchain Layer: Sui network + Smart contracts
- Storage Layer: Object và Event storage

**Loại**: Component Diagram

---

### 2. Profile Creation Flow (`profile-creation-flow.puml`)
**Mô tả**: Luồng xử lý khi user tạo profile mới
- Input validation
- Transaction building
- Wallet signing
- Blockchain execution
- UI update

**Loại**: Sequence Diagram

---

### 3. Messaging Flow (`messaging-flow.puml`)
**Mô tả**: Luồng xử lý khi user gửi message
- Content validation
- Membership verification
- Transaction execution
- Message object creation
- Event emission và UI refresh

**Loại**: Sequence Diagram

---

### 4. Object Relationship (`object-relationship.puml`)
**Mô tả**: Mối quan hệ giữa các Move objects
- ProfileRegistry ↔ UserProfile (1:N)
- RoomRegistry ↔ Room (1:N)
- Room ↔ Message (1:N)
- RoomMemberRegistry ↔ Room ↔ UserProfile (N:M)

**Loại**: Class Diagram

---

### 5. Component Interaction (`component-interaction.puml`)
**Mô tả**: Tương tác giữa các React components
- ChatApp (main container)
- Tab components (Profile, Rooms, Chat)
- Feature components (CreateProfile, RoomList, MessageList, etc.)
- Custom hooks (useChatRegistry, useRoomMembership)
- Integration với @mysten/dapp-kit

**Loại**: Component Diagram

---

### 6. Deployment Model (`deployment.puml`)
**Mô tả**: Quy trình deployment từ development đến production
- Development: Local dev environment
- Build & Test: CI/CD pipeline
- Smart Contract Deployment: Sui network
- Frontend Deployment: Vercel/Netlify/IPFS
- Production: User access points

**Loại**: Deployment Diagram

---

### 7. Security Model (`security-model.puml`)
**Mô tả**: Các lớp bảo mật trong hệ thống
- Layer 1: Smart Contract Security
- Layer 2: Blockchain Security
- Layer 3: Frontend Security
- Layer 4: Infrastructure Security

**Loại**: Package Diagram

---

## Tips

### Zoom In/Out trong Preview
- `Ctrl + Mouse Wheel` (Windows/Linux)
- `Cmd + Mouse Wheel` (Mac)

### Auto-refresh Preview
Extension tự động refresh khi bạn save file `.puml`

### Custom Styling
Các diagram đã được style với:
- `skinparam` để tùy chỉnh màu sắc
- `<<stereotype>>` để phân loại components
- `note` để thêm giải thích

### Export Quality
Để export quality cao:
1. Preferences → Settings
2. Tìm "PlantUML"
3. Set "Export Format" → SVG (vector, scalable)

## Online Viewer (Alternative)

Nếu không muốn cài extension, copy nội dung file `.puml` và paste vào:
- **PlantUML Online**: http://www.plantuml.com/plantuml/uml/
- **PlantText**: https://www.planttext.com/

## Tài Liệu Tham Khảo

- [PlantUML Official Documentation](https://plantuml.com/)
- [PlantUML Sequence Diagram](https://plantuml.com/sequence-diagram)
- [PlantUML Class Diagram](https://plantuml.com/class-diagram)
- [PlantUML Component Diagram](https://plantuml.com/component-diagram)
- [PlantUML Deployment Diagram](https://plantuml.com/deployment-diagram)

---

**Note**: Các diagram này được tham chiếu trong file `PROJECT_OVERVIEW.md` ở mục 7 (Mô Hình).

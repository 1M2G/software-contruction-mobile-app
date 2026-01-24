# Behind-the-App
Software Construction assignment on identifying what is behind a software application using **WHATSAPP** as our case study.

**Group Members**
| Name | Reg Number | Role |
|------|-----|------|
| Abaho Joy | *M23B23/001* | Coordinator  |
| Anguyi Netwon | *S23B23/071*  | App Analyst |
|Bachawa Wangolo|*M23B23/042*| Risk & Change Analyst |
|Mucunguzi Godfrey|*M23B23/025*| Systems Thinker |
|Opi Timothy| *S23B23/086*  | Documentation Lead |

## Part A: Understanding the App.

**What problem does the app solve?**
<br> Before WhatsApp, communication, especially international and long-distance, relied heavily on SMS and traditional phone calls, which were often expensive and unreliable. WhatsApp was developed to address this problem by enabling real-time messaging and calling over the internet. This allows users to communicate instantly, securely, and at a low cost, regardless of their geographic location.

**Who are its primary users?**
<br>WhatsApp serves a wide range of users, including:
1. Students and young people for everyday communication.

2. Families and friends staying connected across long distances.

3. Small and medium-sized businesses communicating with customers and promoting products.

4. Community and social groups coordinating activities and sharing information.

**2. Core Features**
<br>The key features of WhatsApp include:

- **User Authentication & Login:**
Account creation and login using verified phone numbers.

- **Messaging:**
Sending and receiving text messages, images, videos, and voice notes.

- **Voice and Video Calls:**
One-to-one and group calls over the internet.

- **Group Chats:**
Communication among multiple users within a single conversation.

- **Document Sharing:**
Sending files such as PDFs, Word documents, and other supported formats.

- **Notifications:**
Real-time alerts for new messages, calls, and app updates.


## Part B: Thinking Behind the Scenes.
For each of the above features, the following software components are likely involved:

**1. User Authentication & Login.**
- **UI:** Phone number input screens, OTP verification screens.
- **Business Logic:** Account validation, session management.
- **Network / APIs:** OTP verification servers, authentication APIs.
- **Data Storage:** User profiles and authentication tokens.
- **Internet Required:** Yes.
- **If Network Is Slow/Unavailable:** Login delays or failure to verify account.

  **2. Messaging**
- **UI:** Chat screens, emoji keyboard, media preview
- **Business Logic:** Message formatting, encryption, delivery status (sent, delivered, read)
- **Network / APIs:** Messaging servers, message routing services
- **Data Storage:** Local message cache and cloud backups
- **Internet Required:** Yes (limited offline drafting possible)
- **If Network Is Slow/Unavailable:** Messages are queued and sent later

**3. Voice and Video Calls**
- **UI:** Call screens, mute/video controls
- **Business Logic:** Call setup, audio/video stream handling
- **Network / APIs:** Real‑time communication servers (VoIP)
- **Data Storage:** Minimal (call logs)
- **Internet Required:** Yes (strong connection needed)
- **If Network Is Slow/Unavailable:** Poor call quality, dropped calls

**4. Group Chats**
- **UI:** Group chat screens, participant lists
- **Business Logic:** Group membership, admin roles, message broadcasting
- **Network / APIs:** Group message synchronization servers
- **Data Storage:** Group metadata and message history
- **Internet Required:** Yes
- **If Network Is Slow/Unavailable:** Delayed message delivery to group members

**5. Document Sharing**
- **UI:** File picker, download previews
- **Business Logic:** File validation, size limits
- **Network / APIs:** File upload/download servers
- **Data Storage:** Cloud storage and local device storage
- **Internet Required:** Yes
- **If Network Is Slow/Unavailable:** Upload/download failures or delays

**6. Notifications**
- **UI:** Push notifications on device
- **Business Logic:** Notification triggers and priority handling
- **Network / APIs:** Push notification services
- **Data Storage:** Notification preferences
- **Internet Required:** Yes
- **If Network Is Slow/Unavailable:** Delayed or missing notifications

## Part C: Change and Maintainability.

**Selected Change Scenario:** Add Offline Support.

**Which parts of the app would need changes?**
- Messaging system (local storage and synchronization logic).
- Data storage layer (caching messages and media offline).
- Network handling logic (syncing data when the connection is restored).
  
**What existing features could break?**
- Message ordering and delivery status.
- Media uploads and downloads.
- Group chat synchronization.
  
**Why would this change be difficult to implement?**

Offline support introduces complexity in data consistency, conflict resolution, and synchronization across multiple devices. Ensuring messages remain secure and correctly ordered after reconnecting is technically challenging.


## Part D: Software Construction Challenges.

- **Performance and Scalability** – Supporting millions of concurrent users worldwide.
- **Security and Data Privacy** – Maintaining end‑to‑end encryption and user trust.
- **Reliability Under Poor Networks** – Handling unstable or slow internet connections.
- **Testing Across Devices and OS Versions** – Ensuring consistent behavior on many devices.
- **Maintainability and Feature Evolution** – Adding new features without breaking existing ones.


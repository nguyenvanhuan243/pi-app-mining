# BNW Mining Functional Specification Document

## 1. Project Overview

**BNW Mining** is a mobile application inspired by the Pi Network, designed to simulate cryptocurrency mining and user engagement for the BNW blockchain (an EVM-compatible chain with Chain ID: 714). The app allows users to check in daily to earn BNW tokens, grow their mining rate through referrals, and eventually withdraw mined tokens to their Web3 wallets.

---

## 2. Features Overview

* Daily mining session simulation
* KYC verification (email or phone)
* Multi-tier referral system
* Mining rate booster through team activity
* BNW token integration (off-chain & on-chain support)
* Web3 wallet binding
* Push notifications for session reminders
* Admin panel to monitor users and reward distribution
* Side navigation menu for quick access to features
* Multi-language support (including English, Vietnamese, and more)

---

## 3. User Journey & App Pages

### 3.1 Onboarding

* Splash screen
* Intro slider (Welcome to BNW Mining, How it works, Benefits)
* Signup/Login: Email, Phone (OTP), or Web3 wallet
* Referral code entry (must be entered at signup only)
* Language selection during first launch and accessible in profile settings

### 3.2 Dashboard

* Daily mining button: "Start Mining"
* Countdown timer for current session
* Total mined BNW
* Mining rate details
* Referral count & bonuses
* Invite button (share QR code or link)

### 3.3 Profile Page

* User details (username, email/phone)
* KYC status
* Wallet address (BNW EVM-compatible)
* Notification toggle
* Language selector
* Logout button

### 3.4 Team Page

* List of direct referrals
* Status: active/inactive
* Referral mining contribution

### 3.5 Withdraw Page

* Display available balance
* Bind/Update wallet address
* "Withdraw BNW" button
* Transaction history (off-chain & on-chain)

### 3.6 Side Navigation Menu (based on Pi Network app)

* Home
* Mainnet
* BNW Browser (like Pi Browser)
* BNW Utilities
* Mine BNW
* Referral Team
* Roles
* Chat
* Node
* FAQ
* White Paper
* Support Portal
* Core Team
* Profile
* Social Media links: Facebook, Instagram, YouTube, X, Telegram

---

## 4. Mining Logic

### 4.1 Mining Session

* Session duration: 24 hours
* Reward calculated at end of session
* Must press "Start Mining" each session to earn

### 4.2 Reward Formula

```
reward = base_rate * activity_bonus * referral_multiplier
```

* `base_rate`: 1 BNW/hour
* `activity_bonus`: +10% per daily login streak (max 50%)
* `referral_multiplier`: +25% per active referral (max 10 referrals)

### 4.3 Referral System

🧑‍🤝‍🧑 **How It Works**

**Joining BNW Mining:**

* When a user joins BNW Mining, they must use an invitation code (referral code).
* This creates a connection between the referrer and the new user.

**Earning Bonus BNW:**

* Both the referrer and the referred user earn a bonus mining rate (extra BNW per hour).
* The more people you invite, the higher your mining rate can be.

**Security Circle (Optional Future Feature):**

* After mining for a few days, users can start adding trusted members to a "security circle".
* People you referred can be added to this circle, which could be used to secure the blockchain in the future.

**No MLM or Ponzi:**

* This is not a pyramid scheme.
* You only earn from your **direct referrals**, and they must be **active miners** for you to benefit.
* You **do not earn** from the people your referrals invite.

**Referral Code Use:**

* Referral code must be used at signup only and cannot be changed later.

---

## 5. Backend & Database

* User authentication (Firebase Auth / custom JWT)
* Store:

  * User info (email, phone, KYC)
  * Mining session logs
  * Referral links and tree
  * Wallet addresses
  * Reward balances (off-chain)
  * User-selected language preferences
* Cron jobs to calculate and allocate mining rewards

---

## 6. Smart Contracts

### 6.1 Chain Information

* **Chain Name**: BNW
* **Chain ID**: 714
* **RPC**: [http://174.138.18.77:8545](http://174.138.18.77:8545)
* **Token Symbol**: BNW
* **Explorer**: [https://bnwscan.fiotech.org](https://bnwscan.fiotech.org)

### 6.2 Token Contract

* ERC20 standard BNW token
* Optional lockup feature for claiming

### 6.3 Claim Contract

* Withdraw off-chain mined tokens to wallet
* One-time claim per session
* Admin-approved or automatic claim validation

---

## 7. Admin Panel

* View all users
* Search by email/phone
* View mining logs
* KYC status filter
* Approve/deny withdrawals
* Adjust mining rate or bonuses manually (if needed)
* View language statistics (preferred languages)

---

## 8. Notifications

* Daily push reminder: "Your mining session is ready!"
* Withdrawal confirmation
* Referral success alert
* All notifications should support multi-language display based on user settings

---

## 9. Tech Stack

* **Frontend**: React Native with i18n library for multi-language support
* **Backend**: Node.js + MongoDB or Firebase
* **Smart Contracts**: Solidity (BNW Chain)
* **Web3 Integration**: ethers.js
* **Push Notifications**: Firebase Cloud Messaging (FCM)
* **Authentication**: Firebase / custom backend auth

---

## 10. Milestones

1. UI/UX Design (Figma)
2. Frontend Mobile App
3. Backend + Admin Panel
4. Smart Contract Deployment
5. Testing (Unit, Integration, User)
6. Mainnet Launch

---

## 11. Optional Enhancements

* NFT badges for achievements
* Leaderboard by mining score
* Invite campaigns (bonus BNW)
* In-app chat for teams
* Educational gamification

---

## 12. Final Notes

This app is **not a real mining app** but simulates the behavior of mining to grow the BNW token community. All interactions should feel fun, engaging, and user-friendly while offering real BNW tokens as future utility.

---

**End of BNW\_Mining\_Functional\_Spec.md**

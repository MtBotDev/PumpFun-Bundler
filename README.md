

# 🚀 **PumpFun Bundler** 🛠️

## 📋 **Overview**

The **PumpFun Bundler** allows you to bundle **buy** operations with **16 different wallets** in one go on the **Solana blockchain**. Efficient, fast, and designed for high-volume transactions, this tool simplifies your trading experience! 🌟

---

## 📥 **Installation**

To get started with the **PumpFun Bundler**, run the following command to install the **PumpDotFun SDK**:

```bash
npm i pumpdotfun-sdk
```

---

## 🔑 **Setup**

1. **Create `.env` file:**  
   Set your **RPC URL** as per the `.env.example` file. Ensure it's pointing to the correct Solana network.

2. **Fund Your Account:**  
   Fund an account with at least **0.004 SOL**. This will be automatically generated when you run the command below:

```bash
npx ts-node example/basic/index.ts
```

Once set up, you're ready to start bundling!

---

## 🔄 **Usage Example**

Here's an example of how to use the PumpFun Bundler for buying and selling tokens.

### 🛒 **Buy Tokens**

```typescript
async buy(
  buyers: Keypair[], 
  mint: PublicKey, 
  buyAmountSol: bigint, 
  slippageBasisPoints: bigint = 500n, 
  priorityFees?: PriorityFee, 
  commitment: Commitment = DEFAULT_COMMITMENT, 
  finality: Finality = DEFAULT_FINALITY
): Promise<TransactionResult>
```

- **Description:**  
  Buys a specified amount of tokens from the **mint** using **SOL**.
  
- **Parameters:**  
  - `buyers`: Array of buyer keypairs. 👥
  - `mint`: The **public key** of the mint account. 🔑
  - `buyAmountSol`: The amount of **SOL** to use for buying. 💸
  - `slippageBasisPoints`: Slippage in basis points (default: **500**). ⚖️
  - `priorityFees`: Optional **priority fees**. 💎
  - `commitment`: Level of **commitment** (default: **DEFAULT_COMMITMENT**). 🏁
  - `finality`: Level of **finality** (default: **DEFAULT_FINALITY**). ⏳
  
- **Returns:**  
  A promise that resolves to a `TransactionResult` with the result of the transaction. 📝

---

### 💰 **Sell Tokens**

```typescript
async sell(
  seller: Keypair, 
  mint: PublicKey, 
  sellTokenAmount: bigint, 
  slippageBasisPoints: bigint = 500n, 
  priorityFees?: PriorityFee, 
  commitment: Commitment = DEFAULT_COMMITMENT, 
  finality: Finality = DEFAULT_FINALITY
): Promise<TransactionResult>
```

- **Description:**  
  Sells a specified amount of **tokens** and returns the transaction result.
  
- **Parameters:**  
  - `seller`: The **keypair** of the seller. 🔑
  - `mint`: The **public key** of the mint account. 🏛️
  - `sellTokenAmount`: The amount of **tokens** to sell. 💱
  - `slippageBasisPoints`: Slippage in basis points (default: **500**). ⚖️
  - `priorityFees`: Optional **priority fees**. 💎
  - `commitment`: Level of **commitment** (default: **DEFAULT_COMMITMENT**). 🏁
  - `finality`: Level of **finality** (default: **DEFAULT_FINALITY**). ⏳

- **Returns:**  
  A promise that resolves to a `TransactionResult` with the result of the sale. 📝

---

### 🎧 **Add Event Listener**

```typescript
addEventListener<T extends PumpFunEventType>(
  eventType: T, 
  callback: (event: PumpFunEventHandlers[T], slot: number, signature: string) => void
): number
```

- **Description:**  
  Adds an event listener for specific **PumpFun events**.
  
- **Parameters:**  
  - `eventType`: The **type of event** to listen for (e.g., mint, sell, etc.). 📡
  - `callback`: The **callback function** to execute when the event occurs. 🔄

- **Returns:**  
  The **event listener identifier**. 🎫

---

### 🚫 **Remove Event Listener**

```typescript
removeEventListener(eventId: number): void
```

- **Description:**  
  Removes an **event listener** using its **identifier**.

- **Parameters:**  
  - `eventId`: The **identifier** of the event listener to remove. 🔑

---

## 🎬 **Running the Examples**

To run the examples:

1. Clone the repository or navigate to the **example directory**.
2. Execute the **example script** using `npx ts-node example/basic/index.ts`.
3. Check the **transaction link** in the example output:

[Example Transaction Link](https://explorer.jito.wtf/bundle/96cd7b315354afeed1b2610a709b71657e52f2126122d860d4df8da9f675357d) 🌍

---

## 🤝 **Contributing**

We ❤️ contributions! If you have suggestions or improvements, feel free to:

- Submit a **pull request** 📤
- Open an **issue** to discuss changes or bugs 🐞

Let's build together! 💪

---

## 📝 **License**

This project is licensed under the **MIT License**. For more details, check the [LICENSE](LICENSE) file.

---

## 📞 **Contact & Support**

For any issues or questions, reach out on:

- **Twitter**: [@g0drlc](https://twitter.com/g0drlc) 🦸‍♂️

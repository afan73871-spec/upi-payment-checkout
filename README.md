# UPI Payment Checkout Web Page (₹1.00 Bypass Gateway)

A mobile-responsive, production-ready UPI payment checkout web application designed to bypass common mobile browser UPI link errors (*"Payments to this merchant are not available through this link"*) using dynamic QR generation, silent canvas QR decoding (`jsQR`), and app-specific deep linking.

## 🚀 Key Features

* **Dynamic UPI QR Generation:** Generates high-density vector QR code using `qrcode.js` pre-configured for ₹1.00 (`am=1.00`).
* **Direct App Deep-Link Buttons:** One-tap payment launch for:
  * Google Pay (`tez://upi/pay?...`)
  * PhonePe (`phonepe://pay?...`)
  * Paytm (`paytmmp://pay?...`)
  * Generic UPI Apps (`upi://pay?...`)
* **Background QR Auto-Scan & Fetch Engine (`jsQR`):**
  * Silently extracts QR pixel data onto an offscreen `<canvas>`.
  * Decodes verified UPI URI string via `jsQR` and launches target UPI app seamlessly.
  * Live camera scanner & file upload decoder included.
* **Smart 'Desi Jugaad' Fallback System:**
  * **Save QR to Gallery:** Exports branded payment card PNG via `canvas.toDataURL`.
  * **Interactive Mobile Bottom Sheet:** Step-by-step guidance (*Save QR ➔ Open GPay/PhonePe ➔ Scan from Gallery*).
  * **One-Tap VPA Copy:** Instant clipboard copy with toast notifications.
  * **12-Digit UTR Verification:** Reference verification box with NPCI loading state and verified success receipt modal.

## 📁 Project Structure

```text
├── index.html        # Complete standalone web page (HTML5, Tailwind CSS, Vanilla JS)
├── my_qr.jpg         # Original merchant QR code
├── README.md         # Project documentation
└── .gitignore
```

## 💻 How to Run Locally

Simply open `index.html` in any modern web browser or serve with a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .
```

Visit `http://localhost:8000` in your browser.

## 🌐 Deploy to GitHub Pages

1. In your GitHub repository, go to **Settings** > **Pages**.
2. Under **Build and deployment** > **Branch**, select `main` (root) and click **Save**.
3. Your live checkout page will be instantly accessible globally!

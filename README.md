# OpenAI (ChatGPT) Conversions API for sGTM

Integrate your server-side Google Tag Manager (sGTM) container with the **OpenAI (ChatGPT) Conversions API**. This tag allows you to send conversion events directly to OpenAI's servers, ensuring high-accuracy attribution, improved data privacy, and resilience against browser-side tracking limitations.

## 🚀 Key Features

* **Precision Attribution**: Built-in support for the `oppref` (OpenAI Click Identifier) to link conversions directly to your ChatGPT Ad campaigns.
* **Robust Deduplication**: Intelligent use of `event_id` to prevent double-counting between the browser pixel and server-side events.
* **Enhanced Match Quality**: Securely transmit hashed user data (Email/Phone) to improve conversion matching and optimization.
* **Dynamic Data Mapping**: A flexible parameter table allows you to send custom metadata, e-commerce values, and currencies without touching the template code.
* **Validation Mode**: Includes a "Debug Mode" (Validate Only) to verify your setup with OpenAI’s API without affecting live reporting.

## ⚙️ Configuration

Create a new tag using this template and configure the following fields:

| Field | Description |
| :--- | :--- |
| **API Key** | Your OpenAI Bearer Token (found in OpenAI Ads Manager). |
| **Pixel ID** | Your unique OpenAI Pixel ID (`pid`). |
| **Event Name** | The event type (e.g., `purchase`, `lead`). Defaults to the incoming `event_name`. |
| **Oppref ID** | The `oppref` identifier. Captured from the URL or cookie (`__oppref`). |
| **User Data** | Map user identifiers like Email or Phone Number for better attribution. |
| **Flexible Parameters** | Use the table to add metadata like `value`, `currency`, or `transaction_id`. |

## 💡 Best Practices

### The `oppref` Identifier
To maximize attribution accuracy, ensure your web container captures the `oppref` query parameter from the landing page URL and stores it in a first-party cookie. Map that cookie variable to the **Oppref ID** field in this tag.

### Event Deduplication
To avoid over-reporting, ensure the `event_id` sent via this sGTM tag matches the `event_id` sent by your browser-side OpenAI Pixel. When IDs match, OpenAI will deduplicate the signals, prioritizing the server-side data for accuracy.

### Testing
Use the **"Debug Mode (Validate Only)"** checkbox during initial setup. This sends a test request to OpenAI to check for schema errors. The event will be validated but not processed for actual reporting. Once verified in the GTM Preview console, uncheck the box for production.

## 📄 Reference
For detailed API specifications and standard event names, refer to the [Official OpenAI Ads Documentation](https://developers.openai.com/ads/conversions-api).

---
*Maintained for server-side Google Tag Manager implementations.*

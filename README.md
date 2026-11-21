# n8n-facebook-auto-reply-gemini
Automated Facebook Page auto-reply workflow built in n8n using Google Gemini, Webhook, and Respond to Webhook
# Facebook Page Auto-Reply with n8n & Google Gemini

Automated workflow in **n8n** that receives incoming messages via a `POST` Webhook (`facebook-auto-reply`), generates contextual replies using **Google Gemini**, structures sender and reply fields via `Edit Fields`, and returns the final response using `Respond to Webhook`.

## Workflow Flow
1. **Webhook (`POST`)**: Captures incoming payload (`sender_id`, `sender_name`, `message`) with `Using 'Respond to Webhook' Node`.
2. **Basic LLM Chain + Google Gemini Chat Model**: Generates the reply based on the incoming message.
3. **Edit Fields (Set)**: Organizes clean output fields (`sender_id`, `sender_name`, `incoming_message`, `ai_reply`).
4. **Respond to Webhook**: Returns the formatted output to the caller.

## Local Test Command (`curl`)
```bash
curl.exe -X POST "http://localhost:5678/webhook-test/facebook-auto-reply" \
  -F "sender_id=987654321" \
  -F "sender_name=Sara_Hassan" \
  -F "message=I_need_help_with_my_order_and_delivery_time"


## Appointment Booking & Calendar Availability Workflow

Automated workflow built in **n8n** to handle appointment booking requests, check availability in **Google Calendar**, and respond via **Webhook**.

### How It Works
1. **Webhook Trigger:** Receives incoming appointment requests and booking details.
2. **Calendar Availability Check:** Queries **Google Calendar** to check existing events and slot availability.
3. **Conditional Logic (`If`):** Evaluates whether the requested time slot is available.
4. **Event Creation:** Creates a new calendar event when a slot is available.
5. **Webhook Response:** Sends the booking confirmation or availability status back to the caller.

### Workflow File
- `My workflow 4.json` — Exported n8n workflow definition.
-





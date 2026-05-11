
# 🧠 Customer Support (n8n Workflow)
A multi-product AI Support Agent powered by n8n and GPT-4o-mini. This workflow uses a Router-Solver architecture to intelligently classify incoming queries before generating product-specific responses.

# 🚀 Features

Multi-Product Support: Handles queries for three distinct SaaS products:
Bullet: Document/writing automation.
Focuzed: Productivity and task planning.
BunnyDesk: Time tracking and work logs.
Intelligent Routing: Analyzes user intent (Setup, Bug, How-to, Pricing) and Product context before formulating a reply.
Context Awareness: Maintains a conversation memory (Window Buffer) for natural follow-up questions.
Structured Output: Returns clean JSON responses with escalation flag (needsEscalation: true/false).

# 🛠️ Architecture

The workflow follows a linear "Pipeline" pattern with two distinct AI Agents:

Normalization Layer:
Cleans chat input, extracts email addresses (Regex), and standardizes session IDs.
Router Agent (Classifier):
Analyzes the message to detect Product and Intent.
Outputs a confidence score.
Support Agent (Solver):
Takes the Classification + Original Message.
Consults product-specific system prompts.
Generates the final reply.

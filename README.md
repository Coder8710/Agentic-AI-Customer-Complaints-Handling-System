## 🗾 **Title and Short Intro**

**Project Title:**  
**Agentic AI Customer Complaints Handling System**

**Short Introduction:**  
This project is an **AI-powered automation system** designed to handle and resolve customer complaints efficiently.  
It uses **Google Sheets**, **Google Gemini AI**, and **n8n** to automate the entire complaint resolution process — from reading new complaints to drafting emails, getting team feedback, and sending final responses to customers.
The AI automatically drafts complaint resolutions, making the work of the customer support team faster and easier. This eliminates the need for them to spend extra time thinking about each complaint resolution, allowing them to process complaints more quickly and handle a larger number of complaints — ultimately boosting overall productivity and efficiency.  
This system helps companies save time and allows their customer support teams to handle **more complaints in less time, hence benefiting company's business**.

---

## 🚀 **Features**

- ✅ Automatically detects new customer complaints from Google Sheets.  
- 🧠 Uses **Google Gemini AI** to generate complaint summaries and draft resolutions. 
- 🤖 AI automatically drafts complaint resolutions, making the work of the customer support team much easier. 
- 📩 Sends emails to the customer support team for approval,decline or feedback.  
- 🔁 Based on feedback, AI prepares and sends the **final email** to the customer.  
- 🗂 Updates the main Google Sheet with the latest complaint status automatically.  
- ⏱ Runs every minute, ensuring real-time updates and responses.  
- 📈 Improves productivity — support team can handle up to **2x more complaints daily**.

---

## ⚙️ **Workflow Overview**

1. **Google Sheets Trigger**  
   - Checks every minute for new customer complaints.  

2. **Loop Over Items**  
   - Processes each new complaint one by one.  

3. **AI Agent (Google Gemini)**  
   - Reads the complaint and fetches order details from the `order_tracking` sheet.  
   - Drafts a resolution email for the support team with summary, solution, and feedback options.  

4. **Send Message (Gmail)**  
   - Sends the draft email to the support team.  

5. **IF Node**  
   - Waits for feedback (Approve, Decline, Improve, or Worsen Resolution).  

6. **AI Agent 1 (Approved cases/Approved but modified resolution)**  
   - Creates a final customer email if resolution is approved/modified.  

7. **AI Agent 2 (Declined)**  
   - Creates a final customer email if resolution is Declined. 

8. **Send Email**  
   - Sends the final email to the customer.  

9. **Update Row in Google Sheet**  
   - Updates complaint status (Approved, Declined, Complaint Closed, etc.)  

---

## 🖼 **Workflow Diagram Section**

Here’s the visual layout of workflow 👇  

**Workflow Overview Image:**  
![Workflow Overview](AI_workflow.png)

🧩 **Main Components:**  
- Google Sheets Trigger  
- Loop Over Items  
- AI Agent (Gemini)  
- Send Message (Gmail)  
- IF Node  
- AI Agent 1 & 2  
- Structured Output Parsers  
- Email Sending  
- Google Sheet Updater  

This visual flow ensures every complaint is processed end-to-end automatically.

---

## 🛠 **Requirements**

- **n8n (Self-hosted or Cloud)**  
- **Google Gemini API access**  
- **Google Sheets API** (for main and order_tracking sheets)  
- **Gmail integration**   
- **Internet connection** for live triggers and email sending  

---

## 🔑 **Setup Steps**

1. **Open n8n**  
   - Launch your **n8n instance** (either self-hosted or cloud).

2. **Create a New Workflow**  
   - In the top-right corner, click **“New Workflow”**.

3. **Import the Given Workflow File**  
   - Click the **three dots** in the top-right corner.  
   - Choose **“Import from File”**.  
   - Select the provided JSON file (`Agentic AI Customer Complaints Handling Project.json`).  
   - This will automatically load all **nodes and connections** shown in the workflow diagram.

4. **Set Up Required Credentials**  
   After importing, you only need to configure credentials for the following services used in the workflow:

   - 🟢 **Google Sheets**  
     - Used in nodes: **Google Sheets Trigger**, **order_tracking**, and **Update row in main sheet**.  
     - Set up **Google Sheets credentials** with access to your complaint and order tracking sheets.

   - ✉️ **Gmail**  
     - Used in nodes: **Send a message**, **Send email**, and **Send email1**.  
     - Add **Gmail credentials** to send emails from your official support address.

   - 🤖 **Google Gemini AI**  
     - Used in nodes: **AI Agent**, **AI Agent1**, and **AI Agent2**.  
     - Provide your **Google Gemini API key** to enable AI-based response generation and resolution drafting.

5. **Save and Activate the Workflow**  
   - Click **“Activate”** (top right).  
   - The workflow will now automatically check your Google Sheet every minute for new complaints and process them using AI.

6. **Test the Workflow**  
   - Add a **new complaint entry** in your Google Sheet.  
   - The AI should read the complaint, draft a **resolution email**, and update the sheet after sending messages.

---

## 📧 **Example Flow**

**Step 1:**  
Customer submits complaint → added to Google Sheet  

**Step 2:**  
AI reads complaint and order info → drafts email with summary and resolution suggestion  

**Step 3:**  
Support team receives email → suggest feedback ( Approve Resolution / Approve but modify resolution / Decline Resolution) 

**Step 4:**  
AI prepares the final customer email based on team feedback  

**Step 5:**  
Customer receives the email → status updated in main Google Sheet  

---

## 📌 **Use Cases**

- 🤖 **AI-Assisted Resolution Drafting:** The AI automatically drafts complaint resolutions, reducing the effort needed by 
      the support team. This helps them process complaints faster, handle more complaints efficiently, and significantly boost overall productivity.
- 🧩 **Customer Support Automation:** Automatically handles repetitive complaint emails.  
- 🕚 **Time Saving:** Support team can handle 2× more complaints daily compared to manual processing.  
- 🧠 **AI-Driven Resolutions:** AI drafts complaint summaries and resolutions based on company policies.  
- 💬 **Consistent Communication:** Ensures all customers receive professional and timely responses.  
- 📊 **Business Growth:** Increases efficiency, reduces response time, and improves customer satisfaction.


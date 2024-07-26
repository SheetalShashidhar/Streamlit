Here is the documentation in normal text format:

---

**1. Add Domain Knowledge**

**Endpoint:** `POST /addDomainKnowledge`  
**Description:** Adds a new entry to the domain knowledge base. If the entry already exists, it returns an error. Updates the vector store after adding the entry.  
**Expected Input:** 
- Body: 
  - `description` (string): The description to be added to the domain knowledge base.  
  - Data Type: `DomainKnowledgeEntry`  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `message` (string): "Successfully added to domain knowledge base"

**Error Handling:**
- Status Code: `400 Bad Request`  
- Detail: "Entry already exists in the knowledge base"

---

**2. Delete Domain Knowledge**

**Endpoint:** `DELETE /deleteDomainKnowledge`  
**Description:** Deletes an existing entry from the domain knowledge base. Updates the vector store after deletion.  
**Expected Input:** 
- Body: 
  - `description` (string): The description to be deleted from the domain knowledge base.  
  - Data Type: `DomainKnowledgeEntry`  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `message` (string): "Successfully deleted from domain knowledge base"

---

**3. Display Domain Knowledge**

**Endpoint:** `GET /displayDomainKnowledge`  
**Description:** Retrieves and displays all entries from the domain knowledge base.  
**Expected Input:** None  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `data` (array of strings): List of domain knowledge entries

---

**4. Add User Instruction**

**Endpoint:** `POST /addUserInstruction`  
**Description:** Adds a new user instruction to the `user_instruct.json` file. If the file does not exist, it is created.  
**Expected Input:** 
- Body: 
  - `question` (string): The question for the instruction.
  - `instruction` (string): The instruction text.  
  - Data Type: `Instruction`  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `message` (string): "Successfully added instruction"

---

**5. Display Admin Instructions**

**Endpoint:** `GET /displayAdminInstructions`  
**Description:** Retrieves and displays all admin instructions from the `admin_instructions.json` file.  
**Expected Input:** None  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `data` (object): Dictionary of admin instructions (question as key and instruction as value)

---

**6. Delete Admin Instruction**

**Endpoint:** `DELETE /deleteAdminInstruction`  
**Description:** Deletes a specific admin instruction from the `admin_instructions.json` file.  
**Expected Input:** 
- Query Parameter: 
  - `question` (string): The question of the instruction to be deleted.  
  - Data Type: `str`  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `message` (string): "Successfully deleted instruction"

**Error Handling:**
- Status Code: `404 Not Found`  
- Detail: "Instruction not found" or "Instructions file not found"

---

**7. Get Pending Instructions**

**Endpoint:** `GET /getPendingInstructions`  
**Description:** Retrieves and displays all pending user instructions from the `user_instruct.json` file.  
**Expected Input:** None  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `data` (object): Dictionary of pending user instructions (question as key and instruction as value)

---

**8. Accept Pending Instruction**

**Endpoint:** `POST /acceptPendingInstruction`  
**Description:** Moves a pending instruction from `user_instruct.json` to `admin_instructions.json`.  
**Expected Input:** 
- Body: 
  - `question` (string): The question for the instruction.
  - `instruction` (string): The instruction text.  
  - Data Type: `Instruction`  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `message` (string): "Successfully accepted and added instruction"

---

**9. Reject Pending Instruction**

**Endpoint:** `DELETE /rejectPendingInstruction`  
**Description:** Removes a pending instruction from `user_instruct.json` without adding it to `admin_instructions.json`.  
**Expected Input:** 
- Query Parameter: 
  - `question` (string): The question of the instruction to be rejected.  
  - Data Type: `str`  
**Output:** 
- Status Code: `200 OK`  
- Body: 
  - `status` (string): "success"
  - `message` (string): "Successfully rejected instruction"

**Error Handling:**
- Status Code: `404 Not Found`  
- Detail: "Instruction not found" or "User instructions file not found"

---

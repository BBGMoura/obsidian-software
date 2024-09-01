### **Simplified Task: Secure Note Storage**

**Objective:**  
Design a `SecureNoteStorage` system that securely stores and retrieves user notes. The system should support basic encryption, efficient data retrieval, and simple access logging.

### **Requirements:**

#### 1. **Classes and Interfaces:**

- **`Note`**: Represents a note with an ID and content.
- **`SecureNoteStorage`**: Manages a collection of notes securely.
- **`EncryptionStrategy`**: Interface for an encryption algorithm.
- **`SimpleAuditLog`**: Manages logging of access events.

#### 2. **Functional Requirements:**

**`Note`**:
- **Attributes**: `id` (String), `content` (String).
- **Methods**:
    - `getId()`: Returns the note's ID.
    - `getContent()`: Returns the note's content.

**`SecureNoteStorage`**:
- **Attributes**: A collection of `Note` objects, an `EncryptionStrategy`, a `SimpleAuditLog`.
- **Methods**:
    - `storeNote(Note note)`: Stores the note in an encrypted form.
    - `retrieveNote(String noteId)`: Retrieves and decrypts the note by ID.
    - `setEncryptionStrategy(EncryptionStrategy encryptionStrategy)`: Sets the encryption strategy to be used.
    - `logAccess(String noteId)`: Logs an access event for auditing.

**`EncryptionStrategy`**:
- **Methods**:
    - `encrypt(String data)`: Encrypts the data.
    - `decrypt(String data)`: Decrypts the data.

**`SimpleAuditLog`**:
- **Methods**:
    - `logEvent(String noteId)`: Logs an access event with a note ID.
    - `getLog()`: Returns a log of all access events.

#### 3. **Features to Implement:**

1. **Data Storage and Retrieval**:
    - Store notes in an encrypted form.
    - Retrieve and decrypt notes based on the note ID.

2. **Encryption Strategy**:
    - Implement a simple encryption strategy (e.g., reversing the string).
    - Allow changing the encryption strategy at runtime.

3. **Auditing**:    
    - Log each access to a note.
    - Retrieve a simple log of access events.

4. **Edge Cases**:
    - Handling the retrieval of non-existent notes.
    - Ensure that logging occurs each time a note is accessed.

### **Instructions:**

1. **Start with TDD**: Write basic unit tests first based on the functional requirements. Focus on covering the normal use cases and a few edge cases.
2. **Implement the `Note`, `SecureNoteStorage`, `EncryptionStrategy`, and `SimpleAuditLog` classes/interfaces**.
3. **Refactor if Needed**: Keep the code simple and maintainable. Make small adjustments if necessary based on test results.
4. **Document Your Code**: Add comments for clarity where needed.

### **Deliverables:**

- A basic implementation of the `Note` class with ID and content attributes.
- A `SecureNoteStorage` class with methods for storing, retrieving, and managing notes.
- An `EncryptionStrategy` interface with one simple implementation.
- A `SimpleAuditLog` class that tracks and retrieves access events.
- A set of unit tests that validate the basic functionality of note storage, encryption, and logging.

### **Complexity Considerations:**

- Focus on implementing basic functionality to handle storage, encryption, and logging within the time frame.
- Ensure that the system can easily be extended with more complex encryption or additional features in the future.

This simplified task should be achievable within one hour, providing a balance between implementing a practical system and showcasing your ability to handle data management and security concerns.
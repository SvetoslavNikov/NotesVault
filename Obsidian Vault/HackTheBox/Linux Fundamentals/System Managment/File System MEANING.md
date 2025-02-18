
#### **Without Filesystem**

Input: "hello.txt"  
Data stored as:  
`01001000 01100101 01101100 01101100 01101111` (just binary data with no structure)

**Result**:  
You won’t know:

- Where the file starts or ends.
- How to access the file by name.

---

#### **With Filesystem (e.g., ext4)**

Input: "hello.txt"  
File Structure:

- **Filename**: "hello.txt"
- **Data**: `01001000 01100101 01101100 01101100 01101111`
- **Metadata** (location, size, creation date) stored in a directory.

 **Result**:

- You can retrieve the file easily by typing its name.
- The system knows the file’s size and where it’s located.

### **Conclusion**

**Without Filesystem** → Unreadable and chaotic data  
**With Filesystem** → Organized, accessible files and directories
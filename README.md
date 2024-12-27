# gcm

**gcm** is a command line utility that replaces `git commit -m "message"` with an automated workflow:

1. **Detect** your staged changes by running `git diff --staged`.
2. **Find** an `.env` file containing `OPENAI_API_KEY` (current directory, parent, or grandparent).
3. **Send** those changes to OpenAI to generate a short summary of the commit.
4. **Commit** using the generated short summary as the commit message.

## Setup

1. **Install**:  
   - Save the file named `gcm` (no extension) to a directory in your `$PATH` (e.g., `~/bin/gcm`).
   - Make it executable:  
     ```bash
     chmod +x ~/bin/gcm
     ```
   - Confirm you can run it:  
     ```bash
     gcm --help
     ```
     (Currently, it doesn’t have a `--help` flag, but this verifies the script is accessible.)

2. **.env File**:  
   Place a `.env` file in your project or one level above, or two levels above (etc.), containing the line:
   ```bash
   OPENAI_API_KEY=YOUR_KEY_HERE


# Generating a .tex File with All Changes Marked

Follow the steps below to generate a `.tex` file that highlights all changes between the original and revised versions of your document:

### Folder Structure

Ensure your directory follows this structure:

```
<parent-folder>
├── Makefile
├── original
│   ├── figures
│   ├── original.tex
│   └── sections
└── revised
    ├── figures
    ├── revised.tex
    └── sections
```

### Steps to Generate `changes-marked.tex`

1. **Download Sources:**
   - Download the **original source** from PCS and place it in the `original` directory.
   - Download the **revised source** from Overleaf and place it in the `revised` directory.

2. **Obtain the Makefile:**
   - Download the `Makefile` from this directory and place it in the root of the `<parent-folder>`.

3. **Install Homebrew (if not already installed):**
   - Follow the installation instructions provided [here](https://docs.brew.sh/Installation).

4. **Run the Command:**
   - Navigate to the `<parent-folder>` in your terminal.
   - Run the following command:
     ```
     make
     ```

5. **Check Output:**
   - If everything runs successfully, a new file named `changes-marked.tex` will be created in the `<parent-folder>`.

6. **Upload and Compile on Overleaf:**
   - Upload the `changes-marked.tex` file to the root folder of your Overleaf project.
   - Compile the project to generate a PDF in the ACM format with all changes marked.

---

### Additional Notes

- Verify the file paths and folder structure match the instructions before running `make`.
- If you encounter issues during the process, check for errors in the terminal output and confirm all dependencies are installed.
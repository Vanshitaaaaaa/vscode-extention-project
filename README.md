### LeetCode Fetcher Extension  

The LeetCode Fetcher is a Chrome extension that makes it easy to fetch test cases and generate solution files for LeetCode problems. With this tool, you can directly extract test cases from a LeetCode problem page and create solution files in Python (.py) or C++ (.cpp). It also lets you test your solutions using the provided test script (`test.py`) and run tasks in VS Code.  

---

### Features  
- Automatically detects the URL of the open LeetCode problem.  
- Lets you choose between Python (`.py`) or C++ (`.cpp`) for the solution file.  
- Extracts test cases and saves them in a `test_cases_named.json` file.  
- Creates a boilerplate solution file in your chosen language.  
- Allows you to test solutions using preloaded test cases with the help of `test.py`.  

---

### Installation  

#### 1. Clone or Download the Extension  
Download the files or clone the repository to your computer.  

#### 2. Install the Chrome Extension  
- Open Chrome and go to `chrome://extensions/`.  
- Enable **Developer Mode** in the top-right corner.  
- Click **Load unpacked** and select the folder containing the extension files.  

#### 3. Set Up the API Server  
- Make sure Python is installed on your system.  
- Install the required Python packages by running:  
  ```bash
  pip install flask cloudscraper beautifulsoup4
  ```
- Start the Flask server by running:  
  ```bash
  python app.py
  ```
- The server will run at `http://127.0.0.1:5000`.  

---

### How to Use  

#### 1. Running the Extension  
- Open any LeetCode problem page in Chrome.  
- Click the **LeetCode Fetcher** icon in the toolbar.  
- Select your preferred programming language (Python or C++).  
- The extension will save the test cases and generate a solution file in the default directory.  

#### 2. Folder Structure  
The generated files will follow this structure:  
```
/leetcode/
├── two-sum/
│   ├── test_cases_named.json
│   ├── solution.py
│   ├── solution.cpp
├── test.py
└── .vscode/
    └── tasks.json
```

---

### Testing Your Solution  

#### Prerequisites  
- Place the `test.py` file (from this repository) in the `leetcode` folder.  
- Add the provided `tasks.json` file inside a `.vscode` folder in the `leetcode` directory.  

#### Steps to Test  
1. Open Visual Studio Code (VS Code).  
2. Open the solution file (e.g., `solution.py` or `solution.cpp`).  
3. Press **Ctrl+Shift+P** (or **Cmd+Shift+P** on Mac) and select **Tasks: Run Task**.  
4. Choose **Test Current Solution** from the task list.  
5. The test results will appear in the terminal.  

---

### Important Notes  
- **Folder Setup**: Ensure the `leetcode` folder exists at the specified path. If you rename the folder, update the path in `fetch.py`.  
- **`tasks.json`**: This file configures VS Code to run `test.py` with the selected solution file.  
- **Language Selection**: When using the extension, make sure to select the correct programming language (`cpp` or `py`).  

![GhostInTheShell](https://github.com/user-attachments/assets/3b2bf498-6abe-4a27-98b9-5a68f2a03c29)


- **Shell GPT**: Revolutionizing Command-line Productivity

---

## Introduction to Shell GPT

- AI Power Command-line productivity tool 
- For Hobbyist, Developers, Administrators, Pentesters
- Key Features:
	- Natural language command execution, 
	- Automate command execution, 
	- Generating Scripts, 
	- Coding assistance.
- Support all major OS and Docker
-  Compatible - PowerShell, CMD, Bash, Zsh etc.

---

### Requirements

#### Open AI API key is required. 
(May need to purchase depend on your usage)

Create OpenAI API key for Shell-GPT: https://platform.openai.com/
![image](https://github.com/user-attachments/assets/8a609da8-1ffd-485d-9ae4-91430548f719)

---

#### Python 3 is required.

```Bash
python3 --version
```

#### pip is required.

```bash
pip3 --version
```

---

### Working with virtual environment

Create a virtual environment for GPT
```
python3 -m venv ~/.venv/presentvenv
```

Activate virtual environment
```
source ~/.venv/presentvenv/bin/activate
```

Deactivate virtual environment
```
deactivate
```

---

### Install  Shell-gpt

```
pip3 install shell-gpt
```

 Regularly update Shell GPT to the latest version to access new features and improvements:
```
pip3 instll --upgrade shell-gpt
```


---
### Configuration

Edit bshrc or zshrc:
```
nano ~/.bashrc or nano ~/.zshrc
```

Paste following line at the end of the file:
```
export PATH=~/.local/bin:$PATH
``` 

To apply changes, run:
```
source ~/.bashrc or source ~/.zshrc
```

Shell-GPT Configuration file:
```
nano ~/.config/shell_gpt/.sgptrc
```


---

### Full list of arguments

```
sgpt --help
                                                                                                                            
 Usage: sgpt [OPTIONS] [PROMPT]                                                                                              
                                                                                                                             
╭─ Arguments ───────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│   prompt      [PROMPT]  The prompt to generate completions for.                                                           │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ─────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --model                         TEXT                       Large language model to use. [default: gpt-4o-mini]            │
│ --temperature                   FLOAT RANGE [0.0<=x<=2.0]  Randomness of generated output. [default: 0.0]                 │
│ --top-p                         FLOAT RANGE [0.0<=x<=1.0]  Limits highest probable tokens (words). [default: 1.0]         │
│ --md             --no-md                                   Prettify markdown output. [default: md]                        │
│ --editor         --no-editor                               Open $EDITOR to provide a prompt. [default: no-editor]         │
│ --cache          --no-cache                                Cache completion results. [default: cache]                     │
│ --version                                                  Show version.                                                  │
│ --help                                                     Show this message and exit.                                    │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Assistance Options ──────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --shell           -s                        Generate and execute shell commands.                                          │
│ --interaction         --no-interaction      Interactive mode for --shell option. [default: interaction]                   │
│ --describe-shell  -d                        Describe a shell command.                                                     │
│ --code            -c                        Generate only code.                                                           │
│ --functions           --no-functions        Allow function calls. [default: functions]                                    │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Chat Options ────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --chat                 TEXT  Follow conversation with id, use "temp" for quick session. [default: None]                   │
│ --repl                 TEXT  Start a REPL (Read–eval–print loop) session. [default: None]                                 │
│ --show-chat            TEXT  Show all messages from provided chat id. [default: None]                                     │
│ --list-chats  -lc            List all existing chat ids.                                                                  │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Role Options ────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --role                  TEXT  System role for GPT model. [default: None]                                                  │
│ --create-role           TEXT  Create role. [default: None]                                                                │
│ --show-role             TEXT  Show role. [default: None]                                                                  │
│ --list-roles   -lr            List roles.                                                                                 │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```

---

### To Change different AI model
- Higher temperature >1.0, more creative, random
- Lower temperature <1.0, more predictable, conservative
- Default temperature 1.0

```
sgpt --model gpt-4o-mini --temperature 1.0 "hi"
```

```
sgpt --model gpt-4o --temperature 1.0 "hi"
```

---

### Usage

- #### Generating Code
- #### Chat
- #### REPL aka Interactive mode
- #### Analysis
- #### Shell Commands
- #### Summarization

---

### Generating Code

Generate a python code for input validation:
```
sgpt --code "create an implementation of input validation to prevent SQLi attacks in python"
```

Redirect output to a file:
```
sgpt --code "create an implementation of input validation to prevent SQLi attacks in python" > ~/projects/presentations/SQLi-validate.py"
```

Use pipe to pass input into Shell-GPT:
```
cat SQLi-validate.py  | python -m sgpt --code "generate comments for before each line of the code"
```

---

### Chat

Start a chat named 'recipe-idea':
```
sgpt --chat recipe-idea "Please provide 3 receipe for the weekend"
```

Display all onging chat sessions:
```
sgpt --list-chats
```

Recall previous chat
```
sgpt --show-chat recipe-idea
```

---

### REPL (read–eval–print-loop) aka Interactive mode

```
sgpt --repl temp
Entering REPL mode, press Ctrl+C to exit.
>>> Explain following statement
Please provide the statement you'd like me to explain, and I'll be happy to help!                  
>>> sql = "SELECT id FROM users WHERE username='" + user + "' AND password='" + pass + "'"
```

---

#### Analysis

Anlyze a log file for anomalies:
```
tail -n 20 ~/projects/loghub/Windows/Windows_2k.log | sgpt "Analyze the log, identify anomalies, and suggest potential fixes."
```

---

### Shell Commands

Generate and execute shell commands.
Finding log files:
```
sgpt --shell "find all log files in  ~/projects/loghub/"
```


Change file permission to read only:
```
sgpt --shell "set all the files in this directory  ~/projects/loghub/Windows to ready only and list them"
```
---

### Summarization

Summarize a story from a text file:
```
cat ~/projects/presentations/security-engineer-story.txt | sgpt "extract text from the file and summerize it"
```

---

# Thank you!

---

#### Reference: https://github.com/TheR1D/shell_gpt


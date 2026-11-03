# Scripts and safe validation

This project does not require offensive scripts. Use normal, controlled Windows activity inside your own VM to generate the events described in `docs/detection-use-cases.md`.

Examples:
- Sign in normally with a lab test account.
- Make one intentional failed sign-in to your own test account.
- Create a temporary local test account through Windows' normal administration interface.
- Open Notepad and locate its Sysmon process-creation event.
- Create a harmless text file in a dedicated test folder.

Keep tests limited to systems and accounts you own or are authorized to administer. Record what you did, the expected event, and the actual result.

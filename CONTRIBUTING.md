# Contributing Guidelines

Thank you for your interest in contributing to this project!  
Our goal is to improve Windows security in a clear, maintainable, and well-documented way.  
Please read these rules before submitting any contribution.

---

## 📜 General Rules

1. **One Security Change per Pull Request**  
   - Each pull request must focus on **one distinct security change**.  
   - Example (not real case): You **cannot** disable both Edge and Chrome in the same PR.  
   - Exception: If disabling multiple items is required to disable a single target feature, they can be grouped together.

2. **Clear and Understandable Code**  
   - Every change must include **comments in the code** explaining:  
     - What the change does.  
     - Why it improves security.  
     - Any side effects or limitations.  

3. **Pull Request Description**  
   - Your PR description must include:  
     - A clear explanation of what the change does.  
     - The reason for making this change.  
     - Reliable sources (official documentation, CVEs, reputable articles) to support your change.

4. **No Unverified or Unsafe Changes**  
   - Changes must be tested before submission.  
   - Avoid changes that can cause system instability without a clear security benefit.

5. **No AI-Generated Contributions**  
   - The use of AI-generated code, scripts, or explanations is strictly prohibited.  
   - All contributions must be written and reviewed by a human contributor.  
   - This is to ensure accuracy, security, and maintainability.

6. **Coding Style**  
   - Follow the existing code formatting style in the repository.  
   - Use clear variable and function names.

---

## ✅ Example of a Good PR

- **Title:** Disable Windows Remote Assistance  
- **Description:**  
  This change disables the Remote Assistance feature to reduce the attack surface for remote intrusion.  
  Source: [Microsoft Documentation on Remote Assistance](https://learn.microsoft.com/...)  
- **Code:**  
  ```powershell
  # Disable Windows Remote Assistance
  # This prevents unsolicited remote connections to the system.
  Set-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\Remote Assistance' -Name 'fAllowToGetHelp' -Value 0

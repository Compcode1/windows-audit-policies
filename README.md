# Windows Audit Policies

This project documents the process of optimizing Windows Security Audit Policy settings for efficient detection and investigation using Splunk. The goal is to reduce log noise, retain high-value security events, and support detection-focused workflows in a SOC or lab environment.

## Project Overview

- **Purpose:**  
  Streamline Windows audit policy settings to balance security visibility with manageable event volume, supporting practical detection and analysis in Splunk.

- **Scope:**  
  - Initial baseline analysis of default audit policy and its output volume
  - Redesign of audit policy based on actual detection needs
  - Hands-on configuration, testing, and verification
  - Final recommendations for future refinement

## Project Phases

1. **Baseline Analysis:**  
   Review Windows Security event logs under default policy to identify high-volume noise and key detection signals.

2. **Policy Redesign:**  
   Map detection goals to audit policy settings. Identify and retain only essential event types.

3. **Policy Implementation:**  
   Apply the optimized audit policy using `auditpol` commands and (if needed) Group Policy.

4. **Verification:**  
   Generate test events (logon, failed logon, process launch, account/group changes, scheduled tasks) and confirm they are logged in Splunk with reduced noise.

5. **Documentation & Recommendations:**  
   Summarize outcomes, identify any remaining noise or data gaps, and provide guidance for ongoing policy refinement.

## Key Results

- **Significant reduction in low-value event noise** (e.g., Process Termination 4689).
- **All critical detection scenarios successfully captured** (logons, failed logons, privilege escalation, process creation, account changes, scheduled task creation).
- **Project notebook** (`windows_audit_policies.ipynb`) contains detailed steps, SPL queries, and validation results.

## Usage

- Review the notebook for step-by-step guidance.
- Apply audit policy changes on your Windows test system.
- Use the included SPL queries in Splunk to validate detection coverage.

## Repository

- **Notebook:** `windows_audit_policies.ipynb`
- **Author:** [Compcode1](https://github.com/Compcode1)

---

*For further improvements, periodically review audit policy effectiveness, adjust for emerging detection needs, and consider targeted SACL/Object Access auditing for high-value resources.*

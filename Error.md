In **Event Viewer**, errors related to RAM, motherboard, and CPU are often hardware-related and may not explicitly mention "RAM" or "CPU" directly. However, there are specific types of events and error codes you can look for that may indicate issues with these components.

Here’s how to identify potential errors related to each:

### 1. **RAM Errors**:
   - **Event ID**: You might see errors related to **Memory**.
   - Look for:
     - **WHEA-Logger (Event ID 18, 19, 20)**: WHEA stands for **Windows Hardware Error Architecture**. This can indicate memory or CPU-related errors.
     - **Event ID 41**: May indicate a memory failure leading to a system crash.
     - Errors mentioning "Memory", "Paging", or "Data Corruption".

   - Example message:
     ```
     A corrected hardware error has occurred. Component: Memory
     Error Source: Corrected Machine Check
     Error Type: Single-bit ECC error
     ```

### 2. **Motherboard Errors**:
   - **Event ID**: Errors related to the motherboard can vary depending on the component (e.g., chipset, PCIe devices, sensors).
   - Look for:
     - **WHEA-Logger (Event ID 17, 19)**: Often related to system buses, PCIe lanes, or other critical motherboard components.
     - **ACPI Errors**: These might indicate issues with the motherboard or BIOS.
     - **Event ID 6008**: An unexpected shutdown, which could be related to power or thermal issues originating from the motherboard.

   - Example message:
     ```
     The platform firmware has corrupted memory across the previous system boot. 
     Check firmware updates.
     ```

### 3. **CPU Errors**:
   - **Event ID**: CPU-related errors are often logged under **WHEA** (Windows Hardware Error Architecture) or **BugCheck** events.
   - Look for:
     - **WHEA-Logger (Event ID 18)**: Indicates a processor error.
     - **Event ID 1001 (BugCheck)**: This is often logged after a system crash or Blue Screen of Death (BSOD), and might indicate CPU failure if the error was related to CPU processing or thermal throttling.

   - Example message:
     ```
     A fatal hardware error has occurred. Component: Processor Core
     Error Source: Machine Check Exception (MCE)
     Error Type: Cache Hierarchy Error
     ```

### How to Search in Event Viewer:
1. In **Event Viewer**, go to **Windows Logs > System**.
2. Click **Filter Current Log** in the right pane.
3. Choose **Critical** and **Error** levels, and optionally enter the relevant **Event ID** (e.g., 18, 19, 41, etc.) to search specifically.
4. Look at the **Details** tab of the error for more in-depth technical information.

### Summary of Important Event IDs:
- **WHEA-Logger** (17, 18, 19, 20): Often related to hardware errors.
- **Event ID 41**: Kernel-Power errors, often caused by hardware issues like memory or motherboard.
- **Event ID 6008**: Unexpected shutdown, possibly from overheating or hardware failure.
- **Event ID 1001 (BugCheck)**: System crashes that may be caused by CPU or RAM failures.

These errors can help guide you to the root of the problem, but you may need additional tools, like hardware diagnostics utilities (e.g., MemTest86 for RAM, CPU-Z for CPU stress tests), to pinpoint the issue exactly.
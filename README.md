Model Performance Prism

A lightweight performance evaluation dashboard for comparing LLM inference benchmark sweeps across multiple models and deployment profiles.

Overview

Model Performance Prism is an interactive browser-based dashboard for analyzing performance sweep data generated from Large Language Model (LLM) inference benchmarks.

Instead of manually opening dozens of Excel sheets, engineers and product managers can upload benchmark results and instantly compare:

Throughput
Generation Speed
Time To First Token (TTFT)
Requests Per Minute (RPM)
Cached vs Uncached Throughput
Throughput per Hardware Box

The application automatically summarizes benchmark results into business-friendly insights while still exposing the raw engineering data.

Everything runs completely inside the browser.

No backend.
No database.
No server.

Features
Customer / Product Manager View

Designed for quick decision making.

Executive KPIs
Number of models evaluated
GO / Borderline / NO-GO classification
Best throughput
Best generation speed
Uploaded benchmark summary
Configurable Targets

Users can define:

Minimum Throughput
Minimum Generation Speed

Every model is automatically classified based on those targets.

Automatic Recommendations

Each model receives one of three decisions:

✅ GO
⚠️ Borderline
❌ NO-GO

along with a plain-English explanation.

Example:

Model A meets both throughput and generation speed targets. Safe to commit.

Model Cards

Each model includes:

Median throughput
Median generation speed
Number of benchmark profiles
Number of benchmark rows
Deployment recommendation
Visual Comparisons

Compare every uploaded model using interactive charts.

Available visualizations include:

Throughput comparison
Generation speed comparison
Head-to-Head Mode

Select any two models and compare:

Throughput
Generation Speed

Includes:

Side-by-side comparison cards
Winner indicators
Profile comparison line chart
Engineer View

The engineering interface exposes every benchmark row for detailed inspection.

Full Projection Table

Each benchmark row includes:

Model
Profile
Batch Size
Input Length
Output Length
Cache %
Throughput
Throughput per Box
TTFT
Generation Speed
RPM
Cached Throughput
Uncached Throughput
Anomaly Score
Filtering

Filter benchmark rows by:

Model
Profile

Sort by:

Model
Throughput
TTFT
Generation Speed
Anomaly Score
Engineering Charts

Visualizations include:

Median Comparison

Compare all uploaded models using any metric.

Supported metrics:

Throughput
TTFT
Generation Speed
RPM
Throughput per Box
Throughput vs TTFT Scatter Plot

Quickly identify performance tradeoffs.

Higher throughput with lower TTFT indicates better deployment candidates.

Head-to-Head Engineering Comparison

Compare two models across all engineering metrics.

Metrics include:

Throughput
TTFT
Generation Speed
RPM
Throughput per Box
Cached Throughput
Uncached Throughput

Winner badges are automatically generated for every metric.

Supported Input Format

The application accepts:

.xlsx
.xls

Multiple benchmark files may be uploaded simultaneously.

Each workbook may contain multiple sheets.

Automatically Recognized Columns

The parser automatically detects common benchmark column names.

Supported metrics include:

Metric	Aliases
Input Length	input length, input_len
Output Length	output length
Cache %	cache %, cache percent
Batch Size	batch size
Throughput	throughput (t/s)
Throughput / Box	throughput / box
Cached Throughput	cached throughput
Uncached Throughput	uncached throughput
TTFT	time to first token
Prompt Speed	real prompt speed
Generation Speed	gen speed
RPM	requests per minute

Minor naming differences are automatically handled.

Automatic Model Detection

Model names and benchmark profiles are inferred directly from filenames.

Example:

Model_Llama70B_Profile_1.xlsx

becomes

Model: Llama70B

Profile: Profile 1
Anomaly Detection

Basic validation is performed while importing data.

Current anomaly checks include:

Negative throughput
Negative TTFT
Extremely high TTFT
Negative generation speed
Invalid RPM

Rows are assigned an anomaly score and highlighted in the Engineer View.

Themes

Supports both:

Dark Theme
Light Theme

Themes can be toggled instantly without reloading the application.

Technologies
HTML5
CSS3
Vanilla JavaScript
Chart.js
SheetJS (xlsx)

No framework is required.

Project Structure
/
│
├── index.html
├── Converted_data.json
├── README.md
│
├── assets/
│
└── benchmark files/
Workflow
Upload Excel Files
        │
        ▼
Parse Workbook
        │
        ▼
Normalize Columns
        │
        ▼
Generate Records
        │
        ▼
Calculate Statistics
        │
        ▼
Compute GO / NO-GO
        │
        ▼
Interactive Dashboard
Performance Metrics

The dashboard summarizes benchmark results using median values for each model.

Key metrics include:

Median Throughput
Median Generation Speed
Median TTFT
Median RPM
Median Cached Throughput
Median Uncached Throughput

Median aggregation helps reduce the effect of outliers and provides a more stable comparison.

Use Cases

This dashboard is useful for:

LLM benchmarking
Hardware evaluation
Capacity planning
Product demonstrations
Customer architecture reviews
Internal engineering validation
Performance regression analysis
Comparing deployment profiles
Future Improvements

Potential enhancements include:

CSV export
PDF reports
Benchmark history
Performance regression tracking
Percentile statistics (P50/P95/P99)
Latency distributions
GPU utilization metrics
Power consumption analysis
Cost-per-token comparisons
Benchmark version history
Benchmark diff mode
Live benchmark streaming
Multi-node cluster comparisons
Automated report generation
License

This project is intended for internal benchmarking and performance analysis.

Modify and extend as needed for your deployment workflows.

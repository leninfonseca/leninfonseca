<!--
  Profile design V3. Versions README.md and README-v2.md are preserved.
  SVG assets are vector illustrations written as code, not generated raster images.
-->
<div align="center">

<img src="assets/v3-hero.svg" width="100%" alt="Lenin Fonseca — Data Engineering, Analytics and Business Intelligence. Data pipeline from ingestion to analytics." />

<br/>

<a href="https://leninfonseca.com"><img src="https://img.shields.io/badge/PORTFOLIO-Website-111827?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio website"/></a>
<a href="https://github.com/leninfonseca/barcelona-urban-mobility-data-platform"><img src="https://img.shields.io/badge/FEATURED_PROJECT-Barcelona_Mobility-2563EB?style=for-the-badge&logo=github&logoColor=white" alt="Featured project"/></a>
<a href="https://github.com/leninfonseca?tab=repositories"><img src="https://img.shields.io/badge/REPOSITORIES-GitHub-111827?style=for-the-badge&logo=github&logoColor=white" alt="Repositories"/></a>

<br/>

</div>

## 01 — Featured project

### Barcelona Urban Mobility Data Platform

A Microsoft Fabric data platform built using public Barcelona Bicing station availability data. It captures API snapshots, maintains incremental historical records, models data for analytical querying, and provides a Power BI reporting layer.

<div align="center">

<a href="https://github.com/leninfonseca/barcelona-urban-mobility-data-platform">
<img src="https://raw.githubusercontent.com/leninfonseca/barcelona-urban-mobility-data-platform/main/assets/demos/project-barcelona.gif" width="92%" alt="Power BI report demo from the Barcelona Urban Mobility project"/>
</a>

<br/>

<a href="https://github.com/leninfonseca/barcelona-urban-mobility-data-platform"><img src="https://img.shields.io/badge/SOURCE_CODE-111827?style=flat-square&logo=github&logoColor=white" alt="Source code"/></a>
<a href="https://github.com/leninfonseca/barcelona-urban-mobility-data-platform/tree/main/architecture"><img src="https://img.shields.io/badge/ARCHITECTURE-2563EB?style=flat-square" alt="Architecture documentation"/></a>
<a href="https://github.com/leninfonseca/barcelona-urban-mobility-data-platform/tree/main/docs"><img src="https://img.shields.io/badge/DOCUMENTATION-111827?style=flat-square" alt="Technical documentation"/></a>

</div>

<table>
<tr>
<td width="33%" valign="top">
<strong>THE PROBLEM</strong>
<p>Public mobility data changes continuously. A single API response isn't enough to study station availability over time.</p>
</td>
<td width="33%" valign="top">
<strong>THE SOLUTION</strong>
<p>Immutable Bronze snapshots, incremental historical processing in Silver, validation rules and a Gold dimensional model.</p>
</td>
<td width="34%" valign="top">
<strong>THE OUTCOME</strong>
<p>Query-ready Delta tables, a SQL Analytics Endpoint and an interactive Power BI report with analytical KPIs.</p>
</td>
</tr>
</table>

## 02 — Data platform architecture

<img src="assets/v2-platform.svg" width="100%" alt="Barcelona Urban Mobility architecture: REST API, Bronze, Silver, Gold, Power BI." />

The system ingests timestamped JSON snapshots into OneLake Bronze. PySpark processes previously unseen snapshots into Delta-based Silver history; the Gold layer exposes a dimensional model for SQL analysis and Power BI.

The Barcelona district dataset is managed as a separate ingestion branch and is not joined into the Gold model.

## 03 — Technical stack

<div align="center">

**Languages and development**

<br/>

<a href="https://www.python.org/"><img src="https://skillicons.dev/icons?i=python&theme=dark" width="49" alt="Python"/></a>&nbsp;
<a href="https://www.postgresql.org/"><img src="https://skillicons.dev/icons?i=postgres&theme=dark" width="49" alt="PostgreSQL"/></a>&nbsp;
<a href="https://www.mysql.com/"><img src="https://skillicons.dev/icons?i=mysql&theme=dark" width="49" alt="MySQL"/></a>&nbsp;
<a href="https://www.java.com/"><img src="https://skillicons.dev/icons?i=java&theme=dark" width="49" alt="Java"/></a>&nbsp;
<a href="https://git-scm.com/"><img src="https://skillicons.dev/icons?i=git&theme=dark" width="49" alt="Git"/></a>&nbsp;
<a href="https://www.docker.com/"><img src="https://skillicons.dev/icons?i=docker&theme=dark" width="49" alt="Docker"/></a>&nbsp;
<a href="https://code.visualstudio.com/"><img src="https://skillicons.dev/icons?i=vscode&theme=dark" width="49" alt="Visual Studio Code"/></a>

<br/><br/>

**Data platforms and analytics**

<br/>

<a href="https://azure.microsoft.com/"><img src="https://skillicons.dev/icons?i=azure&theme=dark" width="28" height="28" alt="Microsoft Azure logo"/></a>&nbsp;
<img src="https://img.shields.io/badge/Microsoft_Fabric-512DA8?style=for-the-badge&logoColor=white" alt="Microsoft Fabric"/>&nbsp;
<img src="https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white" alt="PySpark"/>&nbsp;
<img src="https://img.shields.io/badge/Delta_Lake-008D82?style=for-the-badge&logoColor=white" alt="Delta Lake"/>&nbsp;
<a href="https://powerbi.microsoft.com/"><img src="https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logoColor=black" alt="Power BI"/></a>

</div>

<br/>

| Data engineering | Data analytics and BI |
| :-- | :-- |
| API and JSON ingestion | Analytical SQL |
| Data Factory pipelines | Star schema design |
| Bronze / Silver / Gold architecture | Fact and dimension tables |
| Incremental processing and watermarks | Power BI semantic models |
| Delta MERGE and idempotency | DAX measures and KPI calculations |
| Data validation and error handling | Interactive reporting |



## 04 — Engineering implementation

<details>
<summary><strong>Incremental processing and idempotency</strong></summary>

The Silver notebook processes new Bronze snapshots identified through watermark logic. An insert-only Delta MERGE keyed by station and capture timestamp prevents duplicate historical observations during reruns.

</details>

<details>
<summary><strong>Data validation</strong></summary>

Critical validations stop invalid processing. Non-critical anomalies in source availability breakdowns are retained and flagged instead of silently corrected.

</details>

<details>
<summary><strong>Dimensional modeling</strong></summary>

The Gold layer includes an availability fact table and station, date, and time dimensions. This model supports SQL querying and Power BI calculations.

</details>

<details>
<summary><strong>Recovery and operational considerations</strong></summary>

The project documents timestamp parsing, changes in station counts, and capacity throttling. Safe manual reruns support recovery of pending snapshots; automated recovery is not claimed.

</details>

## 05 — Certification and contact

**Microsoft Certified: Azure Data Fundamentals**  
`DP-900` · Azure data concepts and services

<img src="https://img.shields.io/badge/Microsoft_Certified-DP--900-2563EB?style=flat-square" alt="Microsoft Certified DP-900"/>

<div align="center">

<a href="https://leninfonseca.com"><img src="https://img.shields.io/badge/PORTFOLIO-leninfonseca.com-2563EB?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio"/></a>

</div>

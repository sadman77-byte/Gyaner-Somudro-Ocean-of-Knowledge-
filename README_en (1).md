# 🌊 Ocean of Knowledge (Gnaner Somudro)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Replit%20%7C%20Node.js%20%7C%20Python-blue)](https://replit.com)
[![Storage Target](https://img.shields.io/badge/Target-1%20Billion%20Contents%20(2055)-emerald)](#)
[![Infrastructure](https://img.shields.io/badge/Distributed%20Nodes-50--100%20Servers-purple)](#)
[![Status](https://img.shields.io/badge/Status-Active%20Development-brightgreen)](#)

> **"Knowledge is not bound by borders; the ocean of knowledge belongs to everyone."**

**Ocean of Knowledge (Gnaner Somudro)** is a massive, distributed, and 100% legally compliant open digital library and research platform. It hosts classic and modern fiction, non-fiction books, rare historical manuscripts, and up-to-date scientific research papers across multiple languages.

The platform architecture is engineered to scale up to **1 Billion (100 Crore) contents by 2055**, while maintaining a lightweight web reader experience operating seamlessly across a distributed infrastructure.

---

## 📑 Table of Contents

1. [Key Features](#-key-features)
2. [System Architecture](#-system-architecture)
3. [Infrastructure & Server Cluster (50-100 Nodes Setup)](#-infrastructure--server-cluster-50-100-nodes-setup)
4. [Legal Framework & Copyright Compliance](#-legal-framework--copyright-compliance)
5. [Installation & Deployment (Replit Ready)](#-installation--deployment-replit-ready)
6. [Zip File Storage Hydrator (Zip Extractor & Parser)](#-zip-file-storage-hydrator-zip-extractor--parser)
7. [Contributing & License](#-contributing--license)

---

## ✨ Key Features

- 📖 **Full-Text Free Reading:** Read books directly in your web browser with a high-speed embedded reader—no paywalls, no hidden subscriptions.
- 📥 **Zero-Wait PDF Downloads:** High-speed PDF downloads routed through 50 to 100 distributed server nodes and edge CDNs.
- 📚 **Comprehensive Content Coverage:**
  - **Fiction:** Classics, Sci-Fi, Thrillers, Novels, Anthologies.
  - **Non-Fiction:** History, Philosophy, Self-Improvement, Biographies, Science & Tech.
  - **Research Papers:** Open-access academic journals, preprints, and archived thesis documents.
- 🚀 **2055 Scaling Roadmap:** Designed with sharded indexing and distributed search engines to handle 1 billion files.
- 📦 **Smart Zip Hydrator:** Built-in Python utility script to automate extracting, parsing, and indexing bulk `.zip` archives directly into server storage.
- ⚖️ **100% Legal & Ethical:** Fully compliant with Public Domain guidelines, Creative Commons (CC) licenses, and Open Access publishing frameworks.

---

## 🏗️ System Architecture

```
                       ┌─────────────────────────┐
                       │  Client / Web Browser   │
                       └───────────┬─────────────┘
                                   │
                           [ Cloudflare Anycast ]
                                   │
                       ┌───────────▼─────────────┐
                       │  Replit Primary Gateway │
                       │    (Load Balancer)      │
                       └───────────┬─────────────┘
                                   │
       ┌───────────────────────────┼───────────────────────────┐
       │                           │                           │
┌──────▼──────┐             ┌──────▼──────┐             ┌──────▼──────┐
│  Node 001   │             │  Node 050   │   ...       │  Node 100   │
│ (Storage A) │             │ (Storage B) │             │ (Storage Z) │
└──────┬──────┘             └──────┬──────┘             └──────┬──────┘
       │                           │                           │
       └───────────────────────────┼───────────────────────────┘
                                   │
                       ┌───────────▼─────────────┐
                       │ Global Metadata Engine  │
                       │  (ElasticSearch/Redis)  │
                       └─────────────────────────┘
```

---

## 🖥️ Infrastructure & Server Cluster (50-100 Nodes Setup)

To serve and host up to 1 billion items, "Ocean of Knowledge" utilizes a distributed file delivery topology (HTTP Cluster + Storage Nodes):

1. **Server Node Load Balancing:** Incoming read/download requests are distributed dynamically across 50–100 active backend server environments.
2. **Fail-safe Redundancy:** Automatic fallback ensures that if any single storage node goes offline, content remains accessible from redundant peer nodes.
3. **Edge Caching:** Popular titles are cached on edge nodes to achieve sub-200ms page load times.

---

## ⚖️ Legal Framework & Copyright Compliance

"Ocean of Knowledge" strictly adheres to global intellectual property laws:

1. **Public Domain Works:** Books and literature whose copyright terms have expired (typically 50–70 years post-author's death).
2. **Creative Commons & Open Access:** Content distributed under CC licenses, open academic repositories (e.g., ArXiv, PubMed, OpenDOAR), and public license frameworks.
3. **Author & Publisher Partnerships:** Digitized content hosted with explicit written authorization from rightsholders.
4. **DMCA Policy:** Rightsholders can request immediate content removal through our Takedown Request procedure, processed within 24 hours.

---

## ⚙️ Installation & Deployment (Replit Ready)

This repository is optimized for one-click deployment on **Replit**.

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/gnaner-somudro.git
cd gnaner-somudro
```

### Step 2: Install Dependencies
```bash
# Node.js dependencies
npm install

# Python zip hydrator dependencies
pip install -r requirements.txt
```

### Step 3: Configure Environment
Rename `.env.example` to `.env` and configure your environment parameters:
```env
PORT=3000
NODE_ENV=production
CLUSTER_NODES_COUNT=50
STORAGE_GATEWAY_URL=https://nodes.gnanersomudro.org
DATABASE_URL=mongodb+srv://...
```

### Step 4: Run the Application
```bash
npm start
```

---

## 📦 Zip File Storage Hydrator (Zip Extractor & Parser)

Use the built-in storage hydrator script to automatically process bulk `.zip` archives containing PDFs and metadata:

```python
# scripts/zip_hydrator.py
import zipfile
import os

def process_book_zips(zip_folder, output_dir):
    if not os.path.exists(output_dir):
        os.makedirs(output_dir)
        
    for item in os.listdir(zip_folder):
        if item.endswith('.zip'):
            file_path = os.path.join(zip_folder, item)
            with zipfile.ZipFile(file_path, 'r') as zip_ref:
                print(f"Extracting & Indexing: {item}...")
                zip_ref.extractall(output_dir)
                print(f"Successfully Processed {item}")

if __name__ == "__main__":
    process_book_zips('./uploaded_zips', './public/library')
```

---

## 📜 MIT License

```text
MIT License

Copyright (c) 2026 Ocean of Knowledge (Gnaner Somudro) Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<p align="center">
  <b>Knowledge is a universal human right — Thank you for contributing to the Ocean of Knowledge project.</b>
</p>

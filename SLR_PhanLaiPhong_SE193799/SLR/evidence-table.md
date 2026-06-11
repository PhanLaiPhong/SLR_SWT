# Evidence Table — Đánh Giá Chất Lượng Bug Report bằng LLM

**Thành viên:** Phan Lại Phong  
**Tổng số bài báo (N):** 313 papers → **15 bài INCLUDE** sau 2 vòng screening  
**PICO:** P = Bug reports · I = LLM assess/improve quality · O = Quality metrics

---

## 1. AgentReport: A Multi-Agent LLM Approach for Automated and Reproducible Bug Report Generation

**Tác giả & Năm:** Choi & Yang, 2025 · **Venue:** Applied Sciences [OK]  
**DOI:** [https://doi.org/10.3390/app152211931]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | Multi-agent LLM pipeline (QLoRA-4bit fine-tuning, CTQRS prompting, CoT, one-shot exemplar) |
| **Dataset** | 3,966 summary–report pairs từ Bugzilla |
| **Metrics** | CTQRS · ROUGE-1 Recall · ROUGE-1 F1 · SBERT |
| **Kết quả** | CTQRS: **80.5%** · ROUGE-1 Recall: **84.6%** · ROUGE-1 F1: **56.8%** · SBERT: **86.4%** |
| **Hạn chế** | N/A |

---

## 2. Can We Enhance Bug Report Quality Using LLMs?: An Empirical Study of LLM-Based Bug Report Generation

**Tác giả & Năm:** Acharya & Ginde, 2025 · **Venue:** ACM EASE 2025 [OK]  
**DOI:** [https://doi.org/10.1145/3756681.3756995]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | Qwen 2.5 · Mistral · LLaMA 3.2 (fine-tuned instruction) · ChatGPT-4o (3-shot) |
| **Dataset** | Bugzilla; unseen projects: Eclipse, GCC |
| **Metrics** | CTQRS · ROUGE · METEOR · SBERT · F1 per field |
| **Kết quả** | CTQRS: Qwen 2.5 (**77%**) > GPT-4o 3-shot (**75%**) > Mistral (**71%**) > LLaMA 3.2 (**63%**) · Qwen 2.5 F1 S2R: **76%** · CTQRS unseen projects: **~70%** |
| **Hạn chế** | Hiệu suất phụ thuộc nhiều vào chất lượng dữ liệu fine-tuning; chưa thử nghiệm trên bug reports không phải tiếng Anh |

---

## 3. Improving Bug Reporting by Fine-Tuning the T5 Model: An Evaluation in a Software Industry

**Tác giả & Năm:** Gonzaga et al., 2025 · **Venue:** SAST 2025 [OK]  
**DOI:** [https://doi.org/10.5753/sast.2025.13591]
| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | T5 (fine-tuned, 3 iterations) |
| **Dataset** | 1,800 bug reports thực tế năm 2024 từ môi trường công nghiệp |
| **Metrics** | BLEU · METEOR · Precision · Recall · F1-Score |
| **Kết quả** | BLEU: **0.9845** · METEOR: **0.9634** · Precision: **0.9898** · Recall: **0.9886** · F1: **0.9892** · Success rate (test): **70%** |
| **Hạn chế** | Chỉ hoạt động tốt với 2 loại bug độ phức tạp thấp; cần điều chỉnh thêm cho nhiều loại issue hơn |

---

## 4. An Empirical Study on the Capability of LLMs in Decomposing Bug Reports

**Tác giả & Năm:** Chen et al., 2025 · **Venue:** arXiv 2504.20911  *(venue chưa xác nhận)*  
**DOI:** [https://doi.org/10.48550/arxiv.2504.20911]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | ChatGPT · DeepSeek (zero-shot → few-shot prompting) |
| **Dataset** | 127 privacy-related bug reports từ Apache Jira |
| **Metrics** | True Decomposition Rate |
| **Kết quả** | ChatGPT: tăng **140%** sau prompt tuning · DeepSeek: tăng **163.64%** sau prompt tuning (từ mức zero-shot rất kém) |
| **Hạn chế** | Hiệu suất phụ thuộc mạnh vào chất lượng prompt; zero-shot performance còn kém |

---

## 5. ImproBR: Bug Report Improver Using LLMs

**Tác giả & Năm:** Akyol et al., 2026 · **Venue:** EASE 2026 (ACM)  *(venue chưa xác nhận)*  
**DOI:** [https://doi.org/10.48550/arxiv.2604.26142]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | GPT-4o mini + fine-tuned DistilBERT + heuristic analyzer + RAG (Minecraft Wiki) |
| **Dataset** | 139 bug reports từ Mojira (Minecraft bug tracker) |
| **Metrics** | Structural completeness (%) · Executable S2R (%) · Fully reproducible reports |
| **Kết quả** | Completeness: **7.9% → 96.4%** · Executable S2R: **28.8% → 67.6%** · Fully reproducible: **1 → 13** (×13) |
| **Hạn chế** | Phạm vi domain hẹp (Minecraft); RAG phụ thuộc vào chất lượng knowledge base |

---

## 6. Automated Generation of High-Quality Bug Reports for Android Applications (BugScribe)

**Tác giả & Năm:** Saha et al., 2026 · **Venue:** arXiv 2604.01148  *(venue chưa xác nhận)*  
**DOI:** [https://doi.org/10.48550/arxiv.2604.01148]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | BugScribe: LLM + GUI interaction context (thông tin màn hình và thao tác) |
| **Dataset** | 48 bug reports từ 26 Android apps |
| **Metrics** | Correctness · Completeness (unified quality framework cho OB/EB/S2R) |
| **Kết quả** | BugScribe vượt trội so với original reports và các LLM-based baselines trên cả correctness và completeness |
| **Hạn chế** | Giới hạn ở Android; phụ thuộc vào GUI interaction data |

---

## 7. Empirical Analysis and Detection of Hallucinations in LLM-Generated Bug Report Summaries

**Tác giả & Năm:** Nirujan et al., 2026 · **Venue:** Peer-reviewed  *(venue chưa xác nhận)*  
**DOI:** [https://doi.org/10.48550/arxiv.2605.24137]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | Section-aware hallucination detection model (multiple pretrained LMs) |
| **Dataset** | BugsRepo dataset (Mozilla OSS); 80 structured summaries (exploratory) |
| **Metrics** | Macro-F1 (report-level · section-level · hallucination-type) |
| **Kết quả** | Report-level Macro-F1: **0.89** · Section-level: **0.83** · Hallucination-type: **0.84** · Exploratory: **47.9%** missing info, **12.3%** fabricated content |
| **Hạn chế** | Dùng synthetic hallucination injection; có thể không phản ánh hallucinations tự nhiên trong thực tế |

---

## 8. CTQRS-Based Reinforcement Learning Framework for Reliable Bug Report Generation Using Open-Source LLMs

**Tác giả & Năm:** Yang, 2025 · **Venue:** Applied Sciences [OK]  
**DOI:** [https://doi.org/10.3390/app152312545]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | Qwen2.5-7B-Instruct + SFT + PPO Reinforcement Learning (CTQRS làm reward signal) + Refinement |
| **Dataset** | Bugzilla dataset |
| **Metrics** | CTQRS · SBERT · RL reward value |
| **Kết quả** | SFT→RL→Refinement: CTQRS **0.46→0.72→0.76** · SBERT **0.68→0.84→0.85** · Reward: **0.42→0.65** |
| **Hạn chế** | Chưa đánh giá trên nhiều domain ngoài Bugzilla; chi phí huấn luyện RL cao |

---

## 9. Automated Root-Cause Subclassification and No-Code Fix Generation for Invalid Bug Reports

**Tác giả & Năm:** Gön et al., 2026 · **Venue:** arXiv 2605.17561  *(venue chưa xác nhận)*  
**DOI:** [https://doi.org/10.48550/arxiv.2605.17561]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | Vanilla LLM · RAG · Agentic web search (GPT-5, DeepSeek, fine-tuned RoBERTa) |
| **Dataset** | Gold-standard benchmark thủ công (invalid bug reports) |
| **Metrics** | Weighted F1-Score · BERTScore · Judge LLM success rate |
| **Kết quả** | RAG: **0.66** weighted F1 (best overall) · Non-reproducibility F1: **0.85** · Agentic Judge LLM: **68.9%** · WAD peak: **87.4%** |
| **Hạn chế** | Wrong Version subclass rất khó phân loại (F1: 0.00–0.29) |

---

## 10. False-Positive Bug Reports in Deep Learning Compilers: Stages, Root Causes, and Mitigation

**Tác giả & Năm:** Huang et al., 2025 · **Venue:** ACM TOSEM [OK]  
**DOI:** [https://doi.org/10.1145/3774889]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | LLM few-shot prompting (vanilla LLM, RAG, agentic) |
| **Dataset** | 1,075 closed issues từ TVM và OpenVINO |
| **Metrics** | Accuracy · Precision · Recall · Explanation quality (Judge-based) |
| **Kết quả** | Few-shot prompting đạt accuracy và explanation quality cao trong phát hiện false-positive bug reports |
| **Hạn chế** | Chỉ tập trung DL compilers; khó tổng quát hóa sang domain khác |

---

## 11. Automatic Generation of Bug Reports Using Large Language Models: An Evaluation in a Software Institute

**Tác giả & Năm:** Chaves et al., 2025 · **Venue:** SBQS 2025 [OK]  
**DOI:** [https://doi.org/10.5753/sbqs.2025.13599]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | T5 (fine-tuned) |
| **Dataset** | Bug reports từ team kiểm thử thiết bị di động (môi trường công nghiệp) |
| **Metrics** | BLEU · METEOR · Precision · Recall · F1-Score · Acceptance rate (user study) |
| **Kết quả** | 3/5 loại bug đạt **87.5%** outputs được đánh giá valid hoặc partially valid · Acceptance rate cao từ team kiểm thử |
| **Hạn chế** | Cần điều chỉnh thêm cho nhiều loại issue; human review vẫn cần thiết sau khi sinh |

---

## 12. Past, Present, and Future of Bug Tracking in the Generative AI Era

**Tác giả & Năm:** Torun et al., 2026 · **Venue:** ACM TOSEM [OK]  
**DOI:** [https://doi.org/10.1145/3806655]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | AI framework: LLM agents (report refinement, validity assessment, severity classification, patch generation) |
| **Dataset** | N/A (survey + framework design + initial empirical grounding) |
| **Metrics** | Time to resolution · Coordination overhead reduction |
| **Kết quả** | Đề xuất framework AI-powered giảm thời gian resolution và overhead phối hợp; empirical component ban đầu xác nhận tính khả thi |
| **Hạn chế** | Framework còn ở giai đoạn vision/design; chưa có full-scale empirical evaluation |

---

## 13. From Reviewers' Lens: Understanding Bug Bounty Report Invalid Reasons with LLMs

**Tác giả & Năm:** Zheng et al., 2025 · **Venue:** IEEE (peer-reviewed, Dec 2025) [OK]  
**DOI:** [https://doi.org/10.48550/arxiv.2511.18608]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | GPT-5 · DeepSeek · fine-tuned RoBERTa + RAG framework (taxonomy of rejection reasons) |
| **Dataset** | 9,942 bug bounty reports từ HackerOne/BugCrowd (1,400 invalid) |
| **Metrics** | Accuracy · Classification consistency · F1 |
| **Kết quả** | Accuracy tổng thể cao nhưng xu hướng over-accept invalid cases; RAG cải thiện classification consistency và giảm bias đáng kể |
| **Hạn chế** | Mô hình khó phát hiện invalid cases; reviewer reputation bias ảnh hưởng kết quả |

---

## 14. A Retrieval-Augmented LLM Framework for Severity Prediction of Bug Reports in Cloud-Based Mobile Applications

**Tác giả & Năm:** Ali et al., 2025 · **Venue:** Journal of Cloud Computing (Springer) [OK]  
**DOI:** [https://doi.org/10.1186/s13677-025-00826-w]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | RAG-GPT-SBR: fine-tuned GPT-2 + BM25 + dense retrieval hybrid |
| **Dataset** | Public Hugging Face bug report dataset (cloud-based mobile apps) |
| **Metrics** | Accuracy · Precision · Recall · F1-Score |
| **Kết quả** | vs deep learning baselines: Accuracy **+7.98%** · Precision **+8.20%** · Recall **+7.90%** · F1 **+8.10%** |
| **Hạn chế** | Chỉ đánh giá trên cloud-based mobile apps; chưa thử nghiệm trên domain phần mềm khác |

---

## 15. FeedAIde: Guiding App Users to Submit Rich Feedback Reports by Asking Context-Aware Follow-Up Questions

**Tác giả & Năm:** Pourasad et al., 2026 · **Venue:** IEEE/ACM MOBILESoft 2026 [OK]  
**DOI:** [https://doi.org/10.1145/3795077.3795120]

| Mục | Chi tiết |
|-----|----------|
| **Tool / LLM** | FeedAIde: Multimodal LLM (context-aware follow-up questions, screenshot input) |
| **Dataset** | 54 feedback/bug reports từ iOS gym app (user study) |
| **Metrics** | Completeness (expert assessment) · Ease of use · Helpfulness (user-rated) |
| **Kết quả** | Cải thiện completeness cho bug reports & feature requests · 2 industry experts đánh giá cao · Users: easier & more helpful so với form thông thường |
| **Hạn chế** | Phạm vi nhỏ (54 reports, 1 ứng dụng); có thể bị ảnh hưởng bởi novelty effect |

---

## Ghi chú tổng hợp

- Tổng số bài **INCLUDE** sau 2 vòng screening: **15 papers** (từ N = 313)
- Số liệu ở phần Kết quả được lấy từ Abstract hoặc full-text bài gốc
- Các ô "N/A" ở Dataset hoặc Hạn chế là bình thường khi làm thực tế

###  Venues chưa xác nhận — cần theo dõi trước khi nộp bản cuối SLR

| # | Venue |
|---|-------|
| 7 | arXiv 2504.20911 |
| 8 | EASE 2026 (ACM) |
| 9 | arXiv 2604.01148 |
| 10 | arXiv 2605.24137 |
| 12 | arXiv 2605.17561 |

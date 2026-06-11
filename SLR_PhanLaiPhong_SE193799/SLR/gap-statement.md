# Gap Statement — LLM-Based Bug Report Quality Assessment

Evidence table: N = 15 papers

---

## Các khoảng trống phát hiện

### GAP-T (Technology): Thiếu so sánh hệ thống giữa các paradigm LLM trên cùng quality framework

Các nghiên cứu hiện tại chia thành 3 hướng riêng lẻ — fine-tuning (T5, DistilBERT, Qwen 2.5), prompting (zero-shot/few-shot ChatGPT, DeepSeek), và RL-based (PPO với CTQRS reward) — nhưng không có nghiên cứu nào so sánh trực tiếp ba hướng này trên cùng dataset và cùng bộ metrics. Ngoài ra, chỉ 1/15 papers (FeedAIde) tích hợp multimodal input (screenshot), trong khi bug reports thực tế thường đi kèm log, screenshot, và video.

**Bằng chứng:**
- Fine-tuning: Gonzaga et al. (2025) — T5 trên dataset công nghiệp; Chaves et al. (2025) — T5 trên mobile testing; Acharya & Ginde (2025) — Qwen/Mistral/LLaMA trên Bugzilla
- Prompting: Chen et al. (2025) — ChatGPT/DeepSeek zero-shot→few-shot trên Apache Jira; Kumar et al. (2024) — GPT-4o/LLaMA-3/Gemini cho summarization evaluation
- RL-based: Yang (2025) — PPO với CTQRS reward trên Bugzilla, là nghiên cứu duy nhất theo hướng này
- Không paper nào chạy cả ba paradigm trên cùng một benchmark để so sánh công bằng
- Multimodal: chỉ Pourasad et al. (2026) dùng screenshot input — 14/15 papers chỉ xử lý text thuần

---

### GAP-M (Metric): Thiếu bộ metrics chuẩn hóa — không thể so sánh kết quả cross-study

Mỗi nghiên cứu tự chọn bộ metrics riêng. Không có paper nào báo cáo đủ một bộ metrics chung, khiến việc so sánh kết quả giữa các nghiên cứu gần như không thực hiện được. Human evaluation cũng rất hạn chế — chỉ 2/15 papers có user study hoặc expert assessment thực sự.

**Bằng chứng:**
- CTQRS-based: Choi & Yang (2025), Acharya & Ginde (2025), Yang (2025) — không dùng BLEU/METEOR
- BLEU/METEOR/F1: Gonzaga et al. (2025), Chaves et al. (2025) — không dùng CTQRS hay SBERT
- Completeness (%): Akyol et al. (2026) — không dùng bất kỳ NLP metric nào
- Macro-F1 (hallucination): Nirujan et al. (2026) — framework riêng, không overlap với papers khác
- True Decomposition Rate: Chen et al. (2025) — metric độc nhất, không paper nào khác dùng
- Human evaluation: chỉ Kumar et al. (2024) so sánh LLM vs human evaluators; Pourasad et al. (2026) có 2 industry experts — 13/15 papers hoàn toàn dùng automated metrics

---

### GAP-D (Dataset): Dataset nhỏ, tập trung một số platform, thiếu đa dạng domain và ngôn ngữ

Phần lớn dataset đến từ Bugzilla hoặc các platform open-source phổ thông. Nhiều nghiên cứu có dataset quá nhỏ để tổng quát hóa. Không có nghiên cứu nào xử lý bug reports đa ngôn ngữ hoặc từ domain chuyên biệt (safety-critical, embedded, enterprise).

**Bằng chứng:**
- Dataset nhỏ (dưới 200 reports): Saha et al. (2026) — 48 reports; Pourasad et al. (2026) — 54 reports; Chen et al. (2025) — 127 reports; Akyol et al. (2026) — 139 reports
- Tập trung Bugzilla: Choi & Yang (2025) — 3,966 pairs; Acharya & Ginde (2025) — Bugzilla + Eclipse/GCC; Yang (2025) — Bugzilla duy nhất
- Dataset lớn nhất: Zheng et al. (2025) — 9,942 reports nhưng giới hạn ở bug bounty context (HackerOne/BugCrowd), không đại diện cho open-source hay enterprise
- Domain hẹp: Akyol et al. (2026) — Minecraft; Saha et al. (2026) và Pourasad et al. (2026) — mobile apps; Ali et al. (2025) — cloud-based mobile apps
- Đa ngôn ngữ: Acharya & Ginde (2025) ghi rõ "chưa thử nghiệm trên bug reports không phải tiếng Anh" — 15/15 papers chỉ xử lý tiếng Anh

---

## Phát biểu GAP tổng hợp

Mặc dù 15 nghiên cứu đã chứng minh LLM có thể đánh giá và cải thiện chất lượng bug report qua các framework CTQRS, completeness (OB/EB/S2R), và validity assessment, vẫn tồn tại ba khoảng trống cốt lõi: (1) chưa có nghiên cứu nào so sánh hệ thống giữa fine-tuning, prompting và RL-based approach trên cùng benchmark, dẫn đến không rõ paradigm nào tối ưu cho từng quality dimension;
(2)** thiếu bộ metrics chuẩn hóa khiến kết quả giữa các nghiên cứu không thể so sánh trực tiếp và human validation còn rất hạn chế; 
(3) phần lớn dataset có quy mô nhỏ, tập trung vào một số platform và domain hẹp, và toàn bộ 15 papers chỉ xử lý bug reports tiếng Anh — giới hạn nghiêm trọng khả năng tổng quát hóa của các phát hiện hiện tại.

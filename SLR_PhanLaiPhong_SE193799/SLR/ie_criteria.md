# IE Criteria — Bug Report Quality Assessment with LLM
**Thành viên:** [Họ tên]
**RQ:** "Đối với bug reports trên GitHub/Jira (P), LLM đánh giá chất lượng báo cáo lỗi tự động theo tiêu chí reproducibility (I) so với developer manual review (C) có đạt Cohen's Kappa ≥ 0.70 không (O)?"
**PICO:**
- P = Bug reports từ các hệ thống issue tracker (GitHub Issues, Jira, Bugzilla...)
- I = LLM / Generative AI (GPT-3+, ChatGPT, GPT-4, LLaMA...) đánh giá chất lượng tự động
- C = Developer manual review / Human expert review
- O = Cohen's Kappa ≥ 0.70 (hoặc agreement/reproducibility metrics tương đương)

---

## Inclusion Criteria (IC) — Bài báo PHẢI đáp ứng ĐẦY ĐỦ TẤT CẢ các mã dưới đây

| Mã      | Nội dung chi tiết                                                                                                                                                                                           |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **IC-L** | Ngôn ngữ trình bày bắt buộc phải là tiếng Anh.                                                                                                                                                            |
| **IC-Y** | Xuất bản từ **2020** đến nay. *Lý do khoa học:* LLM thế hệ GPT-3+ (nền tảng cho các hệ thống đánh giá văn bản tự động) bắt đầu phổ biến rộng rãi từ năm 2020; các nghiên cứu trước đó không dùng LLM nên không phù hợp với PICO.I. |
| **IC-T** | Được công bố trên hội nghị (conference) hoặc tạp chí (journal) chính thống trong ngành SE/AI: ICSE, FSE, ASE, MSR, ICSME, SANER, ISSTA, IST, TSE, TOSEM, EMSE, JSS, IEEE Access...                      |
| **IC-P** | Bài báo tập trung vào tác vụ **đánh giá chất lượng bug reports** — bao gồm: đánh giá khả năng tái tạo (reproducibility assessment), đánh giá tính đầy đủ/rõ ràng (completeness, clarity), hoặc phân loại chất lượng (quality classification) của bug/issue/defect reports. |
| **IC-I** | Bài báo sử dụng ít nhất một trong các kỹ thuật: **LLM** (GPT-3/4, ChatGPT, LLaMA, Gemini, Claude...), **NLP/ML** (BERT, T5, RoBERTa...), hoặc hệ thống **AI-based** để tự động hóa hoặc hỗ trợ việc đánh giá. |
| **IC-E** | Bài báo gốc có ít nhất **một con số kết quả thực nghiệm cụ thể** (số liệu tường minh) được hiển thị trong Table hoặc Figure (ví dụ: Kappa = 0.72, Accuracy = 85%, F1 = 0.81...).                         |

---

## Exclusion Criteria (EC) — Loại bỏ bài báo nếu BẤT KỲ điều kiện nào sau đây đúng

| Mã       | Nội dung chi tiết                                                                                                                                                                                           |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **EC-D** | Bài báo bị trùng lặp với bài báo khác đã có trong danh sách (cùng DOI, cùng title, hoặc cùng nội dung với version khác nhau → giữ lại version published chính thức).                                     |
| **EC-A** | Không thể tìm hoặc không thể truy cập nội dung **bản toàn văn (full-text)** sau khi đã thử: Semantic Scholar, arXiv, ResearchGate, Unpaywall Extension, CORE. Nếu chỉ có abstract → loại.                |
| **EC-S** | Dung lượng bài báo dưới **4 trang** — bao gồm: poster, short paper, extended abstract, 2-page summary. Kiểm tra số trang trong PDF.                                                                       |
| **EC-N** | Không có nội dung thực nghiệm — dạng **position paper, vision paper, tutorial, survey/mapping study thuần lý thuyết** không có số liệu thực nghiệm gốc.                                                  |
| **EC-O** | Không thuộc phạm vi đề tài. **Loại ngay nếu bài báo chỉ về:**  (1) *Bug fixing / Patch generation* — sửa bug, tạo patch tự động (không phải đánh giá chất lượng report).  (2) *Bug triaging / Classification* — phân loại loại bug, assign bug cho developer (không liên quan đến quality của report). (3) *Bug report generation* — tự động tạo ra bug reports mới (không phải đánh giá reports hiện có).  (4) *Test case generation từ bug reports* — sinh test case từ bug, không phải đánh giá report.  (5) *Code review / code quality assessment* — đánh giá code, không phải bug report. |

---

## Lưu ý phân biệt IC-P và EC-O

> **Dễ nhầm nhất:** Một bài có thể dùng LLM (đúng IC-I) nhưng để *tóm tắt* bug reports thay vì *đánh giá chất lượng* → vẫn EXCLUDE (vi phạm IC-P, ghi lý do EC-O).

| Trường hợp | Quyết định | Lý do |
|------------|-----------|-------|
| LLM đánh giá reproducibility của bug report | INCLUDE | Đúng IC-P + IC-I |
| LLM so sánh agreement với developer khi review bug report | INCLUDE | Đúng IC-P + IC-I |
| LLM tóm tắt bug report cho developer đọc nhanh | EXCLUDE | EC-O (không đánh giá quality) |
| ML phân loại bug là security vs. performance | EXCLUDE | EC-O (bug triaging, không phải report quality) |
| LLM generate bug report tự động từ crash log | EXCLUDE | EC-O (generation, không phải assessment) |
| LLM đề xuất patch fix cho bug | EXCLUDE | EC-O (bug fixing) |

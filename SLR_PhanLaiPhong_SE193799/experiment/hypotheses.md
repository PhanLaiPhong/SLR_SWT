# Hypotheses — LLM-Based Bug Report Quality Assessment

**Thành viên:** Phan Lại Phong  
**Derived from:** 01_rq.md · evidence-table.md · gap-statement.md  
**Statistical framework:** Non-parametric comparison (Mann-Whitney U) hoặc paired t-test tùy distribution

---

## Hypothesis Set 1 — So sánh Fine-tuning vs. Prompting (Primary)

Trực tiếp trả lời RQ chính thức.

### H1-0 (Null)
> Fine-tuning approaches và prompting approaches **không có sự khác biệt có ý nghĩa thống kê** về CTQRS score khi đánh giá chất lượng bug reports trên cùng loại dataset (Bugzilla / open-source trackers).
>
> *Formally:* μ(CTQRS_finetune) = μ(CTQRS_prompting)

### H1-1 (Alternative)
> Fine-tuning approaches đạt **CTQRS score cao hơn** prompting approaches một cách có ý nghĩa thống kê khi đánh giá chất lượng bug reports trên cùng loại dataset.
>
> *Formally:* μ(CTQRS_finetune) > μ(CTQRS_prompting)

**Ngưỡng quyết định:** α = 0.05 (two-tailed cho exploratory; one-tailed nếu directional hypothesis được justify bởi prior evidence)

**Lý do directional (H1-1 thay vì two-tailed):**  
Trong corpus, fine-tuned Qwen 2.5 (77%) > GPT-4o 3-shot (75%) trong Acharya & Ginde (2025) — tuy margin nhỏ nhưng nhất quán với lý thuyết rằng task-specific fine-tuning trên domain data có lợi thế hơn general prompting.

---

## Hypothesis Set 2 — Ngưỡng chất lượng tuyệt đối (Secondary)

Kiểm tra xem LLM-based approaches nói chung có đạt ngưỡng chất lượng thực tế không.

### H2-0 (Null)
> LLM-based approaches (fine-tuning và prompting gộp lại) **không đạt** CTQRS score ≥ 0.70 trên bug reports từ open-source issue trackers.
>
> *Formally:* μ(CTQRS_LLM) < 0.70

### H2-1 (Alternative)
> LLM-based approaches đạt **CTQRS score ≥ 0.70** trên bug reports từ open-source issue trackers.
>
> *Formally:* μ(CTQRS_LLM) ≥ 0.70

**Lý do chọn ngưỡng 0.70:**  
- Ngưỡng này tương đương Cohen's Kappa ≥ 0.70 trong ie_criteria.md (substantial agreement)  
- Yang (2025) đạt CTQRS 0.72 sau SFT; Choi & Yang (2025) đạt 80.5% — hai papers này cung cấp prior evidence rằng ngưỡng 0.70 là khả thi  
- Ngưỡng thấp hơn (0.60) sẽ không có ý nghĩa thực tế; cao hơn (0.80) chỉ 1/5 papers đạt được

---

## Hypothesis Set 3 — Structural Completeness sau LLM Improvement (Tertiary)

Từ GAP-M: completeness là metric thứ hai có mặt trong nhiều papers.

### H3-0 (Null)
> LLM-based improvement tools **không cải thiện đáng kể** structural completeness (OB/EB/S2R fields) của bug reports so với baseline (bản gốc chưa xử lý).
>
> *Formally:* Δcompleteness ≤ 0

### H3-1 (Alternative)
> LLM-based improvement tools **cải thiện đáng kể** structural completeness của bug reports so với baseline.
>
> *Formally:* Δcompleteness > 0

**Evidence từ corpus:**  
Akyol et al. (2026) — completeness tăng từ 7.9% → 96.4% (Δ = +88.5pp). Saha et al. (2026) — cải thiện correctness và completeness so với original reports. Đây là evidence mạnh cho H3-1.

---

## Statistical Test Plan

| Hypothesis | Test dự kiến | Lý do |
|-----------|-------------|-------|
| H1 (fine-tuning vs. prompting) | Mann-Whitney U (non-parametric) | Số lượng papers per group nhỏ (≤ 5), không đảm bảo normality |
| H2 (one-sample threshold) | One-sample Wilcoxon signed-rank test so với μ₀ = 0.70 | So sánh median sample vs. constant threshold |
| H3 (before-after completeness) | Wilcoxon signed-rank test (paired) | Pre/post measurements trên cùng dataset |

> **Lưu ý quan trọng:** Với corpus chỉ N = 15 papers, statistical power rất hạn chế. Kết quả p-value cần được diễn giải cẩn thận — effect size (Cohen's d hoặc rank-biserial r) quan trọng hơn p-value. Nếu không đủ data points, chuyển sang **narrative synthesis** và báo cáo effect direction + confidence interval.

---

## Threats to Validity (liên quan đến Hypotheses)

| Loại threat | Nội dung | Mitigation |
|------------|----------|-----------|
| **Internal** | Các papers dùng dataset khác nhau — so sánh CTQRS không hoàn toàn "apple-to-apple" | Ghi rõ dataset của từng paper; phân tích subgroup theo dataset type |
| **External** | 15/15 papers chỉ dùng tiếng Anh, tập trung Bugzilla | Thừa nhận trong limitations; không tổng quát hóa sang non-English bug reports |
| **Construct** | CTQRS không phải metric chuẩn quốc tế — chỉ được dùng trong subset papers | Report cả CTQRS lẫn completeness% làm convergent validity |
| **Statistical** | N nhỏ → low power, risk of Type II error | Dùng effect size; supplement với qualitative synthesis |

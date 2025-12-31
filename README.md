# LN VN-Translator

![License: AGPLv3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)
![Gemini 3 Pro/Flash](https://img.shields.io/badge/Gemini-3%20Pro%2FFlash-4285F4?logo=google&logoColor=white)
![XML Architecture](https://img.shields.io/badge/Architecture-XML--Based-orange)
![Light Novel](https://img.shields.io/badge/Domain-Light%20Novel-ff69b4)
![Transcreation](https://img.shields.io/badge/Method-Transcreation-success)

> **"Light Novel Localization System driven by Gemini Large-Language Model"**

---

## 📖 Giới thiệu

**LN VN-Translator** là hệ thống **Prompt Engineering** chuyên dụng để dịch Light Novel Nhật-Việt chất lượng cao, được tối ưu hóa cho **Google Gemini Pro/Flash**.

### Tại sao chọn Gemini?

- **1M+ Token Context Window:** Duy trì sự nhất quán tuyệt đối về xưng hô, tính cách nhân vật và thuật ngữ xuyên suốt cả tập truyện dài (Volume) mà không bị "mất trí nhớ" (amnesia).

- **Complex Instruction Following:** Khả năng xử lý kiến trúc XML đa lớp vượt trội, tuân thủ nghiêm ngặt các logic điều kiện (If-Then) về độ táo bạo và an toàn mà không bị "loãng" quy tắc.

- **RAG Stability:** Tra cứu mượt mà kho Knowledge Base 12,559 Kanji/Thuật ngữ mà không gặp hiện tượng "ảo giác" (hallucination) hay quá tải bộ nhớ.

- **Native LN Understanding:** Được huấn luyện trên kho dữ liệu khổng lồ từ Syosetsu, Kakuyomu và Light Novel chính thống, Gemini hiểu sâu sắc các tropes, thuật ngữ Chuunibyou và văn phong Otaku đặc thù ngay từ trong lõi (Zero-shot understanding).

---

## Tính năng Cốt lõi

### RTAS (Relationship Tension & Affection Score)

**Định nghĩa:** Thước đo **Căng thẳng & Tình cảm trong mối quan hệ** (1.0 - 5.0)

**Vai trò:**
- **Điều khiển Đại từ (Pronouns):** Tự động chọn cặp đại từ phù hợp theo mức độ thân mật
  - RTAS 1.0-2.0: `Tôi-Anh` (xa cách, căng thẳng)
  - RTAS 2.0-3.5: `Tớ-Cậu` (bạn bè)
  - RTAS 4.2-5.0: `Em-Anh` (tình cảm)
  
- **Kích hoạt Boldness Module:** Khi RTAS ≥ 4.8 hoặc ≤ 1.2, hệ thống tự động:
  - Bẻ gãy câu để tạo nhịp điệu cảm xúc (Sentence Shattering)
  - Thay thế động từ yếu bằng từ mạnh, giàu cảm giác (Vivid Verb Replacement)
  - Chèn tiếng lóng Gen Z phù hợp ngữ cảnh (Slang Injection)

**Công thức Tính toán RTAS v2.0:**

```
RTAS_FINAL = BASELINE(3.0) + Σ(MODIFIERS)
```

**Các yếu tố Modifier:**

1. **Đại từ Nhật** (俺/お前/君): +0.3 đến +0.7
2. **Kính ngữ** (-chan/-san/-sama): -0.8 đến +0.5  
3. **Trợ từ cuối câu** (よ/ね/な): +0.2 đến +0.4
4. **Từ khóa ngữ cảnh** (好き/殺す/告白): -2.0 đến +1.5
5. **Proxemics** (耳元で/机を挟んで): -0.5 đến +1.2

**Conflict Resolution (Xử lý Xung đột):**

Hệ thống tự động phát hiện và xử lý các pattern đặc biệt:

- **Yandere Paradox**: "殺す + 好き" → RTAS = 5.0 (Twisted Love)
- **Tsundere Flip**: "嫌い + 赤面" → Ưu tiên visual cues
- **Keigo Wall**: "です/ます + 怒り" → RTAS = 1.0 (Cold Anger)
- **Visual Override**: Proxemics > Verbal khi xung đột

**Ví dụ Tính toán:**

```
Input: 「好きだ。ずっと前から、お前のことが好きだった」

Phân tích:
- Baseline: 3.0
- お前 (pronoun): +0.7
- 好き (affection): +1.0
- だ (casual ending): +0.2
→ RTAS = 3.0 + 0.7 + 1.0 + 0.2 = 4.9

Kết quả: Cặp đại từ "Tớ-Cậu", Boldness MAX
```

### Dual-Output Protocol

Cơ chế hiển thị **2 luồng thông tin** song song:

1. **Chatbox (Metadata):** 
   - Phân tích RTAS Score
   - Kỹ thuật áp dụng (Boldness, Sensory, Proxemics)
   - Cặp đại từ đã chọn
   - Lý do quyết định

2. **Canvas (Translation):** 
   - Bản dịch sạch, không có tag kỹ thuật
   - Định dạng chuẩn Light Novel
   - Sẵn sàng để publish

### 🧠 Hybrid Brain-Book Architecture

Hệ thống sử dụng mô hình **"Hybrid Brain-Book"**:

- **Brain (RAM):** 
  - Logic xử lý được nén gọn trong `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml` (17KB)
  - Chứa toàn bộ quy tắc ngữ pháp, cơ chế RTAS, Boldness Module, Anti-Translationese Guardrails
  - Được load vào System Instruction của Gemini

- **Book (HDD):** 
  - Dữ liệu tham chiếu lớn (12,559 Kanji, Sensory Lexicon, Golden Samples)
  - Lưu trong các file `.md` riêng biệt
  - Tra cứu on-demand qua Knowledge Base

### Hybrid Honorifics System

- **Trong hội thoại:** Giữ nguyên kính ngữ Nhật (`Senpai`, `Sensei`, `-san`, `-kun`)
- **Trong trần thuật:** Dùng từ Việt (`Tiền bối`, `Thầy`, `Anh/Chị`)

### Anti-Translationese Guardrails

Tự động loại bỏ các cụm từ "dịch máy":
- ❌ "Một cách nhanh chóng" → ✅ "Vội vã"
- ❌ "Có vẻ như anh buồn" → ✅ "Anh buồn"
- ❌ "Cảm xúc của tôi" → ✅ "Tôi... cảm xúc lộn xộn"

---

## 🚀 Hướng dẫn Cài đặt

### Yêu cầu

- Tài khoản **Gemini Advanced** (hoặc API key với Gemini Pro)
- Truy cập vào tính năng **Gems** (Custom AI)

### Các bước Setup

#### Bước 1: Tạo Gem mới

1. Truy cập [Google AI Studio](https://aistudio.google.com/) hoặc Gemini Advanced
2. Chọn **"Create new Gem"**
3. Đặt tên: `LN VN-Translator`

#### Bước 2: Copy System Instruction

1. Mở file `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml`
2. Copy toàn bộ nội dung (từ `<?xml version="1.0"?>` đến `</VN_TRANSLATOR_LOGIC_CORE>`)
3. Paste vào ô **"Instructions"** của Gem
4. Kích hoạt **"Chế độ Canvas"** trong Default Tools

#### Bước 3: Upload Knowledge Base

Upload các file sau vào ô **"Knowledge"**:

**Bắt buộc (Core):**
- `Reference/14_KANJI_KNOWLEDGE_BASE.md` (2.4MB) — 12,559 Kanji + Hán-Việt
- `Reference/03_SENSORY_LEXICON.md` — Từ điển cảm giác
- `Reference/05_GOLDEN_SAMPLES.md` — 19 mẫu dịch S-Tier

**Tùy chọn (Extended):**
- `Reference/02_BOLDNESS_MODULE_v1.0.md` — Chi tiết về Boldness techniques
- `Reference/06_VISUAL_PROXEMICS_QUICK_REFERENCE.md` — Text-based Proxemics
- `Reference/01_VIETNAMESE_PRONOUN_SYSTEM.md` — Hệ thống đại từ đầy đủ
- `Reference/08_ANTI_TRANSLATIONESE_GUARDRAILS.md` — Quy tắc chống văn dịch

#### Bước 4: Sử dụng

**Input format:**
```
Dịch đoạn sau sang tiếng Việt:

「好きだ。ずっと前から、お前のことが好きだった」
```

**Output:**
- **Chatbox:** Metadata phân tích (RTAS, kỹ thuật, đại từ)
- **Canvas:** Bản dịch hoàn chỉnh

---

## Cấu trúc Thư mục

```
JP-VN/
├── 📄 VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml  # Core logic (23KB)
├── 📄 README.md                                       # Tài liệu này
├── 📄 LICENSE                                         # GNU AGPLv3
│
├── 📚 Reference/ (Knowledge Base)
│   ├── Core Modules (Bắt buộc)
│   │   ├── 14_KANJI_KNOWLEDGE_BASE.md                # 12,559 Kanji + Hán-Việt
│   │   ├── 03_SENSORY_LEXICON.md                     # Từ điển cảm giác
│   │   └── 05_GOLDEN_SAMPLES.md                      # 19 mẫu dịch S-Tier
│   │
│   └── Extended Modules (Tùy chọn)
│       ├── 00_LOCALIZATION_PRIMER_VN.md              # Hướng dẫn bản địa hóa
│       ├── 01_VIETNAMESE_PRONOUN_SYSTEM.md           # Hệ thống đại từ
│       ├── 01A_HYBRID_HONORIFIC_SYSTEM.md            # Kính ngữ hybrid
│       ├── 02_BOLDNESS_MODULE_v1.0.md                # Module táo bạo
│       ├── 04_FORMATTING_STANDARDS.md                # Chuẩn định dạng
│       ├── 06_VISUAL_PROXEMICS_QUICK_REFERENCE.md    # Text-based Proxemics
│       ├── 07_LONG_VOWEL_ROMANIZATION.md             # La-tinh hóa tên riêng
│       ├── 08_ANTI_TRANSLATIONESE_GUARDRAILS.md      # Chống văn dịch
│       ├── 09_THINKING_LOG_ICL.md                    # In-Context Learning
│       ├── 10_REAL_WORLD_CRITIQUE_ICL.md             # Phê bình thực tế
│       ├── 11_RUBY_TEXT_PARSING_ICL.md               # Xử lý Furigana
│       ├── 12_SAFETY_COMPLIANCE_MATRIX.md            # Ma trận an toàn
│       └── 13_COMMON_KANJI_SINO_VN.md                # Kanji thông dụng
│
└── 📖 Examples/ (Ví dụ Dịch thuật)
    ├── sample_chapter_JP.txt                         # Nguyên tác tiếng Nhật
    └── sample_chapter_VN.txt                         # Bản dịch bằng LN VN-Translator
```

---

## Ví dụ So sánh

### Cảnh 1: Tỏ tình (RTAS 4.9)

**Input (Nhật):**
```
「好きだ。ずっと前から、お前のことが好きだった」
```

**Google Translate:**
```
"Tôi thích bạn. Tôi đã thích bạn từ lâu rồi."
```

**LN VN-Translator:**
```
"Tớ thích cậu.
Từ lâu rồi... tớ đã thích cậu."

[Kỹ thuật: Sentence Shattering, RTAS 4.9 → Cặp Tớ-Cậu]
```

---

### Cảnh 2: Khủng hoảng (RTAS 4.8)

**Input (Nhật):**
```
体温計の画面に39.6という数字が表示された。絶望的な気持ちになった。
```

**Google Translate:**
```
"Nhiệt độ 39.6 độ hiển thị trên màn hình nhiệt kế. Tôi cảm thấy tuyệt vọng."
```

**LN VN-Translator:**
```
Màn hình hiện số. 39.6.
Một con số tàn khốc.
Toang thật rồi.

[Kỹ thuật: Vivid Verb + Gen Z Slang (Cấp 3) + Fragmentation]
```

---

## ⚖️ Giấy phép & Tuyên bố Pháp lý

### � GNU Affero General Public License v3.0 (AGPLv3)

Dự án này được phát hành dưới giấy phép **GNU AGPLv3** — một giấy phép mã nguồn mở **Copyleft mạnh** được thiết kế đặc biệt cho các ứng dụng mạng (network services).

### ⚠️ Điều khoản Quan trọng

#### ✅ Bạn ĐƯỢC PHÉP:

- ✅ Sử dụng miễn phí cho mục đích cá nhân
- ✅ Sửa đổi, cải tiến hệ thống prompt
- ✅ Phân phối lại (với điều kiện giữ nguyên license)
- ✅ Sử dụng thương mại (với điều kiện tuân thủ AGPLv3)

#### ❌ Bạn PHẢI TUÂN THỦ:

**🔴 ĐIỀU KHOẢN MẠNG (Network Use Clause):**

> **Nếu bạn sử dụng hệ thống prompt này để cung cấp dịch vụ dịch thuật qua mạng (Web App, API, SaaS, Discord Bot, Telegram Bot, v.v.), bạn PHẢI:**
> 
> 1. **Công khai toàn bộ mã nguồn** của phiên bản prompt đã sửa đổi
> 2. **Cung cấp link tải xuống** mã nguồn cho người dùng cuối
> 3. **Giữ nguyên giấy phép AGPLv3** cho phiên bản đã sửa đổi
> 4. **Ghi rõ những thay đổi** bạn đã thực hiện so với bản gốc

**Ví dụ cụ thể:**
- ❌ **Vi phạm:** Bạn chạy một website dịch Light Novel sử dụng prompt này, nhưng không công khai mã nguồn prompt đã tùy chỉnh.
- ✅ **Tuân thủ:** Bạn chạy website dịch Light Novel, và có một nút "Download Prompt Source Code" trên trang web, dẫn đến GitHub repo chứa phiên bản prompt bạn đang dùng.

### Tại sao chọn AGPLv3?

Chúng tôi coi hệ thống Prompt này là **"Soft Code"** (Mã mềm) — một dạng mã nguồn đặc biệt được thực thi bởi AI thay vì CPU.

**Mục tiêu của chúng tôi:**
1. **Bảo vệ cộng đồng:** Ngăn chặn việc "lấy mã nguồn mở → đóng lại → kiếm tiền mà không chia sẻ"
2. **Khuyến khích đóng góp:** Mọi cải tiến đều phải được chia sẻ lại, tạo vòng lặp phát triển bền vững
3. **Minh bạch:** Người dùng cuối có quyền biết hệ thống đang dùng prompt nào để dịch truyện của họ

### Liên hệ về License

Nếu bạn có nhu cầu sử dụng thương mại không tương thích với AGPLv3 (ví dụ: dịch vụ SaaS đóng nguồn), vui lòng liên hệ:

- **Email:** thangdam7790@gmail.com
- **Subject:** `[LN VN-Translator] Commercial License Inquiry`

Chúng tôi có thể cân nhắc cấp **Dual License** (AGPLv3 + Commercial License) cho các trường hợp đặc biệt.

---

## 📊 Thống kê

- **Core Logic:** 17KB (minified XML)
- **Kanji Database:** 12,559 entries (2.4MB)
- **Golden Samples:** 19 S-Tier examples
- **Sensory Lexicon:** 200+ vivid verb alternatives
- **Supported RTAS Range:** 1.0 - 5.0
- **License:** GNU AGPLv3 (Strong Copyleft)

---

## Đóng góp

Dự án này được phát triển để cộng đồng dịch thuật Light Novel Việt Nam có công cụ chất lượng cao.

**Cách đóng góp:**
1. Fork repo này
2. Tạo branch mới cho tính năng của bạn
3. Commit với message rõ ràng (tuân thủ [Conventional Commits](https://www.conventionalcommits.org/))
4. Tạo Pull Request với mô tả chi tiết

**Ý tưởng đóng góp:**
- Thêm Golden Samples mới từ các tác phẩm khác
- Mở rộng Sensory Lexicon
- Cải thiện Anti-Translationese rules
- Thêm support cho các thể loại Light Novel khác (Isekai, Romance, Action...)
- Tối ưu hóa XML structure để giảm token usage

**Quy tắc đóng góp:**
- Mọi đóng góp phải tuân thủ AGPLv3
- Code phải có comment rõ ràng (tiếng Việt hoặc tiếng Anh)
- Phải test kỹ trước khi tạo PR

---

## Lịch sử Phiên bản

### v10.0 (Current) - 31/12/2024
- ✅ **Rebranding:** → LN VN-Translator
- ✅ **License:** Chuyển sang GNU AGPLv3
- ✅ Tích hợp đầy đủ Boldness Module v1.0
- ✅ Thêm 12,559 Kanji vào Knowledge Base
- ✅ Dual-Output Protocol (Chatbox + Canvas)
- ✅ Text-based Proxemics (không cần multimodal input)

### v9.1 - 23/12/2024
- ✅ Visual Proxemics Quick Reference
- ✅ Long Vowel Romanization Module
- ✅ Safety Compliance Matrix

### v9.0 - 15/12/2024
- ✅ RTAS System hoàn chỉnh
- ✅ Hybrid Honorifics
- ✅ Anti-Translationese Guardrails

---

## � Liên hệ & Hỗ trợ

- **Author:** Thang
- **Email:** thangdam7790@gmail.com
- **GitHub Issues:** [Report bugs or request features](https://github.com/your-repo/issues)
- **GitHub Discussions:** [Community discussions](https://github.com/your-repo/discussions)

---

## Lời cảm ơn

Cảm ơn cộng đồng dịch thuật Light Novel Việt Nam đã đóng góp ý kiến và phản hồi để hoàn thiện hệ thống này.

**Đặc biệt cảm ơn:**
- **Kim Đồng Publishing** — Nguồn cảm hứng về văn phong táo bạo (Nguồn: Làm Bạn với Cô Gái Xinh Nhì Lớp)
- **Cộng đồng Gemini Advanced Users** — Feedback về prompt engineering
- **Các dịch giả đã đóng góp Golden Samples** — Nền tảng chất lượng

---

## 🔗 Tài nguyên Liên quan

- [GNU AGPLv3 Full Text](https://www.gnu.org/licenses/agpl-3.0.en.html)
- [Why AGPL? (GNU Foundation)](https://www.gnu.org/licenses/why-affero-gpl.html)
- [Gemini API Documentation](https://ai.google.dev/docs)
- [Light Novel Database (LNDB)](https://lndb.info/)

---

<div align="center">

**Licensed under GNU AGPLv3 — Free as in Freedom**

⭐ Nếu dự án hữu ích, hãy cho một Star!

</div>

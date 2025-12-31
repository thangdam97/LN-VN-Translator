# MODULE 08: RÀO CẢN CHỐNG TRANSLATIONESE

**CHIẾN LƯỢC:** Học tập Tương phản Theo Ngữ cảnh (Contrastive ICL)

Mô hình phải học những gì cần **TRÁNH** bằng cách xem "Đầu ra AI Tồi" so với "Đầu ra Con người Đúng" cạnh nhau. Điều này buộc tính toán **gradient cải thiện**.

---

## HƯỚNG DẪN QUAN TRỌNG

Trước khi dịch mỗi câu, kiểm tra tinh thần:
1. Điều này nghe giống **người Việt Nam nói** hay **máy dịch**?
2. Một người bản ngữ có nói điều này **tự nhiên** trong cuộc trò chuyện không?
3. Tôi đang sử dụng **từ điển** hay **ngôn ngữ sống**?

Nếu câu trả lời là "máy dịch" hoặc "từ điển", **DỬNG LẠI và viết lại**.

---

## THƯ VIỆN CẶP TƯƠNG PHẢN

Nghiên cứu các mẫu này cẩn thận. Cột [SAI_AI] hiển thị những gì bạn **KHÔNG BAO GIỜ ĐƯỢC** tạo ra. Cột [ĐÚNG_NGƯỜI] hiển thị tiếng Việt tự nhiên bạn **PHẢI** tạo ra.

### 1. Vi-rút "Phóng đại Phó từ" ("Một cách...")

**Vấn đề:** AI dịch phó từ "-ly" hoặc tiếng Nhật "に" thành "một cách + tính từ". Điều này máy móc và không tự nhiên.

**Giải pháp:** Sử dụng phó từ trực tiếp, động từ có cách thức tích hợp, hoặc tái cấu trúc câu.

| NGUỐN (JP) | ❌ SAI_AI (Translationese) | ✅ ĐÚNG_NGƯỜI (VN Tự nhiên) |
|:------------|:---------------------------|:---------------------------|
| 急いで走った | Anh ấy chạy **một cách nhanh chóng**. | Anh ấy **vội vã** chạy đi. / Anh **phóng** đi. |
| 幸せに暮らす | Sống **một cách hạnh phúc**. | Sống **hạnh phúc**. / Sống **an vui**. |
| 不自然に笑う | Cười **một cách gượng gạo**. | Cười **gượng**. / Nụ cười **sượng trân**. |
| 静かに歩く | Đi bộ **một cách yên lặng**. | Đi **lặng lẽ**. / Bước chân **thầm lặng**. |
| 優しく話す | Nói **một cách dịu dàng**. | Nói **nhẹ nhàng**. / Giọng **dịu dàng**. |
| 真剣に考える | Suy nghĩ **một cách nghiêm túc**. | Suy nghĩ **nghiêm túc**. / **Trầm ngâm** suy nghĩ. |
| 丁寧に説明する | Giải thích **một cách cẩn thận**. | Giải thích **tỉ mỉ**. / **Tận tình** giải thích. |
| 突然に現れる | Xuất hiện **một cách đột ngột**. | **Bỗng nhiên** xuất hiện. / **Thình lình** hiện ra. |

**Quy tắc:** Cấm "một cách" trừ khi thực sự cần thiết để nhấn mạnh. Sử dụng:
- Phó từ trực tiếp: vội vã, lặng lẽ, nhẹ nhàng
- Động từ cách thức: phóng (rush), rón rén (tiptoe), lẳng lặng (silently)
- Tái cấu trúc: "Nói một cách dịu dàng" → "Giọng dịu dàng"

---

### 2. Vi-rút "Thể Bị động" (Quá tải "Bị/Được")

**Vấn đề:** Tiếng Nhật thích thể bị động. Tiếng Việt ghét nó trừ khi tiêu cực hoặc nhấn mạnh người nhận.

**Giải pháp:** Sử dụng thể chủ động. Chỉ dùng "bị" cho hành động tiêu cực, "được" cho hành động tích cực khi nhấn mạnh người nhận.

| SOURCE (JP) | ❌ BAD_AI (Translationese) | ✅ GOOD_HUMAN (Natural VN) |
|:------------|:---------------------------|:---------------------------|
| 頭を撫でられた | Tôi **được** cô ấy xoa đầu. | Cô ấy xoa đầu tôi. *(Active)* |
| 怒られた | Tôi **bị** tức giận. | Tôi bị mắng. / Bị ăn chửi. |
| 鍵がかけられている | Cửa **đang được** khóa. | Cửa khóa rồi. / Cửa đã khóa. |
| 褒められた | Tôi **được** khen ngợi. | Cô ấy khen tôi. / Được khen. *(OK if emphasizing)* |
| 見られている | Tôi **đang được** nhìn. | Họ đang nhìn tôi. / Bị dòm ngó. |
| 助けられた | Tôi **được** giúp đỡ. | Anh ấy giúp tôi. / Được anh ấy cứu. |
| 呼ばれた | Tôi **được** gọi. | Cô ấy gọi tôi. / Có người gọi. |
| 選ばれた | Tôi **được** chọn. | Họ chọn tôi. / Được chọn. *(OK)* |

**Quy tắc:**
- **Mặc định:** Sử dụng thể chủ động (Chủ ngữ + Động từ + Tân ngữ)
- **"Bị":** Chỉ cho hành động tiêu cực (bị mắng, bị đánh, bị lừa)
- **"Được":** Chỉ khi nhấn mạnh sự may mắn của người nhận (được khen, được chọn)
- **Không bao giờ:** "Đang được" (luôn nghe máy móc)

---

### 3. Vi-rút "Sở hữu" (Spam "Của")

**Vấn đề:** AI chèn "của" (of) cho mỗi "の" (no) tiếng Nhật. Tiếng Việt bỏ nó để tăng sự thân mật và dòng chảy.

**Giải pháp:** Bỏ "của" trừ khi cần thiết để rõ ràng hoặc nhấn mạnh. Sử dụng sở hữu trực tiếp.

| SOURCE (JP) | ❌ BAD_AI (Translationese) | ✅ GOOD_HUMAN (Natural VN) |
|:------------|:---------------------------|:---------------------------|
| 俺の彼女 | Bạn gái **của** tôi. | Bạn gái tôi. / Người yêu tôi. |
| 学校の正門 | Cổng chính **của** trường. | Cổng trường. / Cổng chính trường. |
| 心の痛み | Nỗi đau **của** tim. | Nỗi đau trong tim. / Tim nhói đau. |
| 彼女の笑顔 | Nụ cười **của** cô ấy. | Nụ cười cô ấy. / Cô ấy cười. |
| 母の料理 | Món ăn **của** mẹ. | Món mẹ nấu. / Đồ ăn mẹ làm. |
| 友達の家 | Nhà **của** bạn. | Nhà bạn. / Nhà bạn tôi. |
| 先生の話 | Câu chuyện **của** thầy. | Chuyện thầy kể. / Lời thầy nói. |
| 彼の目 | Đôi mắt **của** anh ấy. | Đôi mắt anh ấy. / Mắt anh ấy. |

**Quy tắc:**
- **Bỏ "của":** Cho các mối quan hệ thân mật (bạn gái tôi, nhà bạn)
- **Giữ "của":** Để nhấn mạnh hoặc ngữ cảnh trang trọng (tài sản của công ty)
- **Tái cấu trúc:** "Nỗi đau của tim" → "Tim nhói đau" (dùng động từ thay thế)

---

### 4. Vi-rút "Danh từ Trừa tượng" (Ngôn ngữ Học thuật)

**Vấn đề:** AI sử dụng danh từ trừa tượng từ từ điển thay vì động từ/tính từ cụ thể.

**Giải pháp:** Sử dụng động từ và tính từ. Tiếng Việt ưu tiên hành động hơn trừa tượng.

| SOURCE (JP) | ❌ BAD_AI (Translationese) | ✅ GOOD_HUMAN (Natural VN) |
|:------------|:---------------------------|:---------------------------|
| 彼女の美しさ | **Vẻ đẹp** của cô ấy. | Cô ấy **đẹp** quá. / Cô ấy **xinh** thật. |
| その重要性 | **Tầm quan trọng** của nó. | Việc này **quan trọng** lắm. / **Rất quan trọng**. |
| 幸福感 | **Cảm giác hạnh phúc**. | Cảm thấy **hạnh phúc**. / **Sung sướng** quá. |
| 不安感 | **Cảm giác bất an**. | Cảm thấy **bất an**. / **Lo lắng** quá. |
| 疲労感 | **Cảm giác mệt mỏi**. | Thấy **mệt** quá. / **Kiệt sức** rồi. |
| 満足感 | **Sự hài lòng**. | **Hài lòng** quá. / **Vừa lòng** rồi. |

**Quy tắc:**
- Cấm: "Vẻ đẹp của," "Tầm quan trọng của," "Sự hài lòng"
- Dùng: Tính từ/động từ trực tiếp + "quá/lắm/thật" để nhấn mạnh

---

### 5. Vi-rút "Dịch Theo Từ" (Từ-cho-Từ)

**Vấn đề:** AI dịch thành ngữ và cách diễn đạt theo nguyên văn thay vì tìm tương đương tiếng Việt.

**Giải pháp:** Sử dụng thành ngữ và cách diễn đạt tiếng Việt tự nhiên.

| SOURCE (JP) | ❌ BAD_AI (Translationese) | ✅ GOOD_HUMAN (Natural VN) |
|:------------|:---------------------------|:---------------------------|
| 胸がドキドキする | Tim **đập thình thịch**. | Tim **đập loạn xạ**. / Tim **hồi hộp**. |
| 顔が赤くなる | Mặt **trở nên đỏ**. | Mặt **đỏ bừng**. / **Đỏ mặt** lên. |
| 目が輝く | Mắt **tỏa sáng**. | Mắt **sáng rực**. / Mắt **long lanh**. |
| 頭が真っ白 | Đầu **hoàn toàn trắng**. | Đầu **óc trống rỗng**. / **Ngơ ngác** hết cả. |
| 耳が痛い | Tai **đau**. | **Nghe vào tai** như dao cắt. / Lời **đau tai**. |
| 手に汗握る | **Nắm mồ hôi trong tay**. | **Hồi hộp** đến **toát mồ hôi**. |

**Quy tắc:** Đừng dịch thành ngữ theo nguyên văn. Tìm tương đương tiếng Việt hoặc tái cấu trúc.

---

## THAM CHIẾU PHONG CÁCH (KIỂM TRA VIBỆ)

**Phong cách Đầu ra Mục tiêu:** Đọc đoạn văn sau để hiệu chỉnh thanh ghi ngôn ngữ của bạn. Đừng dịch đoạn này, chỉ cần **bắt chước nhịp điệu, mật độ từ vựng và cấu trúc câu** của nó.

> **Reference Passage:**
>
> *Nắng chiều đổ dài trên sân trường vắng lặng. Gió luồn qua kẽ lá, mang theo chút hơi lạnh se sắt cuối đông khiến người ta khẽ rùng mình. Cậu ấy đứng đó, nụ cười vẫn rạng rỡ như ngày đầu tiên, nhưng trong ánh mắt đã thoáng nét ưu tư của một người vừa bước qua ngưỡng cửa trưởng thành. Không cần lời hoa mỹ, chỉ cần một cái nắm tay siết nhẹ cũng đủ để thay cho ngàn vạn câu từ.*
>
> *Có những khoảnh khắc trong đời, ta không cần giải thích, không cần phân tích. Chỉ cần cảm nhận. Chỉ cần để tim mình rung động theo nhịp của thời gian, để hơi thở hòa quyện với gió, để ánh mắt nói lên tất cả những gì lời nói không thể diễn tả.*

**Đặc điểm Chính cần Bắt chước:**
- **Câu ngắn gọn, sắc sảo:** "Chỉ cần cảm nhận. Chỉ cần để tim mình rung động."
- **Động từ cảm giác:** đổ, luồn, siết, rung động, hòa quyện
- **Bỏ xưng hô:** "Không cần lời hoa mỹ" (không phải "Chúng ta không cần")
- **Hình ảnh thơ mộng:** "gió luồn qua kẽ lá," "hơi lạnh se sắt"
- **Nhịp điệu tự nhiên:** Kết hợp câu ngắn và trung bình, không có cấu trúc học thuật dài

---

## KẾ HOẠCH PHONG CÁCH TRƯỚC KHI DỊCH

**HƯỚNG DẪN:** Trước khi dịch mỗi chương, thực hiện "Quét Bẫy Translationese" tinh thần:

1. **Xác định 3-5 câu** có khả năng dẫn đến:
   - Cấu trúc "Một cách"
   - Thể bị động vụng về (spam "được/bị")
   - Lạm dụng "Của"
   - Phóng đại danh từ trừa tượng

2. **Viết phiên bản "Sai" trong đầu** (những gì từ điển sẽ tạo ra)

3. **Viết phiên bản "Đúng"** (những gì con người sẽ nói)

4. **Tiến hành dịch** với tư duy "Đúng"

**Example Internal Dialogue:**

```
[STYLE_PLAN]
- Trap: "彼のことが好き"
  Bad: "Việc thích anh ấy"
  Fixed: "Tình cảm dành cho anh ấy" / "Thích anh ấy"

- Trap: "嬉しくてたまらない"
  Bad: "Vui sướng một cách không chịu nổi"
  Fixed: "Vui sướng tột độ" / "Sướng rơn"

- Trap: "彼女の優しさ"
  Bad: "Sự dịu dàng của cô ấy"
  Fixed: "Cô ấy dịu dàng thật" / "Cô ấy hiền quá"
```

---

## CỤM TỪ CẤM (DANH SÁCH ĐEN TỪ ĐIỂN)

Các cụm từ sau đây **Bị CẤM**. Chúng đánh dấu bạn là máy dịch:

### Phóng đại Học thuật/Trang trọng
- ❌ "Hiệu suất chi phí" → ✅ "Tiếc tiền" / "Đáng tiền"
- ❌ "Thực hiện hành động" → ✅ "Làm" / "Hành động"
- ❌ "Tiến hành kiểm tra" → ✅ "Kiểm tra" / "Xem xét"
- ❌ "Đưa ra quyết định" → ✅ "Quyết định"
- ❌ "Thực thi kế hoạch" → ✅ "Thực hiện" / "Làm theo kế hoạch"

### Cấu trúc Máy móc
- ❌ "Một cách + [adjective]" → ✅ Use direct adverb or restructure
- ❌ "Sự + [adjective]" → ✅ Use adjective directly
- ❌ "Việc + [verb]" → ✅ Use verb directly
- ❌ "Cảm giác + [adjective]" → ✅ "Cảm thấy + [adjective]"
- ❌ "Trở nên + [adjective]" → ✅ "[Adjective] + lên/ra"

### Spam Thể Bị động
- ❌ "Đang được + [verb]" → ✅ Use active voice
- ❌ "Được + [verb]" (when not emphasizing) → ✅ Active voice
- ❌ "Bị + [neutral verb]" → ✅ Active voice or use "bị" only for negative

---

## TỰ KIỂM TRA CHẤT LƯỢNG

Sau khi dịch mỗi đoạn văn, hỏi bản thân:

1. ✅ **Một thiếu niên Việt Nam có nói thế này không?**
   - Nếu không → Viết lại bình dân hơn

2. ✅ **Tôi có thể đọc to đoạn này một cách trơn tru không?**
   - Nếu không → Câu quá dài hoặc vụng về

3. ✅ **Tôi có dùng quá 2 "một cách" trong đoạn này không?**
   - Nếu có → Xóa chúng

4. ✅ **Tôi có dùng quá 3 "của" trong đoạn này không?**
   - Nếu có → Xóa những cái không cần thiết

5. ✅ **Tôi có dùng danh từ trừa tượng thay vì động từ không?**
   - Nếu có → Chuyển sang động từ/tính từ

6. ✅ **Điều này nghe giống con người hay sách giáo khoa?**
   - Nếu sách giáo khoa → Đơn giản hóa và thêm cảm xúc

---

## PHẦN BỔ SUNG: SLICE-OF-LIFE HỌC ĐƯỜNG (REAL-WORLD FEEDBACK)

**Ngữ cảnh:** Các ví dụ sau đây được trích xuất từ dự án dịch thực tế, áp dụng RLHF (Reinforcement Learning from Human Feedback) để trau chuốt ngôn từ cho thể loại học đường đời thường.

### 6. Vi-rút "Thể Bị Động Lịch Sự Thái Quá"

**Vấn đề:** Trong hội thoại học đường, việc sử dụng thể bị động lịch sự ("Nếu chị không chê") nghe rất máy móc và không tự nhiên, đặc biệt khi người nói có xu hướng bề trên.

**Giải pháp:** Chuyển sang thể chủ động, thể hiện sự tự tin và thân mật hơn.

| NGỮ CẢNH | ❌ SAI_AI (Bị động - Máy móc) | ✅ ĐÚNG_NGƯỜI (Chủ động - Tự nhiên) |
|:----------|:------------------------------|:------------------------------------|
| Mời về nhà | "Nhà em cách đây không tới 2 phút đi bộ đâu. **Nếu chị không chê**, chị về đó nghỉ ngơi một lát nhé?" | "Nhà em cách đây không tới 2 phút đi bộ đâu. **Nếu tiện**, chị về đó nghỉ ngơi một lát nhé?" |

**Quy tắc:**
- **Bị động ("không chê"):** Nghe sợ sệt, thiếu tự tin
- **Chủ động ("tiện"):** Tự nhiên, thân thiện, phù hợp với học sinh

---

### 7. Vi-rút "Từ Vựng Văn Viết/Phim Lồng Tiếng"

**Vấn đề:** Một số từ Hán Việt hoặc từ ngữ trang trọng nghe giống phim lồng tiếng hơn là lời nói tự nhiên của học sinh.

**Giải pháp:** Ưu tiên lối hành văn đời thường cho bối cảnh slice-of-life.

| NGỮ CẢNH | ❌ SAI_AI (Văn viết/Lồng tiếng) | ✅ ĐÚNG_NGƯỜI (Đời thường) |
|:----------|:--------------------------------|:---------------------------|
| Nói về sở thích | "Những thứ có mùi thơm thì **nhân loại** ai mà chẳng thích!" | "Đồ thơm thì **ai trên đời** mà chả thích!" / "Là người thì ai chả thích đồ thơm!" |

**Quy tắc:**
- **Cấm:** "Nhân loại" (Jinrui) - quá trang trọng, giống phim khoa học
- **Dùng:** "Ai trên đời," "Là người thì" - tự nhiên, gần gũi

---

### 8. Vi-rút "Ẩn Dụ Dài Dòng Không Phù Hợp Ngữ Cảnh"

**Vấn đề:** Một số ẩn dụ dịch sát nghĩa nhưng quá dài dòng hoặc không phù hợp với môi trường học đường.

**Giải pháp:** Điều chỉnh ẩn dụ cho phù hợp với ngữ cảnh cụ thể (lớp học, bạn bè).

| NGỮ CẢNH | ❌ SAI_AI (Ẩn dụ dài/Không phù hợp) | ✅ ĐÚNG_NGƯỜI (Phù hợp môi trường) |
|:----------|:------------------------------------|:-----------------------------------|
| Châm biếm bạn | "Cậu cứ đóng vai **quản lý cấp trung** trong lớp suốt còn gì." | "Cậu cứ làm như mình là **lớp trưởng** không bằng." / "Cậu cứ đi **lo chuyện bao đồng** suốt." |

**Quy tắc:**
- **Giữ nguyên:** Nếu ẩn dụ nhấn mạnh tính cách nhân vật (ví dụ: toan tính)
- **Điều chỉnh:** Nếu ngữ cảnh là học đường → dùng từ ngữ học đường ("lớp trưởng" thay vì "quản lý cấp trung")

---

### 9. Vi-rút "Hán Việt Quá Chuyên Môn Trong Hội Thoại"

**Vấn đề:** Từ Hán Việt chuyên môn/khoa học trong hội thoại đời thường nghe rất lạ tai, trừ khi nhân vật có archetype đặc biệt (mọt sách, lạnh lùng).

**Giải pháp:** Ưu tiên từ ngữ thuần Việt cho hội thoại thông thường. Chỉ dùng Hán Việt khi đã xác định archetype nhân vật.

| NGỮ CẢNH | ❌ SAI_AI (Hán Việt chuyên môn) | ✅ ĐÚNG_NGƯỜI (Thuần Việt tự nhiên) |
|:----------|:--------------------------------|:------------------------------------|
| Giới thiệu quan hệ | "**Hệ nhị đẳng**. Đó là chị gái tôi." | "**Họ hàng gần**. Chị gái tôi đấy." |

**Quy tắc:**
- **Mặc định:** Dùng từ thuần Việt ("họ hàng gần")
- **Ngoại lệ:** Nếu nhân vật là kiểu mọt sách/lạnh lùng → có thể giữ Hán Việt ("Hệ nhị đẳng")
- **Bonus:** Khi dùng Hán Việt cho nhân vật cool → áp dụng **Zero-pronoun Mandate** và **nhịp Staccato** (câu ngắn, sắc sảo)

---

### 10. Vi-rút "Thuật Ngữ Kỹ Thuật Trong Hội Thoại Đời Thường"

**Vấn đề:** Sử dụng thuật ngữ nặng tính kỹ thuật (như "hiệu suất") trong hội thoại học sinh nghe như robot, thiếu cảm xúc.

**Giải pháp:** Thay bằng danh từ gần gũi, mang tính con người hơn.

| NGỮ CẢNH | ❌ SAI_AI (Thuật ngữ kỹ thuật) | ✅ ĐÚNG_NGƯỜI (Gần gũi, con người) |
|:----------|:-------------------------------|:-----------------------------------|
| Đánh giá năng lực | "Giá mà chị có thể xử lý mọi việc nhạy bén hơn nhỉ... Dạo này **hiệu suất làm việc** của chị đang giảm sút trầm trọng." | "Giá mà chị có thể xử lý mọi việc nhạy bén hơn nhỉ... Dạo này **năng lực công việc** của chị đang giảm sút trầm trọng." |

**Quy tắc:**
- **Cấm:** "Hiệu suất" (efficiency) - nghe như đánh giá máy móc
- **Dùng:** "Năng lực" (capability) - mang tính con người, cảm xúc

---

### 11. Vi-rút "Chi Tiết Thừa Từ Tiếng Nhật"

**Vấn đề:** Dịch sát từng chi tiết từ tiếng Nhật làm câu văn dài dòng, không tự nhiên trong tiếng Việt.

**Giải pháp:** Mạnh dạn cắt bỏ chi tiết thừa để câu trôi chảy hơn, đặc biệt trong hội thoại học sinh.

| NGỮ CẢNH | ❌ SAI_AI (Dịch sát - Dài dòng) | ✅ ĐÚNG_NGƯỜI (Cắt gọn - Tự nhiên) |
|:----------|:--------------------------------|:-----------------------------------|
| Hỏi tình trạng | "Ố? Sao thế Amemoto, **đang ở chế độ** hết pin à?" | "Ố? Sao thế Amemoto, hết pin rồi à?" |
| Phàn nàn đồ ăn | "Nói sao nhỉ... **lượng đồ** ăn trưa thế này có hơi ít quá không ạ?" | "Nói sao nhỉ... ăn trưa thế này có hơi ít quá không ạ?" |

**Quy tắc:**
- **Cắt bỏ:** Các cụm từ dài dòng không cần thiết ("đang ở chế độ," "lượng đồ")
- **Giữ lại:** Ý nghĩa cốt lõi và cảm xúc
- **Mục tiêu:** Câu ngắn gọn, tự nhiên như học sinh Việt nói chuyện

---

### 12. ĐIỂM SÁNG: Hán Việt Trong Mô Tả Thẩm Mỹ (KHUYẾN KHÍCH)

**Ngược lại với hội thoại, việc sử dụng Hán Việt trong phần tự sự mô tả vẻ đẹp/cảm xúc là RẤT TỐT.**

**Ví dụ xuất sắc:**

> "Cái cách chị ấy vén những lọn tóc quanh tai rồi khẽ nghiêng đầu, tại sao không hề mang lại cảm giác dễ thương mà lại thấy **tinh xảo** đến vậy nhỉ? Đúng là một loại **ma thuật khó giải**."

**Tại sao tốt:**
- **"Tinh xảo"** (Hán Việt) - tạo cảm giác tinh tế, cao cấp hơn "khéo léo"
- **"Ma thuật khó giải"** - thơ mộng, phù hợp với tự sự Light Novel
- **Ngữ cảnh:** Tự sự (narrative), không phải hội thoại

**Quy tắc:**
- ✅ **Hán Việt trong tự sự:** Tăng tính thẩm mỹ (tinh xảo, ưu tư, rạng rỡ)
- ❌ **Hán Việt trong hội thoại:** Chỉ dùng cho archetype đặc biệt

---

## CHECKLIST SLICE-OF-LIFE HỌC ĐƯỜNG

Trước khi hoàn thiện bản dịch cho cảnh học đường, kiểm tra:

1. ✅ **Hội thoại có nghe như học sinh Việt nói chuyện không?**
   - Nếu không → Cắt bỏ chi tiết thừa, đơn giản hóa

2. ✅ **Có dùng từ "nhân loại," "hệ nhị đẳng," "hiệu suất" không?**
   - Nếu có → Thay bằng từ đời thường

3. ✅ **Có lạm dụng thể bị động lịch sự không?**
   - Nếu có → Chuyển sang chủ động

4. ✅ **Ẩn dụ có phù hợp với môi trường học đường không?**
   - Nếu không → Điều chỉnh cho phù hợp

5. ✅ **Phần tự sự có dùng Hán Việt để tăng tính thẩm mỹ không?**
   - Nếu chưa → Cân nhắc thêm (tinh xảo, ưu tư, rạng rỡ)

---

### 13. Vi-rút "Lặp Cảm Thán" (Interjection Spam)

**Vấn đề:** AI dùng lại cùng một từ cảm thán ("Trời ạ", "Trời ơi") hoặc dịch cứng cảm thán tiếng Nhật (まったく → "Tuyệt đối") gây nhàm chán và máy móc.

**Giải pháp:** Xoay tua (rotate) từ cảm thán và dùng bản dịch tự nhiên phù hợp với archetype nhân vật.

| NGUỒN (JP) | ❌ SAI_AI (Lặp từ/Dịch cứng) | ✅ ĐÚNG_NGƯỜI (Đa dạng/Tự nhiên) |
|:-----------|:-----------------------------|:----------------------------------|
| まったく | "**Tuyệt đối**, thật rắc rối." | "**Haiz**, rắc rối thật." / "**Thiệt tình**, khổ ghê." |
| ええ！？ | "**Trời ạ**!? Thật sao!?" | "**Ủa**!? Thật sao!?" / "**Hả**!?" / "**Gì cơ**!?" |
| うそ！？ | "**Trời ạ**!? Không thể nào!" | "**Không đời nào**!?" / "**Điêu**!?" / "**Ảo thế**!?" |
| もう | "**Trời ơi**, lại nữa à..." | "**Gớm**, lại nữa à..." / "**Haiz**, lại rồi..." |
| あら | "**Trời ạ**, thật bất ngờ." | "**Ái chà**..." / "**Ô kìa**..." / "**Chẳng hay**..." |

**Quy tắc Chống Lặp:**
1. **Đếm từ cảm thán:** Nếu "Trời ạ/Trời ơi" xuất hiện > 2 lần trong 1 trang → **BẮT BUỘC** thay thế
2. **Xoay tua theo mức độ:**
   - Nhẹ: Ơ? / Ủa? / Hả? / Gì cơ?
   - Vừa: Cái gì? / Đùa à? / Thật á? / Ảo thế?
   - Mạnh: Vãi! / Điêu! / Gì vậy trời!
3. **Match archetype:**
   - Ojou-sama: "Ái chà", "Ô kìa", "Chẳng hay"
   - Gyaru/Gen Z: "Vãi", "Điêu", "Ảo thế"
   - Delinquent: "Khỉ thật", "Chết tiệt"
   - Onee-san: "Ái chà chà", "Ôi dào"

**Ví dụ Sửa Lỗi:**

❌ **Lặp từ (SAI):**
```
"Trời ạ!? Thật sao!?"
"Trời ạ!? Nghiêm túc đấy à!?"
"Trời ạ! Không thể tin nổi!"
```

✅ **Đa dạng (ĐÚNG):**
```
"Ủa!? Thật sao!?"
"Không đời nào!? Nghiêm túc đấy à!?"
"Điêu vãi! Không tin nổi!"
```

**Tham khảo:** Xem `15_VIETNAMESE_EXPRESSION_MAPPING.md` để có danh sách đầy đủ các biến thể cảm thán theo archetype.

---

## LỜI NHẮC CUỐI CÙNG

**Mục tiêu của bạn KHÔNG PHẢI dịch từ. Mục tiêu của bạn là làm cho độc giả Việt Nam QUÊN rằng họ đang đọc bản dịch.**

Mọi câu nên nghe như nó được **viết gốc bằng tiếng Việt** bởi người bản ngữ.

**Khi nghi ngờ:** Chọn phiên bản mà một người bạn Việt Nam sẽ nhắn tin cho bạn, không phải những gì từ điển sẽ cho bạn.

**ĐẶC BIỆT CHO SLICE-OF-LIFE HỌC ĐƯỜNG:** Hãy tưởng tượng bạn đang nghe hai học sinh Việt trò chuyện trong giờ ra chơi. Nếu câu thoại nghe không giống thế → viết lại!

**ĐẶC BIỆT CHO CẢM THÁN:** Đừng lặp lại cùng một từ cảm thán > 2 lần trong 1 trang. Xoay tua các biến thể để giữ sự tươi mới và tự nhiên!

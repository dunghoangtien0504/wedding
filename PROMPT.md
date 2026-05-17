# PROMPT THIẾT KẾ — THIỆP CƯỚI TUẤN VIỆT × NHẬT HƯỜNG

> Bản tóm tắt ý đồ thiết kế, dùng để brief lại cho mọi lần render / chỉnh sửa tiếp theo.

---

## 1. Định vị (Positioning)

**Hướng:** *Editorial Couture × Vietnamese Heritage*
Mỗi màn hình phải đẹp như một trang trong tạp chí cưới (Vogue Weddings, Brides, Martha Stewart), nhưng giữ được hồn Á Đông tinh tế — không sến, không "wedding template", không lạm dụng chữ thư pháp.

**Cảm xúc mục tiêu khi mở thiệp:**
1. 0–2 giây: *"Wow, sang."* — khoảng trắng nhiều, layout có nhịp.
2. 3–8 giây: *"Ấm áp, có cảm xúc."* — ánh sáng vàng champagne, chữ viết tay nhẹ.
3. 9–30 giây: *"Có gu, không đụng hàng."* — chi tiết botanical line-art, dấu Song Hỷ ẩn dụ, typography editorial.

**Câu thần chú khi render:** *"Less is luxury. Mỗi điểm nhấn phải có lý do."*

---

## 2. Bảng màu (Color System) — hài hoà với hình ảnh

Lấy trực tiếp từ ảnh studio + ảnh phông đỏ Song Hỷ:

| Vai trò | Tên | HEX | Lấy từ |
|---|---|---|---|
| Nền chính | **Ivory Silk** | `#FBF6EC` | Váy cưới & phông studio sáng |
| Nền phụ ấm | **Champagne Mist** | `#EDE0CB` | Ánh nắng vàng nhẹ trong ảnh |
| Mực chính | **Lacquer Ink** | `#1B1410` | Vest chú rể, độ sâu của ảnh |
| Mực phụ | **Smoke Brown** | `#5E4A3A` | Tóc & shadow trong ảnh |
| Điểm nhấn 1 | **Antique Gold** | `#A8843A` | Foil sang trọng, không loè |
| Điểm nhấn 1b | **Light Gold** | `#D9B96B` | Gradient shimmer |
| Điểm nhấn 2 (di sản) | **Lacquer Red** | `#6B1F1F` | Phông Song Hỷ truyền thống |
| Điểm nhấn 3 (botanical) | **Sage Olive** | `#7E8A60` | Lá trong bó hoa cưới |
| Điểm nhấn 4 (mềm) | **Powder Blush** | `#E8D2C8` | Đèn lồng giấy & da người |

**Quy tắc dùng:**
- 70% ivory + 20% champagne + 6% gold + 3% red + 1% sage. Không bao giờ đảo.
- Đỏ chỉ xuất hiện ở: con dấu Song Hỷ, đèn lồng minh hoạ, RSVP confirm.
- Gold dùng cho đường kẻ chỉ, foil chữ ký, viền khung — **không** dùng cho nền lớn.

---

## 3. Typography

**Editorial — không xài Google Fonts cũ kĩ:**

| Vai trò | Font | Lý do |
|---|---|---|
| Display (tên cô dâu chú rể) | **Italiana** hoặc **Cormorant Garamond Light** | High-contrast serif, mỏng, sang trọng |
| Script (lời mời thân mật) | **Pinyon Script** hoặc **Allura** | Thanh thoát hơn Great Vibes — đỡ "thiệp mẫu" |
| Body | **Inter Tight** weight 300–400 | Nhẹ, hiện đại, dễ đọc tiếng Việt |
| Eyebrow / caption | **Inter Tight UPPERCASE**, letter-spacing 0.4em | Tag editorial |
| Số (countdown, ngày) | **Cormorant** + `font-variant-numeric: tabular-nums` | Không nhảy chữ |

**Hierarchy:**
- H1 tên: 72–96px, letter-spacing -0.02em (siết, không thưa)
- Subheading script: 28–38px
- Body Việt: 15–16px, line-height 1.75
- Eyebrow: 10px, letter-spacing 0.45em, uppercase

---

## 4. Layout & Bố cục

**Phá cách so với bản cũ:**
- Bản cũ căn giữa 100% → trông giống nhiều thiệp khác.
- Bản mới: **layout editorial bất đối xứng có chủ ý**.
  - Ảnh tràn cạnh (full-bleed) một bên, caption nhỏ căn trái lề.
  - Tên cô dâu & chú rể không nằm cùng hàng — đặt so le như poster phim.
  - Có một "magazine spread" cho phần album: 1 ảnh lớn + 2 ảnh nhỏ + paragraph text.
- Container max-width 560px (giữ mobile-first), nhưng **bên trong dùng grid 12 cột** để các phần tử có "neo" lệch nhau.
- Spacing dùng nhịp 4/8/16/24/40/64 — không tùy hứng.

---

## 5. Hình ảnh — xử lý

- **Crop editorial**: ưu tiên crop dọc 3:4 hoặc 4:5 cho hero.
- **Tone-mapping nhẹ**: tăng warmth +5, giảm saturation -10 → ăn rơ với champagne palette.
- **Overlay nhẹ**: gradient ivory 0→8% từ dưới lên để chữ caption nổi.
- **Khung mat**: ảnh hero có viền trong (inset border) gold 1px cách mép 14px — gợi khung tranh.
- Ảnh phông đỏ Song Hỷ: dùng riêng cho section "Lễ Vu Quy" / phần truyền thống.

---

## 6. Motion (chuyển động)

**Quy tắc vàng:** chuyển động phải kể chuyện, không trang trí.

| Element | Animation | Duration | Easing |
|---|---|---|---|
| Hero text | Reveal + slight blur-out 4px → 0 | 1200ms | spring (.16,1,.3,1) |
| Tên đôi | Stagger 200ms giữa Việt và Hường | 900ms each | spring |
| Đường kẻ gold | Vẽ từ giữa ra hai bên (width 0→100%) | 1400ms | ease-out |
| Hoa rơi (petal) | Giữ — nhưng giảm density xuống còn 6 cánh, opacity 0.3 | infinite | linear |
| Image reveal | Mask reveal từ dưới lên (clip-path) | 1500ms | spring |
| Countdown tick | Flip card nhẹ (rotateX) thay vì pop | 400ms | ease-out |

Tôn trọng `prefers-reduced-motion`.

---

## 7. Chi tiết "wow" độc quyền (signature moments)

Đây là những thứ KHÔNG thiệp nào khác làm:

1. **"Song Hỷ Monogram"** — Logo riêng cho cặp đôi: chữ V & H lồng vào nhau theo dạng dấu Song Hỷ 囍 (cách điệu line-art mảnh, gold foil). Xuất hiện ở loading, sigil envelope, RSVP confirm.
2. **Botanical Line Art** — Vẽ tay lily/hyacinth (bó hoa thật trong ảnh) bằng SVG single-stroke, không dùng emoji/flat icon.
3. **Asymmetric Hero** — Tên "TUẤN VIỆT" căn trái, "NHẬT HƯỜNG" căn phải, chữ "&" script lớn ở giữa trên trục so le → có chiều sâu typographic.
4. **Paper grain texture** — Nền ivory có texture noise 2% rất nhẹ → cảm giác giấy thật, không phẳng kỹ thuật số.
5. **Photo with caption** — Mỗi ảnh có caption editorial nhỏ: *"Buổi chiều đầu tiên, Hà Nội, 2023."* — biến thiệp thành story.
6. **Đèn lồng giấy minh hoạ** — SVG lồng đèn nhỏ ở góc, gợi không gian cưới truyền thống mà không bị cliché.
7. **RSVP Form như thư viết tay** — Input bo tròn lớn, label script, placeholder italic.
8. **"Save the Date" Stamp** — Con dấu tròn gold tạo cảm giác bưu phẩm thật.

---

## 8. Anti-patterns — TUYỆT ĐỐI tránh

- ❌ Emoji 💕🌸✨ trong nội dung
- ❌ Font Great Vibes mọi nơi — đã quá phổ biến
- ❌ Background gradient nâu-đen "rustic" toàn trang
- ❌ Hoa hồng đỏ tươi photoshop chèn vào góc
- ❌ Đếm ngược font sans-serif đậm trên nền đen — "đám cưới techie"
- ❌ Music tự bật không tắt được
- ❌ Confetti rơi liên tục
- ❌ Tất cả text căn giữa từ trên xuống dưới

---

## 9. Thông tin đầu vào

- **Cô dâu:** Vũ Nhật Hường
- **Chú rể:** Hoàng Tuấn Việt
- **Thời gian:** 10:30 sáng, Thứ Ba 26/05/2026 (10/04 Bính Ngọ)
- **Địa điểm:** Nhà hàng Hưng Mắm, Khu đô thị Hà Phương
- **Bố mẹ hai bên:** ẩn (theo yêu cầu)

---

## 10. Output yêu cầu

- Mobile-first, max-width 560px, test trên 375px.
- Một file HTML duy nhất, inline CSS + JS để dễ share.
- Đạt Lighthouse Performance ≥ 90.
- Hỗ trợ giảm motion, font-size scale, contrast AA.

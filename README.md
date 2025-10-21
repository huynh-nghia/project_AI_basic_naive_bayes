```markdown
# YouTube Comments Sentiment Analyzer (Flask)

Mô tả
- Ứng dụng Flask đơn giản để lấy bình luận từ video YouTube và phân tích cảm xúc.
- Sử dụng YouTube Data API v3 để lấy comment; phân tích cảm xúc mặc định dùng NLTK VADER (nhanh).
- Có tuỳ chọn dùng Hugging Face `transformers` (cần cài thêm `torch`, nặng hơn nhưng chính xác hơn).

Yêu cầu
- Python 3.8+
- YouTube Data API key

Cài đặt
1. Tạo virtualenv và kích hoạt:
   - python -m venv venv
   - source venv/bin/activate (Linux/macOS) hoặc venv\Scripts\activate (Windows)

2. Cài dependencies:
   - pip install -r requirements.txt

3. Thiết lập biến môi trường:
   - Copy `.env.example` thành `.env` và điền `YOUTUBE_API_KEY`.

4. Cài NLTK VADER lexicon:
   - python -c "import nltk; nltk.download('vader_lexicon')"

(Bổ sung nếu dùng transformers)
- Nếu muốn dùng model transformers, cài `torch` phù hợp GPU/CPU rồi `pip install transformers`. Việc này có thể mất nhiều thời gian/ổ đĩa.

Chạy ứng dụng
- flask run
- Mở http://127.0.0.1:5000

Sử dụng
- Dán URL video YouTube hoặc Video ID và nhấn "Analyze".
- Ứng dụng sẽ lấy một số bình luận (mặc định 100) và trả về nhãn sentiment + điểm.

Ghi chú
- YouTube Data API có quota; nếu cần nhiều comments hoặc nhiều request hãy kiểm tra quota.
- VADER tốt với tiếng Anh; nếu bình luận tiếng Việt bạn cần mô hình phù hợp (phân tích tiếng Việt bằng transformer/finetuned model hoặc dùng lexicon tiếng Việt).
```
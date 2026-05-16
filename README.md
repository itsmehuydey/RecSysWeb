# The Curation — Hướng dẫn chạy project

Project **React + TypeScript + Vite** (frontend) kết hợp **Express + Supabase** (backend).

---

## Yêu cầu

- **Node.js** >= 18
- Tài khoản **Supabase** (tạo project tại [supabase.com](https://supabase.com))

---

## 1. Cài đặt dependencies

**Frontend** (thư mục gốc):
```bash
npm install
```

**Backend:**
```bash
cd backend
npm install
```

---

## 2. Cấu hình environment variables( Hiện tại code đã kèm .env cho dễ ở cấp độ btl --> chứ không đc phép push lên khi deploy)

Tạo file `.env` trong thư mục `backend/`:
```env
SUPABASE_URL=your_supabase_project_url
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key
JWT_SECRET=your_jwt_secret_key
PORT=3001
```

> Lấy `SUPABASE_URL` và `SUPABASE_SERVICE_ROLE_KEY` tại: **Supabase Dashboard → Project Settings → API**

---

## 3. Khởi tạo database

Chạy file schema SQL trong Supabase:
1. Vào **Supabase Dashboard → SQL Editor**
2. Copy nội dung file `backend/supabase/schema.sql` và chạy ( Hiện tại đã có trên cloud rồi)

---

## 4. Seed dữ liệu mẫu (tùy chọn)

```bash
cd backend
npm run seed
```

---

## 5. Chạy project

Mở **2 terminal**:

**Terminal 1 — Backend** (cổng 3001):
```bash
cd backend
npm run dev
```

**Terminal 2 — Frontend** (cổng 5173):
```bash
npm run dev
```

---

## 6. Truy cập

| Thành phần  | URL                                 |
| ----------- | ----------------------------------- |
| Frontend    | http://localhost:5173               |
| Backend API | http://localhost:3001               |
| Health check | http://localhost:3001/api/health   |
| Debug info  | http://localhost:3001/api/debug     |

---

## 7. Bắt đầu chạy mô hình AI trên nền Python:
### Tạo môi trườnh Venv:
```bash
python -m venv venv
.\venv\Scripts\activate
```
### Cài đặt các thư viện cơ bản và API:
```bash
pip install Flask flask-cors PyMySQL transformers numpy pandas scikit-learn
```
### Cài đặt PyTorch (Rất quan trọng):
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

Download qua trang chính thức:
https://huggingface.co/google-bert/bert-base-chinese/tree/main

Hoặc download trực tiếp qua link drive đính kèm:
https://drive.google.com/drive/folders/1VqOwtKDv4TUmyHJNh5TPKZryO5u_1czp?usp=sharing

Sau đó import vào đường dẫn thư mục: 
literary-works-recommendation-algorithm\model_and_train\multi_feature_fm\base_bert_chinese\pytorch_model.bin

### Train model:
Chạy file main.py bằng lệnh:
```bash
python main.py
```
Hoặc download trực tiếp qua link drive đính kèm:
https://drive.google.com/drive/folders/1VqOwtKDv4TUmyHJNh5TPKZryO5u_1czp?usp=sharing

Sau đó import vào đường dẫn thư mục: 
literary-works-recommendation-algorithm\model_params multif_feature_fm_model_adamW_mae_dim=80_epoch=5.pth

### Chạy tầng ứng dụng để kết nối với Web server:
```bash
python app.py
```

## Các lệnh khác

```bash
# Build frontend
npm run build

# Xem bản build
npm run preview

# Lint code
npm run lint
```




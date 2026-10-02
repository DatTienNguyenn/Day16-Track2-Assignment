1. Tôi dùng GCP, us-central1 / us-central1-a, e2-medium (2 vCPU, 4 GB RAM, gpu_count=0), source commit [SHA].
2. Dataset có 284.807 dòng (492 fraud), chia train/validation/test theo tỷ lệ 170.883 / 56.962 / 56.962 dòng (~60% / 20% / 20%), seed 16.
3. Load dữ liệu mất 3.20 giây (3.2038s); training mất 4.34 giây (4.3422s); best iteration là 68.
4. AUC 0.9768 (0.976848), Accuracy 0.9995 (0.999508), F1 0.8478, Precision 0.9070 (0.906977), Recall 0.7959 (0.795918) trên tập test (decision threshold 0.5).
5. Latency 1 dòng 1.26 ms (1.2631 ms, lặp 50 lần); throughput batch 1.000 dòng 260.277 dòng/giây (260.276,9 dòng/s, batch 1.000 dòng mất ~0.0038s, lặp 10 lần); cách đo: median; warm-up excluded; predict_proba on pandas input.
6. CPU/RAM/Network tôi quan sát lúc 10:21:44 (uptime 39 min) là: CPU load 0.2% (99.8% idle, load avg 0.01); RAM used 491.8 MiB / 3.8 GiB (12.5%, available 3.4 GiB, swap 0B); Network (ens4) RX 245.13 MB (14.318 packets, 0 dropped), TX 873.83 KB (7.842 packets, 0 dropped); ảnh đính kèm [top.png, ip_link.png].
7. Billing tại [17:26 ngày 02/10/2026] ghi nhận [chưa cập nhật]; ước tính riêng nếu có [khoảng $0.0335/giờ cho e2-medium, chạy vài phút chi phí không đáng kể].
8. Tôi đã tải kết quả và xóa tài nguyên lúc [17:47 ngày 02/10/2026]; bằng chứng dọn dẹp [ảnh chụp màn hình console GCP VM deleted / lệnh gcloud compute instances delete thành công].

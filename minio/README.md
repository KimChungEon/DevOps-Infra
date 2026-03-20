### 테스트 및 결과

<img width="70%" height="20%" alt="Image" src="https://github.com/user-attachments/assets/913b6b77-b079-4ef2-b25f-a573d91b3ebd" />

<br />
<br />


- Pod 2개 장애 시뮬레이션 (8드라이브 중 4드라이브 장애, 4개일 경우 2개까지 허용)


```bash
# Pod 2개 동시 삭제
kubectl delete pod minio-1 minio-2 -n minio

# 터미널 1에서 업로드가 계속 성공하는지 확인
# 4개 드라이브까지 장애 허용이므로 Pod 2개(=드라이브 4개) 죽어도 동작해야 함

# 클러스터 상태 확인
kubectl exec -it -n minio minio-0 -- mc admin info local
```


<img width="50%" height="50%" alt="Image" src="https://github.com/user-attachments/assets/0b247172-ec75-417a-84fb-633c686d0f68" />
<img width="50%" height="50%" alt="Image" src="https://github.com/user-attachments/assets/bcd46c0a-b6af-4d9a-b8b5-bee8a429aef0" />

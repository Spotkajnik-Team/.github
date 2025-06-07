# 📌 Przydatne linki
- 🌍 Aspire Dashboard: http://10.114.0.2:18888
- ⚙️ Minio Console: http://10.114.0.5:9001
- 📊 Access Server client portal: https://164.90.210.100


# Diagram architektury środowiska `Staging`

```mermaid
architecture-beta
    group vpc(internet)[VPC]
    group internet(internet)[Internet]

    service mongo(database)[MongoDB] in vpc
    service minio(database)[MinIO] in vpc
    service server(server)[API] in vpc
    service aspire(server)[Aspire Dashboard] in vpc
    service unsplash(server)[Unsplash] in internet

    server:L --> R:aspire
    server:T --> R:mongo
    server:T --> R:minio
    server:R --> L:unsplash
```

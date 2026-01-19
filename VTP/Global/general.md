# I. Tổng quan hệ thống Global

```mermaid
sequenceDiagram
    participant user as User
    participant oms as OMS Service
    participant ops as OPS
    participant db as Database

    user ->> oms: tạo đơn
    oms ->> db: ghi vào bảng oms_order
    oms ->> ops: đồng bộ oms_order thông qua kafka topic <br> oms_core.oms_core.oms_order
    
    user ->> ops: thực hiện gán chi nhánh cho đơn <br> trạng thái đơn lên 120
    ops ->> oms: đồng bộ
    oms ->> ops: đồng bộ
    
    user ->> ops: gán bưu cục cho đơn <br> trạng thái đơn lên 200
    ops ->> oms: đồng bộ
    oms ->> ops: đồng bộ

    user ->> ops: gán bưu cục cho đơn <br> trạng thái đơn lên 200
    ops ->> oms: đồng bộ
    oms ->> ops: đồng bộ
    
```

# OMS Tạo đơn
```mermaid
graph TB
    subgraph OMS
        oms[oms core service]
    end

    subgraph OPS
        receiving[receiving service]
        handover[handover service]
        sorting[sorting service]
        delivery[delivery service]
    end

    subgraph Topic Kafka
        oms_order[oms_core.oms_core.oms_order]
    end

    oms -->|produce, đẩy thông tin đơn tạo| oms_order
    receiving --> |consume| oms_order
    handover --> |consume| oms_order
    sorting --> |consume| oms_order
    delivery --> |consume| oms_order
```

# OPS Cập nhật đơn 
Note
- Trong hệ thống Global, thông tin đơn được oms quản lý, mọi sự thay đổi dữ liệu đều phải đi qua oms. Nếu oms tạo/cập nhật đơn, ops đồng bộ thông tin đơn qua topic kafka oms_core.oms_core.oms_order. Nếu thông tin đơn được thay đổi bởi 1 dịch vụ nào trong Ops, dịch vụ này sẽ đẩy event lên topic của nó, sau đó oms sẽ đồng bộ về rồi đẩy event lên topic oms_core.oms_core.oms_order và các service còn lại của Ops thực hiện đồng bộ.
# Умный дом - Диаграмма вариантов использования

```mermaid
flowchart TD
    %% Акторы
    Owner[Владелец]
    Guest[Гость]
    Admin[Администратор]
    Mobile[Мобильное приложение]
    
    %% Группы прецедентов
    subgraph A[Климат и освещение]
        A1[Контроль температуры]
        A2[Управление освещением]
        A3[Сценарии климата]
    end
    
    subgraph B[Безопасность]
        B1[Система безопасности]
        B2[Мониторинг датчиков]
        B3[Экстренные уведомления]
    end
    
    subgraph C[Энергия]
        C1[Энергосбережение]
        C2[Статистика потребления]
    end
    
    subgraph D[Управление]
        D1[Управление устройствами]
        D2[Автоматизация]
        D3[Настройка системы]
    end
    
    %% Связи Владельца
    Owner --> A1
    Owner --> A2
    Owner --> B1
    Owner --> D1
    Owner --> C1
    Owner --> C2
    
    %% Связи Гостя
    Guest --> A2
    Guest --> D1
    
    %% Связи Администратора
    Admin --> D3
    Admin --> B2
    Admin --> C2
    
    %% Связи Мобильного приложения
    Mobile --> A2
    Mobile --> A1
    Mobile --> B1
    Mobile --> D1
    
    %% Внутренние связи
    B1 -.-> B3
    D2 -.-> A3
    D3 -.-> D1
    
    %% Стили
    classDef actor fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef climate fill:#fce4ec,stroke:#c2185b
    classDef security fill:#e8f5e8,stroke:#2e7d32
    classDef energy fill:#fff3e0,stroke:#ef6c00
    classDef control fill:#e3f2fd,stroke:#1565c0
    
    class Owner,Guest,Admin,Mobile actor
    class A1,A2,A3 climate
    class B1,B2,B3 security
    class C1,C2 energy
    class D1,D2,D3 control
```****

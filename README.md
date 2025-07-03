graph TD
    subgraph "あなたのPC (開発環境)"
        User["あなた (開発者)"] -->|指示| VSCode
        VSCode -->|命令| AI["AI工場長<br>(Claude Codeなど)"]
        AI -->|コード編集| Project["Next.js プロジェクト<br>(ウェブサイトのコード)"]
    end

    subgraph "クラウド (インターネット上)"
        GitHub["設計図の保管庫<br>(GitHub)"]
        VPS
        Sanity
    end

    Project -->|1. コードを保管 (git push)| GitHub
    GitHub -->|2. 自動でウェブサイトを建築 (自動デプロイ)| VPS

    subgraph "インターネット"
        Visitors["ウェブサイト訪問者"] -->|サイトを閲覧| VPS
        VPS -->|3. 記事や画像データを取得 (API経由)| Sanity
    end

    style User fill:#cde,stroke:#333,stroke-width:2px
    style VPS fill:#f9f,stroke:#333,stroke-width:2px

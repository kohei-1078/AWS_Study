## Route53
- レコードの種類
    - CNAME
        - ドメイン名やホスト名の別名を定義するレコード
        - RDSの自動フェールオーバーをルーティングする際は、このレコードが切り替わって、フェールオーバーを実行する
    - TXT
        - ホスト名に関連付けるテキスト情報（文字列）を定義するレコード
    - MX
        - 対象ドメイン宛のメール転送先ホスト名を定義するレコード
    - A
        - ホスト（FQDN）とサーバーを識別するグローバルIPアドレスの関連付けを定義するレコード
    - Alias
        - **他のAWSリソースと紐づけるために利用される**
        - DNS機能に対するRoute53固有の拡張機能を提供する
        - IPアドレスまたはドメイン名の代わりに、CloudFrontディストリビューション、Elastic Beanstalk環境、ELB Classic、Application、またはNetwork Load Balancer、静的Webサイトとして設定されているS3バケットへのポインタ、または同じホストゾーン内の別のRoute53レコードを設定することができる
- ルーティング
    - シンプルルーティング
        - ランダムに各サーバーにルーティングする設定が可能
    - 加重ルーティング
        - 指定した比率で複数のリソースにトラフィックをルーティングする場合に使用
    - レイテンシールーティング
        - 複数のAWSリージョンでアプリケーションがホストされている場合、ネットワークレイテンシーが最も低いAWSリージョンに基づいてリクエストを処理することで、ユーザーのパフォーマンスを向上させることが可能
    - フェイルオーバールーティング
        - フェイルオーバーによって異常なリソースへのルーティングを停止して、正常なリソースに対してルーティングすることが可能
    - 位置情報ルーティング
        - ユーザーの位置情報、つまりDNSクエリの発信位置に基づいてトラフィックを処理するリソースを選択可能
    - 地理的近接ルーティング
        - ユーザーとリソース間の物理的な距離に基づいてトラフィックをルーティングできる
- トラフィックフロー
    - 複雑なルーティングを設定するためにこのサービスを用いて順序を設定する
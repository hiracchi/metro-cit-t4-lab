# 付録

## Ciscoルーターコマンド

### モードの切り替え
Ciscoルーターは「ユーザー実行モード」から「特権実行モード」へ移行し、さらに「グローバルコンフィギュレーションモード」で設定を変更する。

- `enable`: 特権実行モードへ移行（プロンプトが `>` から `#` に変わる）
- `configure terminal`: 設定変更モードへ移行
- `exit` / `end`: 現在のモードを抜ける。`end` は一気に特権モードへ戻る

### インターフェース設定

```text
interface [インターフェース名]  # 例: interface GigabitEthernet0/0
ip address [IPアドレス] [サブネットマスク]
no shutdown                     # インターフェースを有効化（デフォルトは無効）
```

### よく使う確認・設定コマンド

- インターフェースの確認

```text
show interfaces
```

- イーサネットインターフェースにIPアドレスを設定

```text
ip address [IP ADDRESS] [netmask]
no shutdown
```

- シリアルインターフェースにIPアドレスを設定

```text
ip address [IP ADDRESS] [netmask]
clock rate 64000
no shutdown
```

- RIPの設定

```text
router rip
network [network-address] # 例: network 192.168.1.0
```

- ルーティングテーブルの確認

```text
show ip route
```

- 到達の確認

```text
ping [IP address]
```

```text
traceroute [IP address]
```

- 設定の確認

```text
show run
```

### Tips

- `?` (ハテナ): 入力できるコマンドの候補を表示する。
- `Tab`キー: コマンドを補完する。

## Linuxの設定・コマンド

### IPアドレスの設定

```text
su
ifconfig eth0 [IP address] netmask [netmask] # 例: ifconfig eth0 192.168.1.1 netmask 255.255.255.0
```

### デフォルトルートの設定

```text
route add default gw [gateway address] # 例: route add default gw 192.168.1.2
```

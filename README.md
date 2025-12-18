```
OpenJDK 18  
No	概要（変更内容）  
1	JEP 400: UTF-8 by Default により、標準の文字エンコーディングが UTF-8 へ変更された。  
2	JEP 408: Simple Web Server により、簡易な組み込み HTTP ファイルサーバを提供するツールが追加された。  
3	JEP 413: Java API ドキュメントにコードスニペットを埋め込む機能が追加された（@snippet タグの導入）。  
4	JEP 416: コアリフレクション API の内部実装がメソッドハンドルを用いたものに再実装され、パフォーマンスと保守性が向上した。  
5	JEP 417: Vector API (第3段階インキュベータ) が導入され、Java でのベクタ計算機能を試験提供。  
6	JEP 418: Internet-Address Resolution SPI の導入により、名前解決 (DNS など) をカスタム実装できる SPI が追加された。  
7	JEP 419: Foreign Function & Memory API (第2段階インキュベータ) が導入され、Java からネイティブライブラリ呼び出しやメモリ操作を安全に行う機能を試験提供。  
8	JEP 420: switch 文のパターンマッチ (第2プレビュー) が導入され、switch 式/文において型やパターンでの分岐が可能になった。  
9	JEP 421: ファイナライゼーション機構が将来のリリースで削除予定として非推奨 (for removal) 指定され、`--finalization=disabled` オプションで明示的に無効化できるようになった。  
10	Security Manager がデフォルトで無効化され、`java.security.manager` プロパティの既定値が "disallow" に変更されたため、明示的に許可しない限り `System.setSecurityManager(...)` 呼び出しが例外をスローするようになった:contentReference[oaicite:0]{index=0}。  
11	SHA-1 で署名された JAR ファイルがデフォルトで無効化され、SHA-1 署名の JAR は未署名として扱われるようになった（2019年以前のタイムスタンプ付き除く）:contentReference[oaicite:1]{index=1}。  
12	JDK の信頼ストアから IdenTrust DST Root CA X3 および GlobalSign Root CA R2 のルート証明書が削除された:contentReference[oaicite:2]{index=2}:contentReference[oaicite:3]{index=3}。  
13	`java.desktop` モジュール内に存在した空の `finalize()` メソッド実装が削除された:contentReference[oaicite:4]{index=4}。  
14	JDK 1.4 以前の古い `DatagramSocketImpl` 実装 (接続非対応など) へのサポートが削除され、該当実装を使用すると `SocketException` 等が発生するようになった:contentReference[oaicite:5]{index=5}:contentReference[oaicite:6]{index=6}。  
15	`java.net.InetAddress` の内部実装差し替え用システムプロパティ `impl.prefix` が削除された（JEP 418 で導入の名前解決 SPI に置き換え）:contentReference[oaicite:7]{index=7}。  
16	レガシーな `PlainSocketImpl` および `PlainDatagramSocketImpl` が削除され、それらを使用するプロパティ (`jdk.net.usePlainSocketImpl` 等) は無視されるようになった:contentReference[oaicite:8]{index=8}:contentReference[oaicite:9]{index=9}。  
17	Kerberos 設定ファイル (`krb5.conf`) の `default_checksum` および `safe_checksum_type` パラメータのサポートが削除された:contentReference[oaicite:10]{index=10}。  
18	`javax.security.auth.Subject::doAs` メソッド2種が将来の削除に向け非推奨 (for removal) となった:contentReference[oaicite:11]{index=11}。  
19	sun.misc.Unsafe のオフセット取得メソッド (`objectFieldOffset` など) が非推奨となり、将来の削除に向け VarHandle API への移行が推奨された:contentReference[oaicite:12]{index=12}。  
20	危険なメソッドである `Thread.stop` が本リリースでターミナル（完全）非推奨となり、将来削除される予定となった:contentReference[oaicite:13]{index=13}。  
21	JVM のバイアス付きロック機能が完全に廃止され、`UseBiasedLocking` 等の関連フラグは指定しても無視されオブソリート警告のみが出るようになった:contentReference[oaicite:14]{index=14}。  
22	XML の XPath 処理で結果が不正になる問題や、無効な XPath 式で誤った例外が発生する問題など、各種バグが修正された:contentReference[oaicite:15]{index=15}。  

OpenJDK 19  
No	概要（変更内容）  
1	JEP 405: Record Patterns (プレビュー) により、レコードの内部データをパターンマッチで抽出できる機能が追加された:contentReference[oaicite:16]{index=16}。  
2	JEP 422: Linux/RISC-V ポートにより、Linux 環境で RISC-V アーキテクチャが公式サポートされた:contentReference[oaicite:17]{index=17}。  
3	JEP 424: Foreign Function & Memory API (プレビュー) により、Java からネイティブコードの呼び出しとメモリ操作を行う API がプレビュー提供された:contentReference[oaicite:18]{index=18}。  
4	JEP 425: 仮想スレッド (プレビュー) により、軽量スレッドである仮想スレッドが導入され、高スループットな並行処理が容易になった:contentReference[oaicite:19]{index=19}。  
5	JEP 426: Vector API (第4段階インキュベータ) が導入され、ベクタ計算用 API の開発が継続された:contentReference[oaicite:20]{index=20}。  
6	JEP 427: switch 文のパターンマッチ (第3プレビュー) が導入され、パターンマッチ機能のプレビューが重ねられた:contentReference[oaicite:21]{index=21}。  
7	JEP 428: 構造化並行処理 (インキュベータ) が導入され、複数のスレッドによる処理を1つの作業単位として扱う API が試験提供された:contentReference[oaicite:22]{index=22}。  
8	Unicode 14.0 対応により、Unicode データベースが v14.0 に更新され、838文字の追加や新スクリプト・新絵文字がサポートされた:contentReference[oaicite:23]{index=23}:contentReference[oaicite:24]{index=24}。  
9	標準出力/標準エラーのエンコーディングを指定するシステムプロパティ (`stdout.encoding` と `stderr.encoding`) が追加された:contentReference[oaicite:25]{index=25}。  
10	HTTPS 接続での Negotiate/Kerberos 認証に TLS チャネルバインディングトークンのサポートが追加され、MITM 攻撃への耐性が向上した:contentReference[oaicite:26]{index=26}。  
11	`DateTimeFormatter.ofLocalizedPattern("yMMM")` などにより任意のローカライズ済み日時パターンでのフォーマットが可能になった（日本語環境では "y年M月" 形式など）:contentReference[oaicite:27]{index=27}:contentReference[oaicite:28]{index=28}。  
12	`HashMap.newHashMap(初期容量)` などの静的ファクトリメソッドが追加され、指定件数のエントリを格納できる容量を持つコレクション (HashMap/LinkedHashMap/WeakHashMap/HashSet/LinkedHashSet) を生成できるようになった:contentReference[oaicite:29]{index=29}:contentReference[oaicite:30]{index=30}。  
13	Linux/AArch64 環境でリターンアドレス保護 (PAC-RET) がサポートされ、ARMv8.3 のポインタ認証機能を利用して ROP 攻撃耐性が強化された:contentReference[oaicite:31]{index=31}:contentReference[oaicite:32]{index=32}。  
14	`-XX:+AutoCreateSharedArchive` オプションが追加され、Java 実行時にクラスデータ共有 (CDS) アーカイブを自動生成・更新できるようになった:contentReference[oaicite:33]{index=33}。  
15	診断フラグ `GCParallelVerificationEnabled` が削除され、ヒープ検証は常に並列で実行されるようになった:contentReference[oaicite:34]{index=34}。  
16	`SSLSocketImpl` の finalize メソッドが削除され、ソケットを明示的に閉じなかった場合でも GC 時の TLS close_notify 送信が行われなくなった:contentReference[oaicite:35]{index=35}。  
17	`Subject::current`/`callAs` の代替 ThreadLocal 実装と制御用プロパティ (`jdk.security.auth.subject.useTL`) が削除され、デフォルト実装のみ残された:contentReference[oaicite:36]{index=36}。  
18	古い `ThreadGroup` API の機能が縮小され、`destroy` は何もせず、`stop`/`suspend`/`resume` などは UnsupportedOperationException をスローするよう挙動が変更された:contentReference[oaicite:37]{index=37}:contentReference[oaicite:38]{index=38}。  
19	`Locale` クラスのコンストラクタが非推奨となり、代わりに `Locale.of()` や `Locale.forLanguageTag()` の利用が推奨された:contentReference[oaicite:39]{index=39}。  
20	`PSSParameterSpec.DEFAULT` 定数および `PSSParameterSpec(int)` コンストラクタが非推奨となった（デフォルト値ではなく適切なパラメータを指定して使用することが推奨）:contentReference[oaicite:40]{index=40}。  
21	`OAEPParameterSpec.DEFAULT` 定数が非推奨となり、RSA OAEP のパラメータは明示的に指定することが推奨された:contentReference[oaicite:41]{index=41}。  
22	本リリースでは Oracle Critical Patch Update による複数のセキュリティ脆弱性修正が含まれ、HarfBuzz 4.4.1 や FreeType 2.12.1 への更新を含む多くのバグ修正が行われた:contentReference[oaicite:42]{index=42}:contentReference[oaicite:43]{index=43}。  

OpenJDK 20  
No	概要（変更内容）  
1	JEP 429: スコープ付き値 (インキュベータ) により、スレッド間で不変データを共有する新 API (ThreadLocal の安全な代替) が試験導入された:contentReference[oaicite:44]{index=44}。  
2	JEP 432: レコードパターン (第2プレビュー) が導入され、レコードの分解パターンマッチ機能が改良された:contentReference[oaicite:45]{index=45}。  
3	JEP 433: switch 文のパターンマッチ (第4プレビュー) が導入され、パターンマッチ機能のさらなる改良検証が行われた:contentReference[oaicite:46]{index=46}。  
4	JEP 434: Foreign Function & Memory API (第2プレビュー) が導入され、ネイティブコード連携 API の改良版が試験提供された:contentReference[oaicite:47]{index=47}。  
5	JEP 436: 仮想スレッド (第2プレビュー) が導入され、仮想スレッド機能の改良版が提供された:contentReference[oaicite:48]{index=48}。  
6	JEP 437: 構造化並行処理 (第2段階インキュベータ) が導入され、構造化並行処理 API の開発が継続された:contentReference[oaicite:49]{index=49}。  
7	JEP 438: Vector API (第5段階インキュベータ) が導入され、Vector API のインキュベータ開発が継続された:contentReference[oaicite:50]{index=50}。  
8	Unicode 15.0 対応により、Unicode がバージョン15.0 に更新され、4,489文字の追加と関連クラスのアップデートが行われた:contentReference[oaicite:51]{index=51}。  
9	中国標準文字セット GB18030 が 2022 年版に更新され、非互換変更に対応するため旧版マッピングを使うプロパティ `jdk.charset.GB18030` が追加された:contentReference[oaicite:52]{index=52}:contentReference[oaicite:53]{index=53}。  
10	Java Flight Recorder に初期セキュリティプロパティを記録するイベント `jdk.InitialSecurityProperty` が追加された:contentReference[oaicite:54]{index=54}:contentReference[oaicite:55]{index=55}。  
11	Java Flight Recorder にセキュリティプロバイダのサービス呼び出しを記録するイベント `jdk.SecurityProviderService` が追加された:contentReference[oaicite:56]{index=56}:contentReference[oaicite:57]{index=57}。  
12	暗号処理の高速化として、Poly1305 (x86_64+AVX512):contentReference[oaicite:58]{index=58}および ChaCha20 (x86_64/AArch64):contentReference[oaicite:59]{index=59}で CPU 命令最適化による高速化が行われた。  
13	複合代入での暗黙の型キャストによる精度劣化を検出するコンパイラ警告 (`-Xlint:lossy-conversions`) が追加された:contentReference[oaicite:60]{index=60}。  
14	TLS/DTLS 接続で使用する暗号グループ (Named Groups) をカスタマイズ設定できる `SSLParameters.getNamedGroups` / `setNamedGroups` メソッドが追加された:contentReference[oaicite:61]{index=61}。  
15	OpenJDK 20 では主要な機能削除は行われず、上記プレビュー/インキュベータ機能の改良と、最新のタイムゾーンデータ対応や各種バグ修正・セキュリティパッチ適用が行われている:contentReference[oaicite:62]{index=62}:contentReference[oaicite:63]{index=63}。  

OpenJDK 21  
No	概要（変更内容）  
1	JEP 430: 文字列テンプレート (プレビュー) により、埋め込み式とテンプレートプロセッサを用いた安全な動的文字列構築機能が導入された:contentReference[oaicite:64]{index=64}。  
2	JEP 431: シーケンシャルコレクション – Encounter 順序を持つ `SequencedCollection`/`SequencedSet`/`SequencedMap` インタフェースが追加され、LinkedHashMap/LinkedHashSet 等に実装された:contentReference[oaicite:65]{index=65}。  
3	JEP 439: ジェネレーショナル ZGC – Z ガベージコレクタに若世代と老世代の世代管理を導入し、Generational ZGC としてパフォーマンスが向上した:contentReference[oaicite:66]{index=66}。  
4	JEP 440: レコードパターン – レコードパターン機能が正式化され、レコードの分解パターンがプレビューを経て正式に利用可能になった:contentReference[oaicite:67]{index=67}。  
5	JEP 441: switch パターンマッチ – switch 式/文でのパターンマッチ機能が正式化され、型や常値によるパターン分岐が標準機能になった:contentReference[oaicite:68]{index=68}。  
6	JEP 442: Foreign Function & Memory API (第3プレビュー) が導入され、外部関数・メモリ API のさらなる改良版が提供された:contentReference[oaicite:69]{index=69}。  
7	JEP 443: 無名パターン・変数 (プレビュー) が導入され、マッチ対象を使用しない場合に `_` で無視できる機能などパターンマッチ記法が強化された:contentReference[oaicite:70]{index=70}。  
8	JEP 444: 仮想スレッド – 仮想スレッド機能が正式化され、JVM が管理する軽量スレッドによる高スケーラビリティ並行処理が正式サポートされた:contentReference[oaicite:71]{index=71}。  
9	JEP 445: 無名クラスとインスタンス main メソッド (プレビュー) が導入され、小規模な単一ファイルプログラムを容易に実装できるようになった:contentReference[oaicite:72]{index=72}。  
10	JEP 446: スコープ付き値 (プレビュー) が導入され、スレッド内での不変データ共有機能が試験提供された（JEP 429 のプレビュー版）:contentReference[oaicite:73]{index=73}。  
11	JEP 448: Vector API (第6段階インキュベータ) が導入され、Vector API の開発が継続された:contentReference[oaicite:74]{index=74}。  
12	JEP 449: Windows 32-bit x86 ポートが将来の削除予定として非推奨化された:contentReference[oaicite:75]{index=75}。  
13	JEP 451: Java エージェントの動的読み込みを将来禁止するための準備が行われ、デフォルトで Attach API によるエージェント付加を制限する機構が導入された:contentReference[oaicite:76]{index=76}。  
14	JEP 452: キーカプセル化メカニズム (KEM) API が導入され、ポスト量子暗号を含む鍵交換アルゴリズム用の API が追加された:contentReference[oaicite:77]{index=77}。  
15	JEP 453: 構造化並行処理 (プレビュー) が導入され、構造化並行処理 API がプレビュー段階に入った:contentReference[oaicite:78]{index=78}。  
16	Security Manager が完全に無効化され、`System.setSecurityManager(...)` は常に例外をスローする仕様となった（JEP 411 の実施）:contentReference[oaicite:79]{index=79}:contentReference[oaicite:80]{index=80}。  
17	Security Manager 無効化に伴い、RMI のリモートコードダウンロード機能が削除されるなど、いくつかの旧機能が整理された:contentReference[oaicite:81]{index=81}。また、32bit Windows サポートの非推奨化 (JEP 449) など将来の削除予定も告知された。  
18	JDK 21 は LTS として過去の全更新を含み、多数のバグ修正・パフォーマンス改善および最新のセキュリティ修正 (2023年9月時点の CPU 適用) が行われている。  


```


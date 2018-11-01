---
title: 'Lync Server 2013: Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示'
TOCTitle: Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48273386
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの表示

 

_**トピックの最終更新日:** 2014-09-26_

Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションは、 Microsoft Lync 2010 API ではなくスクリプト言語を使用する、スクリプトのみのアプリケーションです。MSPL を使用すると、フィルターおよびプロキシの動作をより細かく制御できます。また、トランザクション ベースの SIP アプリケーションに特定のメッセージを送信できます。MSPL は、特に SIP メッセージのフィルターおよびルーティングに使用されます。MSPL アプリケーションは UserServices モジュールと同じプロセスで実行されるのに対して、 Lync 2010 API をベースとするプログラムは別のプロセスで実行されます。

Lync Server コントロール パネルの \[ **トポロジ** \] グループの \[ **サーバー アプリケーション** \] ページを使用して、 Lync Server 2013 環境のフロントエンド サーバーで実行される MSPL サーバー アプリケーションの一覧を表示できます。この一覧には、各プールで使用できるスクリプトと、これらのスクリプトが有効になっているか、または重要と指定されているかが表示されます。スクリプトは、一覧表示された順序で実行されます。

これらのスクリプトには次のものがあります。

  - ClientVersionFilter では、プールによりサポートされるクライアントのバージョンを指定できます。クライアント バージョン フィルターを使用してクライアントのバージョンを確認し、クライアントがログオンできないようにするか、ユーザーがサポート対象外のクライアントを使用していることを知らせるメッセージを表示できます。最新バージョンのクライアントをダウンロードできる URL がメッセージとして表示されるように、クライアント バージョン フィルターを構成することもできます。

  - TranslationService は、ユーザーがダイヤルした番号を、管理者によって定義された正規化ルールに従って E.164 番号に変換します。詳細については、「 [Lync Server 2013 変換ルール](lync-server-2013-translation-rules.md)」を参照してください。

  - IncomingFederation は、テナントレベルのフェデレーション検証を強制的に実行して、テナント間のメッセージと外部展開から受信するメッセージを確認します。

  - UserServices は、フロントエンド サーバーの SIP レジストラー、プレゼンス、および会議コンポーネントです。また、SIP プロキシ上に構築され、密接に統合された IM、プレゼンス、および電話会議機能を提供します。

  - InterClusterRouting は、通話を呼び出し先のプライマリ レジストラー プールにルーティングします。詳細については、「 [Lync Server 2013 のフロント エンド サーバーの VoIP コンポーネント](lync-server-2013-front-end-server-voip-components.md)」を参照してください。

  - IIMFilter (インテリジェント IM フィルター) は、クリック可能な URL が含まれるメッセージ、またはファイル送信を開始しようとするメッセージをブロックします。さらに、IIMFilter はサーバーの代わりにクライアント バージョンもチェックします。IIMFilter の影響を受けるファイル送信は、Lync Server または Communicator を使用して開始されたものです。既定では、クリック可能なリンクは、リンクの先頭文字の前にアンダースコア文字を追加することで無効になります。管理者は、この動作を変更して、リンクがブロックされるようにすることができます。この場合、クリック可能な URL が含まれているメッセージ、またはファイル送信を開始しようとするメッセージはサーバーによりブロックされるため、目的の送信先に到達することはありません。IIMFilter は、プロキシ サーバーおよびアーカイブ サーバーを除く、Lync Server が実行されるすべてのサーバーにインストールされます。

  - UserPinService は、ユーザーのダイヤルイン会議の暗証番号 (PIN) を確認するために使用します。

  - DefaultRouting は、 Lync Server が実行されるサーバーの既定のルーティング アプリケーションです。これは既定では有効になっています。このルーティング アプリケーションは、すべての Standard Edition サーバーおよび Enterprise Edition サーバーにインストールされます。

  - ExumRouting は、Exchange Server ユニファイド メッセージング (UM) の呼び出しをルーティングします。また、預かっている新しいボイス メール メッセージがあるときに適切な Exchange UM サーバーを決定し、通話をルーティングします。さらに、ExumRouting は Exchange UM 統合の他の機能 (自動応答、サブスクライバー アクセスへのルーティングなど) も処理します。

  - OutboundRouting は、ダイヤルされた番号およびユーザーのダイヤル承認に従って電話番号への通話をルーティングするゲートウェイを決定します。さらに、OutboundRouting は、ゲートウェイが通話を処理できない場合に通話の再ルーティングも処理します。

  - QoEAgent は、SIP SERVICE 要求を使用してエンドポイントから QoE (Quality of Experience) データのレポートを受信し、HTTP POST を使用して、データを監視サーバー上の送信先キューまたはサードパーティのコンシューマーに送信します。詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。

  - OutgoingFederation は、テナントレベルのフェデレーション検証を強制的に実行して、対象となる外部展開に送信されるメッセージを確認します。

  - AcpRouting は、プロキシとして、電話会議プロバイダー宛ての INVITE 要求を電話会議プロバイダー ゲートウェイに代わりに送信します。

エッジ サーバー上で実行されるスクリプトには次のものがあります。

  - IIMFilter

  - OptionsHandler は、現在のサーバー宛ての OPTIONS 要求を受信すると、 **200 OK** で応答します。これは、トポロジ検証で使用されます。

## 関連項目

#### タスク

[Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの有効化または無効化](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)


---
title: Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Lync Server 2013 での Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-09-26_

Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API ではなく、スクリプト言語を使用するスクリプトのみのアプリケーションです。 MSPL は、特定のメッセージをトランザクションベースの SIP アプリケーションにディスパッチするための機能に加えて、フィルター処理とプロキシ動作をより細かく制御できるようにします。 MSPL は、特に SIP メッセージのフィルター処理とルーティングに使用されます。 MSPL アプリケーションは UserServices モジュールと同じプロセスで実行されますが、Lync 2010 API に基づくプログラムは別のプロセスで実行されます。

Lync server コントロールパネルの [**トポロジ**] グループの [**サーバーアプリケーション**] ページを使用して、lync Server 2013 環境のフロントエンドサーバーで実行される MSPL Server アプリケーションの一覧を表示できます。 一覧には、各プールで利用可能なスクリプトと、それらが有効または重要であるかどうかが表示されます。 スクリプトは、一覧表示されている順序で実行されます。

これらのスクリプトには、次のようなものがあります。

  - ClientVersionFilter を使うと、管理者はプールでサポートされているクライアントのバージョンを指定することができます。 クライアントバージョンフィルターはクライアントのバージョンを確認し、クライアントがログオンできないようにするか、サポートされていないクライアントを使っていることを示すメッセージをユーザーに表示することができます。 クライアントのバージョンフィルターを構成して、クライアントの最新のダウンロード可能バージョンの URL が含まれているユーザーにメッセージを表示することもできます。

  - TranslationService は、管理者によって定義された正規化ルールに従って、ユーザーが E.i 番号にダイヤルする番号を変換します。 詳細については、「 [Lync Server 2013 の翻訳ルール](lync-server-2013-translation-rules.md)」を参照してください。

  - IncomingFederation は、テナント間の相互のフェデレーション検証を適用します。外部展開からのテナントと受信メッセージについては、この検証が適用されます。

  - UserServices は、フロントエンドサーバーの SIP レジストラー、プレゼンス、会議コンポーネントです。 SIP プロキシの上に構築された、密接に統合された IM、プレゼンス、会議機能を提供します。

  - InterClusterRouting は、呼び出し先のプライマリレジストラープールへの呼び出しをルーティングする責任を負います。 詳細については、「 [Lync Server 2013 のフロントエンドサーバー VoIP コンポーネント](lync-server-2013-front-end-server-voip-components.md)」を参照してください。

  - IIMFilter (インテリジェント IM フィルター) は、クリック可能な Url を含むメッセージをブロックするか、ファイル転送を開始しようとします。 IIMFilter は、サーバーの代わりにクライアントバージョンも確認します。 IIMFilter は、Lync Server または Communicator を使用して開始されたファイル転送に影響します。 既定では、クリック可能なリンクは、リンクの最初の文字の前にアンダースコア文字を追加することで無効になります。 管理者はこの動作を変更して、リンクがブロックされるようにすることができます。この場合、クリック可能な Url が含まれているメッセージ、またはファイル転送を開始しようとしても、サーバーが意図した宛先に到達するまでブロックされます。 IIMFilter は、Lync Server を実行しているすべてのサーバー (プロキシサーバーとアーカイブサーバーを除く) にインストールされます。

  - UserPinService を使用して、ダイヤルイン会議のユーザー暗証番号 (Pin) を確認します。

  - DefaultRouting は、Lync Server を実行しているサーバーの既定のルーティングアプリケーションです。 既定で有効になっています。 ルーティングアプリケーションは、すべての Standard Edition および Enterprise Edition サーバーにインストールされています。

  - 「ExumRouting」では、Exchange Server ユニファイドメッセージング (UM) への通話がルーティングされます。 ExumRouting は、新しいボイスメールメッセージが送信されたときに、通話をルーティングする適切な Exchange UM サーバーを決定します。 ExumRouting は、自動応答とサブスクライバーアクセスへのルーティングなど、その他の Exchange UM 統合機能も処理します。

  - OutboundRouting は、ダイヤルされた番号とユーザーのダイヤル承認に従って、通話を電話番号にルーティングするゲートウェイを決定します。 また、OutboundRouting は、ゲートウェイが通話を処理できない場合に、通話の再ルーティングも処理します。

  - QoEAgent は、SIP サービス要求によってエンドポイントから Quality of Experience (QoE) データレポートを受け取り、そのデータを監視サーバー上の送信先キューまたは HTTP POST を使ってサードパーティのコンシューマーに送信します。 詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。

  - OutgoingFederation は、対象の外部展開に移動するメッセージに対して、テナントレベルのフェデレーション検証を適用します。

  - AcpRouting プロキシは、電話会議プロバイダーに宛てた要求を電話会議プロバイダーのゲートウェイに招待します。

エッジサーバー上で実行されるスクリプトには、次のようなものがあります。

  - IIMFilter

  - [オプション] は、要求が現在のサーバーを対象としている場合は、着信オプション要求に対して**200 OK**を返します。 これは、トポロジの検証に使われます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


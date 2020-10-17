---
title: Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示
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
ms.openlocfilehash: 22a4098ed36be274f31aaeebb381654595884377
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518464"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-09-26_

Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API の代わりにスクリプト言語を使用するスクリプトのみのアプリケーションです。 MSPL は、特定のメッセージをトランザクションベースの SIP アプリケーションにディスパッチするための機能に加えて、フィルター処理やプロキシ動作をより詳細に制御します。 MSPL は、SIP メッセージのフィルター処理およびルーティングに特に使用されます。 MSPL アプリケーションは UserServices モジュールと同じプロセスで動作しますが、Lync 2010 API に基づくプログラムは別のプロセスで実行されます。

Lync server コントロールパネルの**トポロジ**グループの [**サーバーアプリケーション**] ページを使用して、lync server 2013 環境内のフロントエンドサーバーで実行される MSPL サーバーアプリケーションの一覧を表示できます。 この一覧には、各プールで使用できるスクリプトと、これらのスクリプトが有効になっているか、または重要と指定されているかが表示されます。 スクリプトは、一覧表示された順序で実行されます。

これらのスクリプトには次のものがあります。

  - ClientVersionFilter では、プールによりサポートされるクライアントのバージョンを指定できます。クライアント バージョン フィルターを使用してクライアントのバージョンを確認し、クライアントがログオンできないようにするか、ユーザーがサポート対象外のクライアントを使用していることを知らせるメッセージを表示できます。最新バージョンのクライアントをダウンロードできる URL がメッセージとして表示されるように、クライアント バージョン フィルターを構成することもできます。

  - TranslationService は、ユーザーがダイヤルした番号を、管理者によって定義された正規化ルールに従って E.164 番号に変換します。 詳細については、「 [Lync Server 2013 の変換ルール](lync-server-2013-translation-rules.md)」を参照してください。

  - IncomingFederation は、テナントレベルのフェデレーション検証を強制的に実行して、テナント間のメッセージと外部展開から受信するメッセージを確認します。

  - UserServices は、フロントエンド サーバーの SIP レジストラー、プレゼンス、および会議コンポーネントです。また、SIP プロキシ上に構築され、密接に統合された IM、プレゼンス、および電話会議機能を提供します。

  - InterClusterRouting は、通話を呼び出し先のプライマリ レジストラー プールにルーティングします。 詳細については、「 [Lync server 2013 のフロントエンドサーバー VoIP コンポーネント](lync-server-2013-front-end-server-voip-components.md)」を参照してください。

  - IIMFilter (インテリジェント IM フィルター) は、クリック可能な Url を含むメッセージまたはファイル転送を開始しようとするメッセージをブロックします。 IIMFilter は、サーバーに代わってクライアントバージョンも確認します。 IIMFilter は、Lync Server または Communicator を使用して開始されるファイル転送に影響します。 既定では、リンクの最初の文字の前にアンダースコア文字を追加することによって、クリック可能なリンクが無効になります。 管理者はこの動作を変更して、リンクがブロックされるようにすることができます。この場合、クリック可能な Url を含むメッセージまたはファイル転送を開始しようとするメッセージは、目的の宛先に到達してもサーバーによってブロックされます。 IIMFilter は、プロキシサーバーおよびアーカイブサーバーを除く、Lync Server を実行しているすべてのサーバーにインストールされます。

  - UserPinService は、ユーザーのダイヤルイン会議の暗証番号 (PIN) を確認するために使用します。

  - DefaultRouting は、Lync Server を実行しているサーバーの既定のルーティングアプリケーションです。 これは既定では有効になっています。 このルーティング アプリケーションは、すべての Standard Edition サーバーおよび Enterprise Edition サーバーにインストールされます。

  - ExumRouting は、Exchange Server ユニファイド メッセージング (UM) の呼び出しをルーティングします。また、預かっている新しいボイス メール メッセージがあるときに適切な Exchange UM サーバーを決定し、通話をルーティングします。さらに、ExumRouting は Exchange UM 統合の他の機能 (自動応答、サブスクライバー アクセスへのルーティングなど) も処理します。

  - OutboundRouting は、ダイヤルされた番号およびユーザーのダイヤル承認に従って電話番号への通話をルーティングするゲートウェイを決定します。さらに、OutboundRouting は、ゲートウェイが通話を処理できない場合に通話の再ルーティングも処理します。

  - QoEAgent は、SIP SERVICE 要求を使用してエンドポイントから QoE (Quality of Experience) データのレポートを受信し、HTTP POST を使用して、データを監視サーバー上の送信先キューまたはサードパーティのコンシューマーに送信します。 詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。

  - OutgoingFederation は、テナントレベルのフェデレーション検証を強制的に実行して、対象となる外部展開に送信されるメッセージを確認します。

  - AcpRouting は、プロキシとして、電話会議プロバイダー宛ての INVITE 要求を電話会議プロバイダー ゲートウェイに代わりに送信します。

エッジ サーバー上で実行されるスクリプトには次のものがあります。

  - IIMFilter

  - OptionsHandler は、現在のサーバー宛ての OPTIONS 要求を受信すると、**200 OK** で応答します。 これは、トポロジ検証で使用されます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Lync Server 2013 で、Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


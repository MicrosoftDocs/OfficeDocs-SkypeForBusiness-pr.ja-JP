---
title: 'Lync Server 2013: イベントログを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Lync Server 2013 でイベントログを確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-08-06_

[Windows イベントビューアー](http://go.microsoft.com/fwlink/p/?linkid=314067)を使用して、イベントログを表示したり、サービスエラー、AD DS のレプリケーションエラー、仮想メモリやディスク容量などのシステムリソースに関する警告を表示したりすることができます。 イベントビューアーは、Windows Server 2008 および2012に含まれています。

Lync Server 2013 ログツールで、デバッグセッションを終了するときに、[**ログファイルの分析**] をクリックして、ログファイルを表示するには、Snooper ツールを使用します。

イベントビューアーは、コンピューター上のアプリケーション、セキュリティ、およびシステムイベントに関するログを保持します。 Lync Server 2013 と Windows は両方とも、イベントログの警告とエラー状態を報告します。 そのため、毎日イベントログを確認します。

イベントビューアーを使用して、次の操作を行います。

  - イベントログを表示して管理します。

  - 解決する必要があるハードウェア、ソフトウェア、およびシステムの問題に関する情報を入手します。

  - 将来の対処が必要な傾向を特定します。

Windows Server オペレーティングシステムで Lync Server を実行しているサーバーでは、次の4種類のログにイベントが記録されます。

  - **アプリケーションログ**   アプリケーションまたはプログラムによって記録されるイベントを含むアプリケーションログ。 記録するイベントは、開発者が決定します。 たとえば、データベースプログラムでは、アプリケーションログにファイルエラーが記録されることがあります。 ほとんどの Lync Server 2013 関連イベントは、アプリケーションログに表示されます。

  - **セキュリティ**   ログには、ファイルまたはその他のオブジェクトの作成、オープン、削除などのリソースの使用に関連するイベントに加えて、有効な、有効ではないというようなイベントが記録されます。 たとえば、ログオン監査が有効になっている場合、システムへのログオン試行はセキュリティログに記録されます。

  - **システムログ**   システムログには、Windows システムコンポーネントによってログ記録されるイベントが含まれます。 たとえば、ドライバーなどのシステムコンポーネントの起動中に読み込みに失敗した場合、システムログに記録されます。 システムコンポーネントによってログに記録されるイベントの種類は、サーバーで事前に定義されています。

  - **Lync Server 2013**   ログツールには、認証、接続、ユーザー操作に関する重要なイベントが記録されます。 診断ログを有効にした後は、イベントビューアーでログエントリを表示できます。

<div>


> [!NOTE]  
> Microsoft カスタマサポートサービスによって指示されていない限り、最大ログ設定を使用することはお勧めしません。 最大ログ記録によって、大量のリソースが消費され、多くの "誤検知" が発生することがあります。これは、最大のログ記録でのみ記録されるエラーであり、問題の原因ではありません。 また、診断ログを完全に有効にしないことをお勧めします。 トラブルシューティング時にのみ使用してください。



</div>

各イベントビューアーログには、Lync Server 2013 で情報通知、警告イベント、エラーイベントが記録されます。 これらのログを慎重に監視して、Lync Server 2013 サーバー上で実行されているトランザクションの種類を追跡します。 ログを定期的にアーカイブするか、自動的なロールオーバーを使って領域が不足しないようにする必要があります。 ログファイルは、一定の量の領域を占有している可能性があるため、ログサイズを大きくし (たとえば、50 MB)、Lync Server 2013 サーバーが新しいイベントの書き込みを続行できるように、上書きするように設定します。

次のツールとテクノロジを使用して、イベントログの管理を自動化することもできます。

  - System Center Operations Manager は、Lync Server 2013 サーバーの正常性および使用状況を監視します。 Lync Server 2013 Management Pack for Operations Manager は、Lync Server 2013 を実行しているサーバーの特別な監視機能を提供して、Operations Manager を拡張します。

  - Lync Server 2013 Management Pack for Operations Manager は、標準およびエンタープライズ版の Lync Server 2013 を監視します。 このリリースには、以前は別の管理パックとして使用されていた Quality of Experience (QoE) 管理パックも組み込まれています。

監視される型は、イベントログエントリ、パフォーマンスカウンター、QoE のステートフル監視です。 このバージョンの管理パックは、Lync Server 2013 および2010のみを監視し、Office Communications Server 2007 を監視するために使用することはできません。

管理パックは、次の機能を提供します。

  - サービスに影響を与えるイベントを示すアラート

  - 構成、およびその他のサービス以外の影響の問題を示すアラート

  - Lync Server サービスの状態監視

  - 製品情報: 特定された問題の原因と解決策

Lync Server 2013 管理パックの詳細については、「 [System Center Operations Manager を使用して Lync server 2013 を監視](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)する」を参照してください。

**イベントのマス**   目イベントマス間ツールでは、複数のコンピューターのイベントログから特定のイベントを1か所にまとめて収集します。 指定したイベント Id またはイベントソースのみをレポートすることができます。 イベントのマス目の詳細については、[アカウントのロックアウトと管理ツール](http://go.microsoft.com/fwlink/?linkid=35607)の web サイトを参照してください。

****   Windows Server 2012 でのイベントトリガー: 管理者がプログラムを実行するか、メールメッセージを送信するか、または画面上のメッセージを表示することができます。 この機能の詳細については、Windows Server 2008 R2 のトピック「[特定のイベントに応答してタスクを実行](http://technet.microsoft.com/en-us/library/cc748900.aspx)する」を参照してください。 また、' Eventtrigger ' などのコマンドラインツールを使用して、イベントログの作成と照会、および特定のログに記録されたイベントへのプログラムの関連付けを行うこともできます。 Eventtriggers を使うことで、特定のイベントが発生したときにプログラムを実行するイベントトリガーを作成できます。

<div>

## <a name="see-also"></a>関連項目


[Windows イベントビューアー](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


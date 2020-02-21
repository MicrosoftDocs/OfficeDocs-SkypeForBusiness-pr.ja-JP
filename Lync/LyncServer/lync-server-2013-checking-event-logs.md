---
title: 'Lync Server 2013: イベントログの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8574681353a6082ce46efb514923871a01c1427d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Lync Server 2013 でのイベントログの確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-06_

[Windows イベントビューアー](https://go.microsoft.com/fwlink/p/?linkid=314067)を使用して、イベントログを表示したり、サービスの障害、AD DS のレプリケーションエラー、および仮想メモリやディスク容量などのシステムリソースに関する警告を取得したりできます。 イベントビューアーは、Windows Server 2008 および2012に含まれています。

Lync Server 2013 ログツールで、デバッグセッションを終了するときに、Snooper ツールを使用してログファイルを表示するには、[**ログファイルの分析**] をクリックします。

イベントビューアーは、アプリケーション、セキュリティ、およびシステムイベントに関するログをコンピューターに保持します。 Lync Server 2013 と Windows は両方とも、イベントログに警告とエラーの状態を報告します。 そのため、毎日イベントログを確認します。

イベントビューアーを使用して、次のことを行います。

  - イベントログを表示および管理します。

  - 解決する必要があるハードウェア、ソフトウェア、およびシステムの問題に関する情報を取得します。

  - 今後のアクションを必要とする傾向を特定します。

Windows Server オペレーティングシステムで Lync Server を実行しているサーバーは、次の4種類のログにイベントを記録します。

  - **アプリケーションログアプリケーション**   またはプログラムによって記録されたイベントをアプリケーションログに記録します。 開発者は、どのイベントをログに記録するかを決定します。 たとえば、データベースプログラムでは、アプリケーションログにファイルエラーが記録されることがあります。 ほとんどの Lync Server 2013 関連イベントは、アプリケーションログに記録されます。

  - **セキュリティ**   ログセキュリティログには、ファイルやその他のオブジェクトの作成、オープン、削除などのリソース使用に関連するイベントに加えて、有効で有効なログオン試行などのイベントが記録されます。 たとえば、ログオン監査が有効になっている場合、システムへのログオン試行はセキュリティログに記録されます。

  - **システムログ**   システムログには、Windows システムコンポーネントによって記録されたイベントが含まれます。 たとえば、起動時に読み込まれるドライバーまたはその他のシステムコンポーネントの障害は、システムログに記録されます。 システムコンポーネントによってログに記録されるイベントの種類は、サーバーによってあらかじめ決められています。

  - **Lync Server 2013**   ログツールは、認証、接続、ユーザー操作に関連する重要なイベントを記録します。 診断ログを有効にした後、ログエントリをイベントビューアーで表示できます。

<div>


> [!NOTE]  
> Microsoft カスタマーサポートサービスから指示があった場合を除いて、[最大ログ出力] の設定は使用しないことをお勧めします。 最大ログは大量のリソースを消費することがあり、多くの "誤検知" を与える可能性があります。エラーは、最大ログ出力でのみ記録されますが、実際には問題の原因ではないと考えられます。 また、診断ログを完全に有効にしないことをお勧めします。 トラブルシューティング時にのみ使用します。



</div>

各イベントビューアーログで、Lync Server 2013 は情報イベント、警告イベント、およびエラーイベントを記録します。 これらのログを注意深く監視して、Lync Server 2013 サーバー上で実行されているトランザクションの種類を追跡します。 ログを定期的にアーカイブするか、または自動ロールオーバーを使用して、空き領域が不足しないようにしてください。 ログファイルは、有限の容量を占有することがあるため、ログのサイズを増やし (たとえば、50 MB に)、上書きするように設定して、Lync Server 2013 サーバーが新しいイベントを引き続き書き込むことができるようにします。

次のツールとテクノロジを使用して、イベントログの管理を自動化することもできます。

  - System Center Operations Manager は、Lync Server 2013 サーバーの正常性と使用状況を監視します。 Lync server 2013 Operations Manager 用管理パックは、Lync Server 2013 を実行しているサーバーに特別な監視を提供することによって、Operations Manager を拡張します。

  - Operations Manager 用 Lync Server 2013 管理パックは、Lync Server 2013 の Standard Edition および Enterprise Edition を監視します。 このリリースには、以前は個別の管理パックであった QoE (Quality of Experience) 管理パックも組み込まれています。

監視対象の種類は、イベントログエントリ、パフォーマンスカウンター、QoE のステートフル監視です。 このバージョンの管理パックは、Lync Server 2013 および2010のみを監視し、Office Communications Server 2007 を監視するために使用することはできません。

管理パックには、次の機能があります。

  - サービスに影響するイベントを示すアラート

  - 構成、およびその他のサービス以外の影響に関する問題を示すアラート

  - Lync Server サービスの状態監視

  - 製品ナレッジ: 特定された問題の原因と解決策

Lync Server 2013 管理パックの詳細については、「 [System Center Operations Manager で Lync server 2013 を監視](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)する」を参照してください。

****   イベントのくし形イベントマス目ツールは、複数のコンピューターのイベントログから特定のイベントを1か所にまとめて収集します。 指定したイベント Id またはイベントソースのみを報告することができます。 イベントの詳細については、「[アカウントのロックアウトおよび管理ツール](https://go.microsoft.com/fwlink/?linkid=35607)の web サイト」を参照してください。

****   Windows Server 2012 のイベントトリガー windows イベントビューアーでは、管理者がプログラムを実行したり、電子メールメッセージを送信したり、画面上のメッセージを表示したりすることができます。 この機能の詳細については、「Windows Server 2008 R2 のトピック」を参照してください。特定のイベントへの応答として[タスクを実行](https://technet.microsoft.com/library/cc748900.aspx)します。 また、' Eventtrigger ' などのコマンドラインツールを使用して、イベントログを作成および照会したり、特定のログイベントにプログラムを関連付けしたりすることもできます。 Eventtriggers を使用すると、特定のイベントが発生したときにプログラムを実行するイベントトリガーを作成できます。

<div>

## <a name="see-also"></a>関連項目


[Windows イベントビューアー](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


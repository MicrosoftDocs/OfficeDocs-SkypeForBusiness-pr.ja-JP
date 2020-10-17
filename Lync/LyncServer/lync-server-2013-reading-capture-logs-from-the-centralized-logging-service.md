---
title: 'Lync Server 2013: 集中ログサービスからキャプチャログを読み取る'
description: 'Lync Server 2013: 集中ログサービスからキャプチャログを読み取っています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559163"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 の集中ログサービスからキャプチャログを読み取る

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-28_

検索を実行してから、報告された問題を追跡するために使用できるファイルがある場合は、集中ログサービスの実際のメリットを実感できます。 ファイルを読み取るには、いくつかの方法があります。 出力ファイルは標準のテキスト形式であり、Notepad.exe を使用したり、テキストファイルを開いて読み取ることができるその他のプログラムを使用したりすることができます。 大規模なファイルとより複雑な問題については、集中ログサービスからのログ出力を読み取りおよび解析するように設計された Snooper.exe のようなツールを使用できます。 Snooper は、個別のダウンロードとして利用できる Lync Server 2013 デバッグツールに含まれています。 Lync Server 2013 デバッグツールは、次の場所からダウンロードできます [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。 Lync Server 2013 デバッグツールをインストールしても、短いカットとメニュー項目は作成されません。 Lync Server 2013 デバッグツールをインストールした後、Windows エクスプローラー、コマンドラインウィンドウ、または Lync Server 管理シェルを開いて、ディレクトリ (既定の場所) C: \\ Program Files \\ Microsoft Lync Server 2013 \\ デバッグツールに移動します。 コマンドラインまたは Lync Server 管理シェルを使用している場合は、[Snooper.exe] をダブルクリックするか、Snooper.exe を入力して enter キーを押します。

<div>


> [!IMPORTANT]  
> このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。 トラブルシューティングとそれに関連するプロセスは、複雑な問題です。 基本的なトラブルシューティングと特定のワークロードのトラブルシューティングの詳細については、Microsoft Lync Server 2010 リソースキットブック () を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> 。 プロセスと手順は、引き続き Lync Server 2013 に適用されます。



</div>

Lync Server 2013 には、いくつかの新機能を含む Snooper の更新バージョンが導入されています。 次のスクリーンショットは、Office Communications Server 2007 の Snooper のバージョンを示しています。

![Office Communications 2007 バージョンの Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 バージョンの Snooper。")

次のスクリーンショットは、Lync Server 2013 デバッグツールに含まれている新しいバージョンの Snooper を示しています。

![Lync Server 2013 バージョンの Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 バージョンの Snooper。")

次のスクリーン ショットは、よく使用する機能を含むツールバーを示します。

![Snooper 2013 ツールバー。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 ツールバー。")

また、価値を高める最新の機能として、フロー チャート (通話フロー) 図ビューがあります。[**メッセージ**] タブでメッセージ フローを選択して [**通話フロー**] ボタンをクリックします。メッセージを読み進めると、通話フロー図が新しいデータで更新されます。

![Snooper 2013 通話フロー図](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話フロー図")

図のビューにマウスを合わせると、メッセージに関する詳細、フローおよびメッセージの内容、サーバーの要素が表示されます。通話フローのいずれかの矢印をクリックすると、メッセージ ビューでメッセージが表示されます。

![呼び出しフロー図のメッセージの詳細。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "呼び出しフロー図のメッセージの詳細。")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Snooper でログ ファイルを開くには

1.  Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 グループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。

2.  Lync Server デバッグツール (LyncDebugTools.msi) をインストールした後、Windows エクスプローラーまたはコマンドラインから Snooper.exe の場所にディレクトリを変更します。 既定では、デバッグツールは C: \\ Program Files \\ Microsoft Lync Server 2013 \\ デバッグツールにあります。 Snooper.exe をダブルクリックするか、実行します。

3.  Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。

4.  ログ ファイルの**トレース** メッセージは、[**トレース**] タブに表示されます。収集されたトレースのメッセージの内容を表示するには、[**メッセージ**] タブをクリックします。

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>通話フロー図を表示するには

1.  Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 グループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。

2.  ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。

3.  [**通話フロー**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 通話フローに含まれていないメッセージまたはトレースをクリックした場合、図は表示されず、Snooper の最下部に "This message is not eligible for callfow" (このメッセージは通話フローの対象ではありません) というステータス メッセージが表示されます。別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。

    
    </div>

4.  メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。

5.  要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>


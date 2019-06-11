---
title: 'Lync Server 2013: 一元ログサービスからのキャプチャログの読み取り'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 の一元ログサービスからのキャプチャログの読み取り

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-28_

検索を実行した後で一元管理サービスの実際の利点を実感し、報告された問題を追跡するために使用できるファイルを用意しています。 このファイルは、さまざまな方法で読むことができます。 出力ファイルは標準のテキスト形式なので、メモ帳など、テキスト ファイルを開いて読むことができる任意のプログラムを使用できます。 大規模なファイルとより複雑な問題については、一元管理サービスからのログ出力の読み取りと解析のために設計された Snooper などのツールを使うことができます。 Snooper は、個別のダウンロードとして利用できる Lync Server 2013 デバッグツールに含まれています。 Lync Server 2013 デバッグツールは、次[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)のページからダウンロードできます。 Lync Server 2013 デバッグツールをインストールすると、短い切り取りとメニュー項目は作成されません。 Lync Server 2013 デバッグツールをインストールしたら、Windows エクスプローラー、コマンドラインウィンドウ、または Lync Server Management Shell を開いて、ディレクトリ (既定の場所) C:\\Program Files\\Microsoft Lync Server 2013\\デバッグツールを開きます。 Snooper をダブルクリックするか、Snooper を入力して、コマンドラインまたは Lync Server Management Shell を使用している場合は、ENTER キーを押します。

<div>


> [!IMPORTANT]  
> このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。 トラブルシューティングとそれに関連するプロセスは、複雑な問題です。 基本的なトラブルシューティングと特定のワークロードのトラブルシューティングの詳細については、「 <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Microsoft Lync Server 2010 リソースキット」を参照してください。 プロセスと手順は、引き続き Lync Server 2013 に適用されます。



</div>

Lync Server 2013 には、いくつかの新機能が含まれている Snooper の更新バージョンが導入されています。 次のスクリーンショットは、Office Communications Server 2007 からの Snooper のバージョンを示しています。

![Office Communications 2007 バージョンの Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 バージョンの Snooper。")

次のスクリーンショットは、Lync Server 2013 デバッグツールに含まれている Snooper の新しいバージョンを示しています。

![Snooper の Lync Server 2013 バージョン。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Snooper の Lync Server 2013 バージョン。")

次のスクリーンショットは、よく使われる関数を含むツールバーを示しています。

![Snooper 2013 ツールバー。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 ツールバー。")

また、値を追加する最新の機能は、フローチャート (コールフロー) ダイアグラムビューです。 [**メッセージ**] タブでメッセージフローを選択し、[**通話フロー** ] ボタンをクリックします。 メッセージを移動すると、コールフローダイアグラムが新しいデータで更新されます。

![Snooper 2013 コールフロー図。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 コールフロー図。")

ダイアグラムビューの上にマウスポインターを移動すると、メッセージや、フローとメッセージの内容、およびサーバー要素に関する詳細情報を取得することができます。 いずれかの通話フローの矢印をクリックして、[メッセージ] ビューのメッセージに移動します。

![コールフロー図のメッセージの詳細。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "コールフロー図のメッセージの詳細。")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Snooper でログ ファイルを開くには

1.  Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。

2.  Lync Server デバッグツール (LyncDebugTools) をインストールした後、Windows エクスプローラーまたはコマンドラインから Snooper の場所にディレクトリを変更します。 既定では、デバッグツールは C:\\Program Files\\Microsoft Lync Server 2013\\デバッグツールに含まれています。 Snooper.exe をダブルクリックするか、実行します。

3.  Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。

4.  ログ ファイルの**トレース** メッセージは、[**トレース**] タブに表示されます。収集されたトレースのメッセージの内容を表示するには、[**メッセージ**] タブをクリックします。

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>通話フロー図を表示するには

1.  Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。

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


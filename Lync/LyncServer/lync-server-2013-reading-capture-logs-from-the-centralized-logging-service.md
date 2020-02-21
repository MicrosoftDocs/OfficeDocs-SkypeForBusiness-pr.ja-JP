---
title: 'Lync Server 2013: 集中ログサービスからキャプチャログを読み取る'
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
ms.openlocfilehash: 0807552784b69b58accfd026031af55d41c91f33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="fc0c3-102">Lync Server 2013 の集中ログサービスからキャプチャログを読み取る</span><span class="sxs-lookup"><span data-stu-id="fc0c3-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc0c3-103">_**トピックの最終更新日:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="fc0c3-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="fc0c3-104">検索を実行してから、報告された問題を追跡するために使用できるファイルがある場合は、集中ログサービスの実際のメリットを実感できます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="fc0c3-105">ファイルを読み取るには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="fc0c3-106">出力ファイルは標準のテキスト形式であるため、メモ帳またはその他のプログラムを使用して、テキストファイルを開いて読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="fc0c3-107">大規模なファイルと複雑な問題については、集中ログサービスからのログ出力を読み取りおよび解析するように設計された Snooper などのツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="fc0c3-108">Snooper は、個別のダウンロードとして利用できる Lync Server 2013 デバッグツールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="fc0c3-109">Lync Server 2013 デバッグツールは、次[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="fc0c3-110">Lync Server 2013 デバッグツールをインストールしても、短いカットとメニュー項目は作成されません。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="fc0c3-111">Lync Server 2013 デバッグツールをインストールした後、Windows エクスプローラー、コマンドラインウィンドウ、または Lync Server 管理シェルを開いて、ディレクトリ (既定の場所) C:\\Program Files\\Microsoft Lync Server 2013\\デバッグツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="fc0c3-112">コマンドラインまたは Lync Server 管理シェルを使用している場合は、Snooper をダブルクリックするか、Snooper と入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fc0c3-113">このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="fc0c3-114">トラブルシューティングとそれに関連するプロセスは、複雑な問題です。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="fc0c3-115">基本的なトラブルシューティングと特定のワークロードのトラブルシューティングの詳細については、Microsoft <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Lync Server 2010 リソースキットブック () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="fc0c3-116">プロセスと手順は、引き続き Lync Server 2013 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="fc0c3-117">Lync Server 2013 には、いくつかの新機能を含む Snooper の更新バージョンが導入されています。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="fc0c3-118">次のスクリーンショットは、Office Communications Server 2007 の Snooper のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="fc0c3-119">![Office Communications 2007 バージョンの Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 バージョンの Snooper。")</span><span class="sxs-lookup"><span data-stu-id="fc0c3-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="fc0c3-120">次のスクリーンショットは、Lync Server 2013 デバッグツールに含まれている新しいバージョンの Snooper を示しています。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="fc0c3-121">![Lync Server 2013 バージョンの Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 バージョンの Snooper。")</span><span class="sxs-lookup"><span data-stu-id="fc0c3-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="fc0c3-122">次のスクリーン ショットは、よく使用する機能を含むツールバーを示します。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="fc0c3-123">![Snooper 2013 ツールバー。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 ツールバー。")</span><span class="sxs-lookup"><span data-stu-id="fc0c3-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="fc0c3-p104">また、価値を高める最新の機能として、フロー チャート (通話フロー) 図ビューがあります。[**メッセージ**] タブでメッセージ フローを選択して [**通話フロー**] ボタンをクリックします。メッセージを読み進めると、通話フロー図が新しいデータで更新されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-p104">And, the newest feature that adds value is the Flow Chart (call flow) diagram view. You select a message flow in the **Message** tab and click the **Call Flow** button. As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="fc0c3-127">![Snooper 2013 通話フロー図](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話フロー図")</span><span class="sxs-lookup"><span data-stu-id="fc0c3-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="fc0c3-p105">図のビューにマウスを合わせると、メッセージに関する詳細、フローおよびメッセージの内容、サーバーの要素が表示されます。通話フローのいずれかの矢印をクリックすると、メッセージ ビューでメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-p105">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements. Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="fc0c3-130">![呼び出しフロー図のメッセージの詳細。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "呼び出しフロー図のメッセージの詳細。")</span><span class="sxs-lookup"><span data-stu-id="fc0c3-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="fc0c3-131">Snooper でログ ファイルを開くには</span><span class="sxs-lookup"><span data-stu-id="fc0c3-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="fc0c3-p106">Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 グループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-p106">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="fc0c3-134">Lync Server デバッグツール (LyncDebugTools) をインストールした後、Windows エクスプローラーまたはコマンドラインから Snooper の場所にディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="fc0c3-135">既定では、デバッグツールは C:\\Program Files\\Microsoft Lync Server 2013\\デバッグツールにあります。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="fc0c3-136">Snooper.exe をダブルクリックするか、実行します。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="fc0c3-137">Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="fc0c3-138">ログ ファイルの**トレース** メッセージは、[**トレース**] タブに表示されます。収集されたトレースのメッセージの内容を表示するには、[**メッセージ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="fc0c3-139">通話フロー図を表示するには</span><span class="sxs-lookup"><span data-stu-id="fc0c3-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="fc0c3-p108">Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 グループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-p108">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="fc0c3-142">ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="fc0c3-143">[**通話フロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc0c3-p109">通話フローに含まれていないメッセージまたはトレースをクリックした場合、図は表示されず、Snooper の最下部に "This message is not eligible for callfow" (このメッセージは通話フローの対象ではありません) というステータス メッセージが表示されます。別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-p109">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”. Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="fc0c3-146">メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="fc0c3-147">要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc0c3-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


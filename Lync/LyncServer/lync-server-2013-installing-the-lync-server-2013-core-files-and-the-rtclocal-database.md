---
title: Lync Server 2013 コアファイルおよび RTCLocal データベースのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eefd8316e0e33ab8c4418a6ce72ea9eb05fc84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="ad7c0-102">Lync Server 2013 コアファイルおよび RTCLocal データベースのインストール</span><span class="sxs-lookup"><span data-stu-id="ad7c0-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad7c0-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ad7c0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ad7c0-104">Lync Server 2013 のコアファイルをコンピューターにインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="ad7c0-105">RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="ad7c0-106">監視ノードに SQL Server をインストールする必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="ad7c0-107">代わりに、SQL Server Express が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="ad7c0-108">Lync Server 2013 コアファイルおよび RTCLocal データベースをインストールするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="ad7c0-109">ウォッチャー ノード コンピューターで、[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックします。次に、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="ad7c0-110">コンソールウィンドウで、次のコマンドを入力し、ENTER キーを押して、Lync Server セットアップファイルへの適切なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="ad7c0-111">コア Lync Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="ad7c0-112">Lync Server 2013 管理シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="ad7c0-113">最初にこのコマンドを実行したときは、まだウォッチャー ノード コンピューターを構成していないので何もデータが表示されません。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="ad7c0-114">エラーが返されずにコマンドが実行されている限り、Lync Server のセットアップが正常に完了したと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="ad7c0-115">監視ノードコンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Lync Server 2013 のインストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="ad7c0-116">組織で構成されている暗証番号 (PIN) ポリシーの数に応じて、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="ad7c0-117">PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="ad7c0-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


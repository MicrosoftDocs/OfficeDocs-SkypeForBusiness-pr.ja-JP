---
title: Lync Server 2013 コアファイルと RTCLocal データベースのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="83141-102">Lync Server 2013 コアファイルと RTCLocal データベースのインストール</span><span class="sxs-lookup"><span data-stu-id="83141-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83141-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="83141-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="83141-104">Lync Server 2013 コアファイルをコンピューターにインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83141-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="83141-105">RTCLocal データベースは、コアファイルのインストール時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="83141-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="83141-106">監視ノードに SQL Server をインストールする必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="83141-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="83141-107">代わりに、SQL Server Express が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="83141-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="83141-108">Lync Server 2013 コアファイルと RTCLocal データベースをインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83141-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="83141-109">ウォッチャーノードのコンピューターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83141-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="83141-110">[コンソール] ウィンドウで、次のコマンドを入力し、ENTER キーを押します。 Lync Server セットアップファイルへの適切なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="83141-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="83141-111">主要な Lync Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="83141-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="83141-112">Lync Server 2013 管理シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="83141-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="83141-113">このコマンドを初めて実行したときに、ウォッチャーノードのコンピューターをまだ構成していないため、データは返されません。</span><span class="sxs-lookup"><span data-stu-id="83141-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="83141-114">コマンドを実行してもエラーが返されない限り、Lync Server のセットアップが正常に完了したと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="83141-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="83141-115">ウォッチャーノードのコンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して、Lync Server 2013 のインストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="83141-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="83141-116">組織で使用するために構成されている暗証番号 (PIN) ポリシーの数に応じて、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83141-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="83141-117">PIN ポリシーに関する情報が表示される場合は、コアコンポーネントが正常にインストールされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="83141-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 資格情報認証を使用するようにウォッチャーノードを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="6e684-102">Lync Server 2013 での資格情報認証を使用するためのウォッチャーノードの構成</span><span class="sxs-lookup"><span data-stu-id="6e684-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e684-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6e684-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6e684-104">ウォッチャーノードのコンピューターが境界ネットワークの外側にある場合は、別の手順に従って、そのウォッチャーノードが代理トランザクションを実行するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e684-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="6e684-105">具体的には、信頼されたアプリケーションプールと信頼されたアプリケーションを作成しないようにする必要があります。また、監視ノードが、境界ネットワーク内のコンピューターに通知を送信できるようにする証明書をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e684-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="6e684-106">これは、次の2つの個別のタスクを完了する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6e684-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="6e684-107">コンピューターの RTC ローカルの読み取り専用管理者グループのメンバーシップを更新する</span><span class="sxs-lookup"><span data-stu-id="6e684-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="6e684-108">ウォッチャーノード構成ファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="6e684-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="6e684-109">RTC ローカルの読み取り専用管理者グループのメンバーシップを更新しています</span><span class="sxs-lookup"><span data-stu-id="6e684-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="6e684-110">ウォッチャーノードが境界ネットワークの外側にある場合は、ネットワークサービスアカウントを、ウォッチャーノードコンピューターの RTC ローカルの読み取り専用管理者グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e684-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="6e684-111">これを行うには、ウォッチャーノードで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e684-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="6e684-112">[**スタート**] をクリックし、[**コンピューター**] を右クリックして、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="6e684-113">サーバーマネージャーで、[**構成**] を展開し、[**ローカルユーザーとグループ**] を展開して、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="6e684-114">[グループ] ウィンドウで、[ **RTC ローカル読み取り専用管理者**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="6e684-115">[ **RTC のローカルの読み取り専用管理者のプロパティ**] ダイアログボックスで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="6e684-116">[**ユーザー、コンピューター、サービスアカウント、またはグループの選択**] ダイアログボックスで、[**場所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="6e684-117">[**場所**] ダイアログボックスで、ウォッチャーノードのコンピューターの名前を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="6e684-118">[**選択するオブジェクト名を入力してください**] ボックスに「**ネットワークサービス**」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="6e684-119">[ **RTC のローカルの読み取り専用管理者のプロパティ**] ダイアログボックスで、[ **OK**] をクリックし、[**サーバーマネージャー**] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="6e684-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="6e684-120">監視ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e684-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="6e684-121">ウォッチャーノード構成ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="6e684-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="6e684-122">ウォッチャーノードのコンピューターが再起動したら、次の手順として、Watchernode ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e684-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="6e684-123">このファイルを実行するには、[**スタート**]、[**すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックして、lync server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e684-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="6e684-124">Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します (Watchernode のコピーの実際のパスを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="6e684-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="6e684-125">前に説明したように、Watchernode はコマンドウィンドウから実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e684-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="6e684-126">コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] メニューをクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e684-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="6e684-127">コマンドウィンドウが開いたら、前に示したのと同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e684-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="6e684-p105">監視ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。このモードでは、管理者が監視ノードのテスト ユーザー パスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e684-p105">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


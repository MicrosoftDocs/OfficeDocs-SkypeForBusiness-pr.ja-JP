---
title: 'Lync Server 2013: 資格情報認証を使用するように監視ノードを構成する'
description: 'Lync Server 2013: 資格情報認証を使用するように監視ノードを構成する。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b65d4e3f90b27aac69b8569472ac9896766e093e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576323"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="eb389-103">Lync Server 2013 で資格情報認証を使用するように監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="eb389-103">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb389-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="eb389-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="eb389-p101">ウォッチャー ノードのコンピューターが境界ネットワークの外側にある場合は、代理トランザクションを実行するようにウォッチャー ノードを構成するために、少し異なる手順に従う必要があります。具体的には、信頼されたアプリケーション プールや信頼されたアプリケーションを作成せずに、境界ネットワークの内側にあるコンピューターにウォッチャー ノードが通知を送信できるようにする証明書をインストールする必要があります。つまり、次に示す個別の 2 つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb389-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="eb389-108">コンピューターの RTC Local Read-only Administrators グループのメンバーシップを更新する</span><span class="sxs-lookup"><span data-stu-id="eb389-108">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="eb389-109">ウォッチャー ノード構成ファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="eb389-109">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="eb389-110">RTC Local Read-Only Administrators グループのメンバーシップの更新</span><span class="sxs-lookup"><span data-stu-id="eb389-110">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="eb389-p102">ウォッチャー ノードが境界ネットワークの外側にある場合は、Network Service アカウントをウォッチャー ノード コンピューターの RTC Local Read-only Administrators グループに追加する必要があります。そのためには、ウォッチャー ノードで以下の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="eb389-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="eb389-113">[**スタート**] メニューの [**コンピューター**] を右クリックし、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-113">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="eb389-114">サーバー マネージャーで、[**構成**]、[**ローカル ユーザーとグループ**] の順に展開し、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-114">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="eb389-115">[グループ] ウィンドウで、[**RTC Local Read-only Administrators**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-115">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="eb389-116">[**RTC Local Read-only Administrators のプロパティ**] ダイアログ ボックスで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-116">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="eb389-117">[**ユーザー、コンピューター、サービス アカウント、またはグループの選択**] ダイアログで、[**場所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-117">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="eb389-118">[**場所**] ダイアログ ボックスで、ウォッチャー ノード コンピューターの名前を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-118">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="eb389-119">[**選択するオブジェクト名を入力してください**] ボックスに、「**Network Service**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb389-119">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="eb389-120">[**RTC Local Read-only Administrators のプロパティ**] ダイアログ ボックスで、[**OK**] をクリックし、[**サーバー マネージャー**] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="eb389-120">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="eb389-121">ウォッチャー ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="eb389-121">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="eb389-122">ウォッチャー ノード構成ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="eb389-122">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="eb389-123">ウォッチャー ノード コンピューターの再起動後、次の手順は Watchernode.msi ファイルの実行です。</span><span class="sxs-lookup"><span data-stu-id="eb389-123">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="eb389-124">このファイルを実行するには、[ **スタート**]、[ **すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックして、Lync server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb389-124">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="eb389-125">Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="eb389-125">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="eb389-p104">前述のように、Watchernode.msi はコマンド ウィンドウから実行することもできます。コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] メニューをクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。コマンド ウィンドウが開いたら、先ほどと同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="eb389-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="eb389-129">ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb389-129">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="eb389-130">このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb389-130">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


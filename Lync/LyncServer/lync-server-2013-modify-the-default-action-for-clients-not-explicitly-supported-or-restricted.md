---
title: 明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0262bface172c965d12fc276bc08882cac8348ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="b69ad-102">Lync Server 2013 で明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="b69ad-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b69ad-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b69ad-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b69ad-104">Lync Server 2013 環境でサポートするクライアントのバージョンを指定するだけでなく、バージョンポリシーが定義されていないクライアントに対する既定のアクションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="b69ad-105">これにより、Lync Server 環境で使用するクライアントバージョンを制限することができます。これにより、複数のクライアントバージョンのサポートに関連するコストを制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="b69ad-106">明示的にサポートまたは制限されていないクライアントの既定のアクションを変更するには</span><span class="sxs-lookup"><span data-stu-id="b69ad-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="b69ad-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b69ad-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b69ad-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b69ad-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b69ad-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b69ad-110">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b69ad-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="b69ad-111">[**クライアントバージョンの構成**] ページで、リスト内の**グローバル**構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b69ad-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="b69ad-112">[**クライアントのバージョン構成の編集**] ダイアログボックスで、[**バージョン管理を有効に**する] チェックボックスがオンになっていることを確認し、[**既定のアクション**] で次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b69ad-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="b69ad-113">**[許可**   ] を選択すると、クライアントバージョンがクライアントの [**バージョンポリシー** ] 一覧のいずれのフィルターとも一致しない場合に、クライアントはログオンできます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="b69ad-114">\*\*\*\*   クライアントのバージョンがクライアントの [**バージョンポリシー** ] の一覧のどのフィルターとも一致しない場合、ブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="b69ad-115">**[Url**   を含むブロック] クライアントのバージョンが [**クライアントのバージョンポリシー** ] 一覧のいずれのフィルターとも一致しない場合、クライアントはログオンを拒否し、新しいクライアントをダウンロードできる url を含むエラーメッセージを含めます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="b69ad-116">**[URL**   による許可] を使うと、クライアントのバージョンが [**クライアントのバージョンポリシー** ] のいずれのフィルターとも一致しない場合に、クライアントはログオンでき、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="b69ad-117">[ **Url でブロック**する] を選択した場合、[ **url** ] ボックスにエラーメッセージとして含めるクライアントのダウンロード URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b69ad-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="b69ad-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b69ad-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="b69ad-119">クライアントのバージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="b69ad-119">To disable client version control</span></span>

  - <span data-ttu-id="b69ad-120">クライアントのバージョンに関係なくすべてのクライアントがログオンできるバージョン管理を無効にするには、[**バージョン管理を有効**にする] チェックボックスをオフにして、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b69ad-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b69ad-121">Windows PowerShell コマンドレットを使用して既定のアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="b69ad-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b69ad-122">クライアントバージョンポリシーによって明示的にサポートまたは制限されていないクライアントを使ってユーザーがサインインしようとしたときに実行される既定のアクションは、Windows PowerShell コマンドラインインターフェイスと**Set-CsClientVersionPolicy**コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="b69ad-123">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b69ad-124">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69ad-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="b69ad-125">アクセスをブロックする既定のアクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="b69ad-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="b69ad-126">次のコマンドは、レドモンドサイトブロックの既定のアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="b69ad-126">The following command sets the default action for the Redmond site Block.</span></span> <span data-ttu-id="b69ad-127">これにより、クライアントのバージョン設定ルールが存在しないクライアントについては、登録がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-127">This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="b69ad-128">アクセスを許可するように既定のアクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="b69ad-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="b69ad-129">この例では、Redmond サイトの既定のアクションが [許可] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b69ad-129">In this example, the default action for the Redmond site is set to Allow.</span></span> <span data-ttu-id="b69ad-130">これにより、クライアントのバージョン設定ルールが存在しないすべてのクライアントに対して登録が許可されます。</span><span class="sxs-lookup"><span data-stu-id="b69ad-130">This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="b69ad-131">詳細については、「 [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69ad-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b69ad-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b69ad-132">See Also</span></span>


[<span data-ttu-id="b69ad-133">Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="b69ad-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 63ff08d05c9c8c18b7f81f22b04e2168a14f1a8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="24799-102">Lync Server 2013 で明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="24799-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24799-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="24799-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="24799-104">Lync Server 2013 環境でサポートするクライアントのバージョンを指定することに加えて、バージョンポリシーが定義されていないクライアントの既定のアクションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="24799-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="24799-105">これにより、Lync Server 環境で使用するクライアントバージョンを制限することができます。これは、複数のクライアントバージョンのサポートに関連するコストの制御に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="24799-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="24799-106">明示的にサポートまたは制限されていないクライアントの既定のアクションを変更するには</span><span class="sxs-lookup"><span data-stu-id="24799-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="24799-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="24799-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24799-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="24799-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24799-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24799-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24799-110">左側のナビゲーション バーで [**クライアント**] をクリックし、[**クライアント バージョン構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24799-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="24799-111">[**クライアント バージョン構成**] ページで、リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="24799-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="24799-112">[**クライアント バージョン構成の編集**] ダイアログ ボックスで [**バージョン管理を有効にする**] チェック ボックスがオンになっていることを確認し、[**既定のアクション**] で次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="24799-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="24799-113">**[許可**   ] クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合に、クライアントのログオンを許可します。</span><span class="sxs-lookup"><span data-stu-id="24799-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="24799-114">\*\*\*\* クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合に、クライアントのログオンを禁止します。   </span><span class="sxs-lookup"><span data-stu-id="24799-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="24799-115">**[Block in URL**   ] クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合にクライアントのログオンを禁止し、新しいクライアントをダウンロードできる URL を含むエラーメッセージを含めます。</span><span class="sxs-lookup"><span data-stu-id="24799-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="24799-116">**Allow url**   を使用すると、クライアントのバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合にクライアントがログオンでき、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24799-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="24799-117">[**禁止して URL を表示**] を選択した場合は、エラー メッセージに含めるクライアントのダウンロード用 URL を [**URL**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="24799-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="24799-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24799-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="24799-119">クライアント バージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="24799-119">To disable client version control</span></span>

  - <span data-ttu-id="24799-120">バージョン管理を無効にしてすべてのクライアントがクライアント バージョンに関係なくログオンできるようにするには、[**バージョン管理を有効にする**] をオフにして [**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24799-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="24799-121">Windows PowerShell コマンドレットを使用した既定のアクションの変更</span><span class="sxs-lookup"><span data-stu-id="24799-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="24799-122">ユーザーが明示的にサポートしていないクライアントまたはクライアントバージョンポリシーによって制限されていないクライアントを使用してユーザーがサインオンを試行したときに実行される既定のアクションは、Windows PowerShell コマンドラインインターフェイスおよび**Set-CsClientVersionPolicy**コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="24799-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="24799-123">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="24799-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24799-124">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="24799-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="24799-125">アクセスをブロックする既定のアクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="24799-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="24799-p104">次のコマンドでは、Redmond サイトの既定のアクションを "Block" に設定します。これにより、クライアント バージョン構成ルールが存在しないクライアントの登録が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="24799-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="24799-128">アクセスを許可するように既定のアクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="24799-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="24799-p105">この例では、Redmond サイトの既定のアクションが "Allow" に設定されています。これにより、クライアント バージョン構成ルールが存在しないクライアントの登録が許可されます。</span><span class="sxs-lookup"><span data-stu-id="24799-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="24799-131">詳細については、「 [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24799-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24799-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="24799-132">See Also</span></span>


[<span data-ttu-id="24799-133">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="24799-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する
description: 明示的にサポートまたは制限されていないクライアントの既定のアクションを変更します。
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
ms.openlocfilehash: 2c28ad4d357953c22f889309323ccbb95c6840e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566953"
---
# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="c075e-103">Lync Server 2013 で明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="c075e-103">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c075e-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c075e-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c075e-105">Lync Server 2013 環境でサポートするクライアントのバージョンを指定することに加えて、バージョンポリシーが定義されていないクライアントの既定のアクションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c075e-105">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="c075e-106">これにより、Lync Server 環境で使用するクライアントバージョンを制限することができます。これは、複数のクライアントバージョンのサポートに関連するコストの制御に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c075e-106">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="c075e-107">明示的にサポートまたは制限されていないクライアントの既定のアクションを変更するには</span><span class="sxs-lookup"><span data-stu-id="c075e-107">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="c075e-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c075e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c075e-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c075e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c075e-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c075e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c075e-111">左側のナビゲーション バーで [**クライアント**] をクリックし、[**クライアント バージョン構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c075e-111">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="c075e-112">[**クライアント バージョン構成**] ページで、リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c075e-112">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="c075e-113">[**クライアント バージョン構成の編集**] ダイアログ ボックスで [**バージョン管理を有効にする**] チェック ボックスがオンになっていることを確認し、[**既定のアクション**] で次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c075e-113">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="c075e-114">**許可**    クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合に、クライアントのログオンを許可します。</span><span class="sxs-lookup"><span data-stu-id="c075e-114">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="c075e-115">**ブロック**    クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合に、クライアントのログオンを禁止します。</span><span class="sxs-lookup"><span data-stu-id="c075e-115">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="c075e-116">URL を含む**ブロック**    クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合にクライアントのログオンを禁止し、新しいクライアントをダウンロードできる URL を含むエラーメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c075e-116">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="c075e-117">URL の使用**を許可する**    クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合にクライアントのログオンを許可します。また、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c075e-117">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="c075e-118">[**禁止して URL を表示**] を選択した場合は、エラー メッセージに含めるクライアントのダウンロード用 URL を [**URL**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="c075e-118">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="c075e-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c075e-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="c075e-120">クライアント バージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="c075e-120">To disable client version control</span></span>

  - <span data-ttu-id="c075e-121">バージョン管理を無効にしてすべてのクライアントがクライアント バージョンに関係なくログオンできるようにするには、[**バージョン管理を有効にする**] をオフにして [**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c075e-121">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c075e-122">Windows PowerShell コマンドレットを使用した既定のアクションの変更</span><span class="sxs-lookup"><span data-stu-id="c075e-122">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c075e-123">ユーザーが明示的にサポートしていないクライアントまたはクライアントバージョンポリシーによって制限されていないクライアントを使用してユーザーがサインオンを試行したときに実行される既定のアクションは、Windows PowerShell コマンドラインインターフェイスおよび **Set-CsClientVersionPolicy** コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="c075e-123">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="c075e-124">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c075e-124">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c075e-125">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="c075e-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="c075e-126">アクセスをブロックする既定のアクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="c075e-126">To configure the default action to block access</span></span>

  - <span data-ttu-id="c075e-p104">次のコマンドでは、Redmond サイトの既定のアクションを "Block" に設定します。これにより、クライアント バージョン構成ルールが存在しないクライアントの登録が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="c075e-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="c075e-129">アクセスを許可するように既定のアクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="c075e-129">To configure the default action to allow access</span></span>

  - <span data-ttu-id="c075e-p105">この例では、Redmond サイトの既定のアクションが "Allow" に設定されています。これにより、クライアント バージョン構成ルールが存在しないクライアントの登録が許可されます。</span><span class="sxs-lookup"><span data-stu-id="c075e-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="c075e-132">詳細については、「 [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c075e-132">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c075e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c075e-133">See Also</span></span>


[<span data-ttu-id="c075e-134">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="c075e-134">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


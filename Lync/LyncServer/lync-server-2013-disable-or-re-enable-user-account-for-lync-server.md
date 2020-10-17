---
title: 'Lync Server 2013: Lync Server のユーザーアカウントの無効化または再有効化'
description: 'Lync Server 2013: Lync Server のユーザーアカウントを無効にするか、再び有効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568173"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="1368c-103">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="1368c-103">Disable or re-enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1368c-104">_**トピックの最終更新日:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="1368c-104">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="1368c-105">次の手順を使用して、ユーザーアカウントに対して構成した Lync Server 設定を失わずに、Lync Server 2013 で既に有効になっているユーザーアカウントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1368c-105">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="1368c-106">Lync Server ユーザーアカウント設定が失われないため、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1368c-106">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1368c-107">Active Directory のユーザーアカウントを無効にしても、ユーザーが Lync Server にサインインしたり、Lync Server を使用したりでき <STRONG>なくなることはありません</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="1368c-107">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="1368c-108">これは、Lync は認証プロセスを合理化する証明書認証を使用し、これらのクライアント証明書は180日間有効であるためです。</span><span class="sxs-lookup"><span data-stu-id="1368c-108">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="1368c-109">Lync Server へのアクセスが Lync Server に対して有効になっていた、無効にされた Active Directory アカウントを停止するには、 <STRONG>ユーザー</STRONG> コマンドレットを使用するか、この記事で説明しているように <STRONG>Lync server コントロールパネル</STRONG> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1368c-109">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="1368c-110">ユーザーが Lync で無効にされ、中央管理ストアが環境内でレプリケートされ、ユーザーはサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1368c-110">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="1368c-111">また、サインインしているユーザーは切断されます。</span><span class="sxs-lookup"><span data-stu-id="1368c-111">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="1368c-112">Lync Server で既に有効になっているユーザーアカウントを無効にするか、再び有効にするには</span><span class="sxs-lookup"><span data-stu-id="1368c-112">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="1368c-113">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1368c-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1368c-114">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1368c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1368c-115">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1368c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1368c-116">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1368c-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1368c-117">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1368c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="1368c-118">表で、無効または再度有効にするユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1368c-118">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="1368c-119">[**アクション**] メニューで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1368c-119">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="1368c-120">Lync server 2013 のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1368c-120">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="1368c-121">Lync Server 2013 のユーザーアカウントを有効にするには、[ **Lync server の再有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1368c-121">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="1368c-122">Windows PowerShell を使用してユーザーアカウントを無効にするか、再度有効にする</span><span class="sxs-lookup"><span data-stu-id="1368c-122">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="1368c-123">ユーザーアカウントを一時的に無効にして **から、ユーザーコマンドレット** を使用して再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1368c-123">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="1368c-124">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="1368c-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1368c-125">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="1368c-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="1368c-126">ユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="1368c-126">To disable a user account</span></span>

  - <span data-ttu-id="1368c-127">ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="1368c-127">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="1368c-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1368c-128">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="1368c-129">ユーザーアカウントを再度有効にするには</span><span class="sxs-lookup"><span data-stu-id="1368c-129">To re-enable a user account</span></span>

  - <span data-ttu-id="1368c-130">無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="1368c-130">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="1368c-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1368c-131">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="1368c-132">詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1368c-132">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1368c-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="1368c-133">See Also</span></span>


[<span data-ttu-id="1368c-134">Lync Server 2013 のユーザーアカウントを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="1368c-134">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="1368c-135">Lync Server 2013 のユーザーの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="1368c-135">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


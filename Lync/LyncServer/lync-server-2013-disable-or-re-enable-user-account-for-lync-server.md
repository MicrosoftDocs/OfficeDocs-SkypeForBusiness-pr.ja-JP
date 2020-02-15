---
title: 'Lync Server 2013: Lync Server のユーザーアカウントの無効化または再有効化'
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
ms.openlocfilehash: cc7ed0572d36a87532c4845df887dc87ccb34eec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="79bbe-102">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="79bbe-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79bbe-103">_**トピックの最終更新日:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="79bbe-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="79bbe-104">次の手順を使用して、ユーザーアカウントに対して構成した Lync Server 設定を失わずに、Lync Server 2013 で既に有効になっているユーザーアカウントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="79bbe-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="79bbe-105">Lync Server ユーザーアカウント設定が失われないため、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="79bbe-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="79bbe-106">Active Directory のユーザーアカウントを無効にしても、ユーザーが Lync Server にサインインしたり、Lync Server を使用したりでき<STRONG>なくなることはありません</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="79bbe-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="79bbe-107">これは、Lync は認証プロセスを合理化する証明書認証を使用し、これらのクライアント証明書は180日間有効であるためです。</span><span class="sxs-lookup"><span data-stu-id="79bbe-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="79bbe-108">Lync Server へのアクセスが Lync Server に対して有効になっていた、無効にされた Active Directory アカウントを停止するには、<STRONG>ユーザー</STRONG>コマンドレットを使用するか、この記事で説明しているように<STRONG>Lync server コントロールパネル</STRONG>を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79bbe-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="79bbe-109">ユーザーが Lync で無効にされ、中央管理ストアが環境内でレプリケートされ、ユーザーはサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="79bbe-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="79bbe-110">また、サインインしているユーザーは切断されます。</span><span class="sxs-lookup"><span data-stu-id="79bbe-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="79bbe-111">Lync Server で既に有効になっているユーザーアカウントを無効にするか、再び有効にするには</span><span class="sxs-lookup"><span data-stu-id="79bbe-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="79bbe-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="79bbe-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79bbe-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79bbe-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79bbe-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bbe-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79bbe-115">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79bbe-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="79bbe-116">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79bbe-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="79bbe-117">表で、無効または再度有効にするユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="79bbe-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="79bbe-118">[**アクション**] メニューで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="79bbe-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="79bbe-119">Lync server 2013 のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79bbe-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="79bbe-120">Lync Server 2013 のユーザーアカウントを有効にするには、[ **Lync server の再有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79bbe-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="79bbe-121">Windows PowerShell を使用してユーザーアカウントを無効にするか、再度有効にする</span><span class="sxs-lookup"><span data-stu-id="79bbe-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="79bbe-122">ユーザーアカウントを一時的に無効にして**から、ユーザーコマンドレット**を使用して再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="79bbe-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="79bbe-123">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="79bbe-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="79bbe-124">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bbe-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="79bbe-125">ユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="79bbe-125">To disable a user account</span></span>

  - <span data-ttu-id="79bbe-126">ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="79bbe-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="79bbe-127">例:</span><span class="sxs-lookup"><span data-stu-id="79bbe-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="79bbe-128">ユーザーアカウントを再度有効にするには</span><span class="sxs-lookup"><span data-stu-id="79bbe-128">To re-enable a user account</span></span>

  - <span data-ttu-id="79bbe-129">無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="79bbe-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="79bbe-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79bbe-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="79bbe-131">詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79bbe-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79bbe-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="79bbe-132">See Also</span></span>


[<span data-ttu-id="79bbe-133">Lync Server 2013 のユーザーアカウントを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="79bbe-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="79bbe-134">Lync Server 2013 のユーザーの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="79bbe-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


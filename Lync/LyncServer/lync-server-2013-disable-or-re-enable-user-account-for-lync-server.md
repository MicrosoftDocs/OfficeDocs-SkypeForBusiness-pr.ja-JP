---
title: 'Lync Server 2013: Lync Server のユーザーアカウントを無効にするか、再び有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="275c6-102">Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="275c6-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="275c6-103">_**最終更新日:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="275c6-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="275c6-104">次の手順を使用して、ユーザーアカウント用に構成した Lync Server の設定を失わずに、Lync Server 2013 で以前に有効になっていたユーザーアカウントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="275c6-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="275c6-105">Lync Server のユーザーアカウント設定が失われないため、ユーザーアカウントを再構成することなく、以前に有効になっていたユーザーアカウントを再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="275c6-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="275c6-106">Active Directory のユーザーアカウントを無効にしても、ユーザーが Lync Server にサインインしたり、使用できなくなること<STRONG>はありません</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="275c6-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="275c6-107">これは、Lync では認証プロセスを合理化する証明書認証が使用されるため、これらのクライアント証明書は180日間有効です。</span><span class="sxs-lookup"><span data-stu-id="275c6-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="275c6-108">Lync Server へのアクセス許可が有効になっていた Active Directory アカウントを無効にするには、[<STRONG>無効</STRONG>にする] を使用するか、この記事で説明されているように<STRONG>Lync server コントロールパネル</STRONG>を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="275c6-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="275c6-109">ユーザーが Lync で無効になっており、中央管理ストアが環境内でレプリケートされた後、ユーザーはサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="275c6-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="275c6-110">また、サインインしたユーザーは切断されます。</span><span class="sxs-lookup"><span data-stu-id="275c6-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="275c6-111">Lync Server で以前に有効になっていたユーザーアカウントを無効にするか、再び有効にするには</span><span class="sxs-lookup"><span data-stu-id="275c6-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="275c6-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="275c6-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="275c6-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="275c6-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="275c6-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="275c6-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="275c6-115">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="275c6-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="275c6-116">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、またはもう一度有効にするユーザーアカウントの Ip Uniform リソース識別子 (URI) のすべてまたは最初の部分を入力します。[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="275c6-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="275c6-117">表で、無効にする、またはもう一度有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="275c6-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="275c6-118">[**アクション**] メニューで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="275c6-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="275c6-119">Lync Server 2013 のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="275c6-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="275c6-120">Lync Server 2013 のユーザーアカウントを有効にするには、[ **Lync server の場合は再度有効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="275c6-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="275c6-121">Windows PowerShell を使用してユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="275c6-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="275c6-122">ユーザーアカウントは一時的に無効にすることができます。また、**設定-CsUser**コマンドレットを使用して、後で再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="275c6-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="275c6-123">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="275c6-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="275c6-124">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="275c6-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="275c6-125">ユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="275c6-125">To disable a user account</span></span>

  - <span data-ttu-id="275c6-126">ユーザーアカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="275c6-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="275c6-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="275c6-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="275c6-128">ユーザーアカウントを再度有効にするには</span><span class="sxs-lookup"><span data-stu-id="275c6-128">To re-enable a user account</span></span>

  - <span data-ttu-id="275c6-129">無効のユーザーアカウントを再び有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="275c6-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="275c6-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="275c6-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="275c6-131">詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="275c6-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="275c6-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="275c6-132">See Also</span></span>


[<span data-ttu-id="275c6-133">Lync Server 2013 のユーザーアカウントを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="275c6-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="275c6-134">Lync Server 2013 のユーザーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="275c6-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


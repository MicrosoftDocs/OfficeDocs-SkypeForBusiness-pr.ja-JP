---
title: 'Lync Server 2013: クライアントのバージョン管理を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c575a861644c27a0dba93790667ece9b973211e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="eea58-102">Lync Server 2013 でクライアントのバージョン管理を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="eea58-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eea58-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eea58-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eea58-104">クライアントバージョンの構成設定を使用して、クライアントバージョンの制御をグローバルに、または特定のサイトに対して有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="eea58-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="eea58-105">グローバルクライアントバージョン構成は、Lync Server 2013 と共にインストールされ、サーバー展開全体でクライアントバージョン管理を有効または無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eea58-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="eea58-106">グローバル構成が有効になっている場合、ユーザーがログオンを試行すると、設定したすべてのクライアントバージョンポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="eea58-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="eea58-107">クライアントバージョン管理を行わない場合は、グローバルクライアントバージョン構成を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eea58-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="eea58-108">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから、クライアントのバージョン管理を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eea58-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eea58-109">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="eea58-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="eea58-110">Lync Server コントロールパネルを使用してクライアントのバージョン管理を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="eea58-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="eea58-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eea58-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eea58-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="eea58-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eea58-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea58-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eea58-114">左側のナビゲーションバーで [**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eea58-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="eea58-115">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="eea58-115">Do the following:</span></span>
    
      - <span data-ttu-id="eea58-116">クライアントのバージョン管理をグローバルに有効または無効にするには、**グローバル**構成をダブルクリックし、設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="eea58-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="eea58-117">特定のサイトのクライアントバージョン管理を有効または無効にするには、[**新規**] をクリックし、サイトを選択して [ **OK**] をクリックし、サイトの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="eea58-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eea58-118">Windows PowerShell コマンドレットを使用してクライアントのバージョン管理を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="eea58-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eea58-119">クライアントのバージョン管理を有効または無効にするには、 **Set-CsClientVersionConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eea58-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="eea58-120">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="eea58-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eea58-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea58-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="eea58-122">クライアントのバージョン管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="eea58-122">To enable client versioning</span></span>

  - <span data-ttu-id="eea58-123">クライアントのバージョン管理を有効にするには、 **Enabled**プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="eea58-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="eea58-124">クライアントのバージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="eea58-124">To disable client versioning</span></span>

  - <span data-ttu-id="eea58-125">**Enabled**プロパティを False ($False) に設定すると、クライアントのバージョン管理を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eea58-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="eea58-126">詳細については、「 [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea58-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


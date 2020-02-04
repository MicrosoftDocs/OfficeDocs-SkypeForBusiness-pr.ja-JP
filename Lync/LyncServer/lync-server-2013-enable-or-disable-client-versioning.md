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
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="b5c63-102">Lync Server 2013 でクライアントのバージョン管理を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b5c63-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5c63-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b5c63-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b5c63-104">クライアントバージョンの構成設定は、グローバルに、または特定のサイトに対して、クライアントのバージョン管理をオンまたはオフにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5c63-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="b5c63-105">グローバルクライアントバージョンの構成は、Lync Server 2013 と共にインストールされ、サーバー展開全体でクライアントのバージョン管理を有効または無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5c63-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="b5c63-106">グローバル構成が有効になっている場合は、ユーザーがログオンしようとしたときに、使用しているクライアントバージョンポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b5c63-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="b5c63-107">クライアントのバージョン管理を行わない場合は、グローバルクライアントのバージョン設定を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5c63-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="b5c63-108">Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からクライアントのバージョン管理を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5c63-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5c63-109">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="b5c63-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="b5c63-110">Lync Server コントロールパネルを使用してクライアントのバージョン管理を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="b5c63-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b5c63-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b5c63-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5c63-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b5c63-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5c63-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5c63-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5c63-114">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5c63-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="b5c63-115">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5c63-115">Do the following:</span></span>
    
      - <span data-ttu-id="b5c63-116">クライアントのバージョン管理をグローバルに有効または無効にするには、**グローバル**構成をダブルクリックして、設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="b5c63-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="b5c63-117">特定のサイトのクライアントのバージョン管理を有効または無効にするには、[**新規**] をクリックし、サイトを選択し、[ **OK**] をクリックして、サイトの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="b5c63-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b5c63-118">Windows PowerShell コマンドレットを使用してクライアントのバージョン管理を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b5c63-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b5c63-119">クライアントのバージョン管理を有効または無効にするには、 **Set-CsClientVersionConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5c63-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="b5c63-120">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5c63-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b5c63-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5c63-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="b5c63-122">クライアントのバージョン管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="b5c63-122">To enable client versioning</span></span>

  - <span data-ttu-id="b5c63-123">クライアントのバージョン管理を有効にするには、 **Enabled**プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5c63-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="b5c63-124">クライアントのバージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="b5c63-124">To disable client versioning</span></span>

  - <span data-ttu-id="b5c63-125">クライアントのバージョン管理を無効にするには、 **Enabled**プロパティを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5c63-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="b5c63-126">詳細については、「 [Set-CsClientVersionConfiguration)](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5c63-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


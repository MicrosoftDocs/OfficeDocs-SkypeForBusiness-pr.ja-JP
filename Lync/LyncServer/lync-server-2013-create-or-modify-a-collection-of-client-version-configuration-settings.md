---
title: クライアントバージョンの構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7ed33-102">Lync Server 2013 でクライアントのバージョン構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="7ed33-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ed33-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7ed33-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7ed33-104">クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="7ed33-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="7ed33-105">グローバルクライアントバージョンの構成は Lync Server と共にインストールされ、サーバーの展開全体に対してクライアントのバージョン管理を有効または無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ed33-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="7ed33-106">個々のサイトのクライアントのバージョン構成設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ed33-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="7ed33-107">Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からクライアントバージョンの構成設定を作成または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7ed33-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7ed33-108">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="7ed33-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="7ed33-109">Lync Server コントロールパネルを使用してクライアントのバージョン設定を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="7ed33-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7ed33-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7ed33-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ed33-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ed33-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ed33-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7ed33-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ed33-113">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ed33-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="7ed33-114">[**クライアントのバージョン設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7ed33-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="7ed33-115">新しい構成を作成するには、[**新規**] をクリックし、サイトを選択して、[ **OK]** をクリックし、設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="7ed33-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="7ed33-116">構成を変更するには、構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックして、設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="7ed33-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ed33-117">Windows PowerShell コマンドレットを使用してクライアントのバージョン構成設定を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="7ed33-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7ed33-118">**新しい-CsClientVersionConfiguration**コマンドレットを使用してクライアントバージョンの構成設定を作成し、**その設定を**変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7ed33-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="7ed33-119">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ed33-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7ed33-120">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ed33-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="7ed33-121">クライアントのバージョン構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="7ed33-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="7ed33-122">次のコマンドは、Redmond サイトに適用されるクライアントのバージョン構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ed33-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="7ed33-123">この例では、レドモンドサイトのクライアントバージョン管理が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7ed33-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="7ed33-124">サイトのクライアントのバージョン管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="7ed33-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="7ed33-125">このコマンドにより、レドモンドサイトのクライアントのバージョン管理が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7ed33-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="7ed33-126">組織全体でクライアントのバージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="7ed33-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="7ed33-127">この例では、組織で使用されているすべてのクライアントバージョンの構成設定について、クライアントのバージョン管理が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7ed33-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="7ed33-128">詳細については、「[新しい-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) ()」と「 [csclientversionconfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))コマンドレットを設定する」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ed33-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


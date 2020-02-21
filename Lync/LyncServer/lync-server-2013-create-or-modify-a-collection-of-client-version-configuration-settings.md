---
title: クライアントバージョン構成設定のコレクションを作成または変更する
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
ms.openlocfilehash: 6851a332b0b2c33d769328a0656f206d5f7d271c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="674b1-102">Lync Server 2013 でクライアントバージョン構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="674b1-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="674b1-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="674b1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="674b1-104">クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="674b1-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="674b1-105">グローバルクライアントバージョン構成は Lync Server と共にインストールされ、サーバー展開全体に対してクライアントバージョン制御を有効または無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="674b1-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="674b1-106">また、個々のサイトのクライアントバージョン構成設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="674b1-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="674b1-107">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから、クライアントバージョン構成設定を作成または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="674b1-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="674b1-108">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="674b1-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="674b1-109">Lync Server コントロールパネルを使用してクライアントバージョン構成設定を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="674b1-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="674b1-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="674b1-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="674b1-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="674b1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="674b1-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="674b1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="674b1-113">左側のナビゲーションバーで [**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="674b1-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="674b1-114">[**クライアントバージョン構成**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="674b1-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="674b1-115">新しい構成を作成するには、[**新規**] をクリックし、サイトを選択して [ **OK]** をクリックし、設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="674b1-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="674b1-116">構成を変更するには、構成を選択し、[**編集**]、[**詳細の表示**] の順にクリックし、設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="674b1-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="674b1-117">Windows PowerShell コマンドレットを使用してクライアントバージョン構成設定を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="674b1-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="674b1-118">クライアントバージョン構成設定を作成するには、**新しい-CsClientVersionConfiguration**コマンドレットを使用し、これらを変更するには、 **Set-csclientversionconfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="674b1-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="674b1-119">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="674b1-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="674b1-120">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="674b1-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="674b1-121">クライアントバージョン構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="674b1-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="674b1-122">次のコマンドは、Redmond サイトに適用されるクライアントバージョン構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="674b1-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="674b1-123">この例では、Redmond サイトのクライアントバージョン管理は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="674b1-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="674b1-124">サイトのクライアントバージョン管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="674b1-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="674b1-125">このコマンドは、Redmond サイトのクライアントバージョン管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="674b1-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="674b1-126">組織全体でクライアントのバージョン管理を無効にするには</span><span class="sxs-lookup"><span data-stu-id="674b1-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="674b1-127">この例では、組織で使用されているすべてのクライアントバージョン構成設定についてクライアントバージョン管理が無効になります。</span><span class="sxs-lookup"><span data-stu-id="674b1-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="674b1-128">詳細については、ヘルプトピックの「[新しい-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) 」と「 [Set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="674b1-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


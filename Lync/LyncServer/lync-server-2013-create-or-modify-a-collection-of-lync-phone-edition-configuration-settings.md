---
title: Lync Phone Edition 構成設定のコレクションを作成または変更する
description: Lync Phone Edition 構成設定のコレクションを作成または変更します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82a4becadf581ec965952e507c3eb2839b622d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578253"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f4bcd-103">Lync Server 2013 の Lync Phone Edition 構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f4bcd-103">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4bcd-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f4bcd-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f4bcd-105">Lync Server をインストールすると、Lync Phone Edition 設定のグローバルコレクションが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-105">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="f4bcd-106">これらの設定は、展開で Lync Phone Edition を実行しているすべてのデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-106">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="f4bcd-107">これらの設定はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-107">You can change these settings at any time.</span></span> <span data-ttu-id="f4bcd-108">また、特定のサイト内のデバイスに適用される新しい設定のコレクションを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-108">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="f4bcd-109">サイト設定はグローバル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-109">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="f4bcd-110">構成設定は、コレクション名、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログ レベル、音声のサービス品質 (QoS) レベル、電話のロックの設定、および電話のロックの詳細 (暗証番号 (PIN) を解除する必要がある期間と、電話が自動的にロックされる前に電話がアイドル状態になる期間) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-110">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="f4bcd-111">Lync Phone Edition の構成設定のコレクションを作成するか、既存のコレクションの設定を編集するには</span><span class="sxs-lookup"><span data-stu-id="f4bcd-111">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="f4bcd-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4bcd-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4bcd-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4bcd-115">左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイス構成**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f4bcd-116">[**デバイス構成**] ページで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-116">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f4bcd-117">Lync Phone Edition 構成設定の新しいコレクションを作成するには、[ **新規**] をクリックし、サイトを選択して [ **OK**] をクリックし、既定の設定を確認し、必要に応じて変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-117">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="f4bcd-118">既存のコレクションの設定を変更するには、コレクションをクリックし、[**編集**] メニューをクリックします。[**詳細の表示**] をクリックし、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-118">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="f4bcd-p103">グローバル コレクションの既定の設定に戻すには、[<STRONG>編集</STRONG>] メニューをクリックして [<STRONG>削除</STRONG>] をクリックし、[<STRONG>OK</STRONG>] をクリックします。この操作では、グローバル コレクションが削除されるのではなく、設定が既定にリセットされるだけです。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="f4bcd-121">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f4bcd-122">Windows PowerShell コマンドレットを使用して新しい Lync Phone Edition 構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="f4bcd-122">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f4bcd-123">Lync Phone Edition の構成設定は、Windows PowerShell と **get-csucphoneconfiguration** コマンドレットを使用して (サイトスコープでのみ) 作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-123">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="f4bcd-124">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-124">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f4bcd-125">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="f4bcd-126">既定値を使用する新しい Lync Phone Edition の構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="f4bcd-126">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="f4bcd-127">次のコマンドでは、Redmond サイト用に UC 電話構成設定の新しいセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-127">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="f4bcd-128">このコマンドでは (必須の Identity パラメーター以外の) パラメーターが指定されていないため、新しい構成設定のコレクションでは、すべてのプロパティに既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-128">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="f4bcd-129">新しい Lync Phone Edition 構成設定を作成するときに1つのプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="f4bcd-129">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="f4bcd-p105">別のプロパティ値を使用する設定を作成するには、該当するパラメーターとパラメータ値を追加します。たとえば、既定で電話のロックを必要とする UC 電話構成設定のコレクションを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="f4bcd-132">新しい Lync Phone Edition 構成設定の作成時に複数のプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="f4bcd-132">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="f4bcd-p106">複数のパラメーターを含めることにより、複数のプロパティ値を変更できます。たとえば次のコマンドでは、電話のロックを適用し、さらに PIN の最小桁数を 8 桁に設定します。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="f4bcd-135">詳細については、「 [get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4bcd-135">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4bcd-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4bcd-136">See Also</span></span>


[<span data-ttu-id="f4bcd-137">Lync Server 2013 の Lync Phone Edition 構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="f4bcd-137">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="f4bcd-138">Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f4bcd-138">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="f4bcd-139">Lync Server 2013 での電話ロックの適用</span><span class="sxs-lookup"><span data-stu-id="f4bcd-139">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


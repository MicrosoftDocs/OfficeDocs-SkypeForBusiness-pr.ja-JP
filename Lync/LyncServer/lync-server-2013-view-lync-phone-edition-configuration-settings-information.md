---
title: 'Lync Server 2013: Lync Phone Edition 構成設定情報の表示'
description: 'Lync Server 2013: Lync Phone Edition 構成設定情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576433"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="70a7d-103">Lync Server 2013 での Lync Phone Edition の構成設定情報の表示</span><span class="sxs-lookup"><span data-stu-id="70a7d-103">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70a7d-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="70a7d-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="70a7d-105">Lync Phone Edition を実行しているデバイスに関する構成情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-105">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="70a7d-106">情報はコレクションにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="70a7d-106">The information is organized into collections.</span></span> <span data-ttu-id="70a7d-107">Lync Server をインストールすると、展開で Lync Phone Edition を実行しているすべてのデバイスに適用される Lync Phone Edition の設定のコレクションが取得されます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-107">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="70a7d-108">特定のサイトに対して、設定の新しいコレクションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-108">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="70a7d-109">サイト設定は、グローバル設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-109">Site settings take precedence over global settings.</span></span> <span data-ttu-id="70a7d-110">設定の各コレクションは、名前、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログ レベル、音声のサービス品質 (QoS) レベル、電話ロック設定、および電話ロックの詳細 (ロック解除の暗証番号 (PIN) の最小桁数および電話が自動ロックされるまでの時間) で構成されています。</span><span class="sxs-lookup"><span data-stu-id="70a7d-110">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="70a7d-111">Lync Phone Edition を実行しているデバイスに関する構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="70a7d-111">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="70a7d-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="70a7d-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70a7d-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70a7d-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a7d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70a7d-115">左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイスの構成**] 移動ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70a7d-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="70a7d-p103">[**デバイスの構成**] ページで、情報を表示する設定のコレクションをクリックします。名前、スコープ、SIP セキュリティ設定、音声の品質レベル、および電話ロック設定がメイン ページに表示されます。ログ レベルと電話ロックの詳細を表示するには、[**編集**] メニューをクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70a7d-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="70a7d-119">Windows PowerShell コマンドレットを使用して Lync Phone Edition の構成情報を表示する</span><span class="sxs-lookup"><span data-stu-id="70a7d-119">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="70a7d-120">Lync Server 管理シェルと **get-csucphoneconfiguration** コマンドレットを使用して、Lync Phone Edition の構成設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-120">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="70a7d-121">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-121">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="70a7d-122">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a7d-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="70a7d-123">Lync Phone Edition の構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="70a7d-123">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="70a7d-124">すべての Lync Phone Edition 構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="70a7d-124">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="70a7d-125">コマンドを実行すると、次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="70a7d-125">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="70a7d-126">詳細については、「 [get-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a7d-126">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70a7d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="70a7d-127">See Also</span></span>


[<span data-ttu-id="70a7d-128">Lync Server 2013 の Lync Phone Edition 構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="70a7d-128">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="70a7d-129">Lync Server 2013 の Lync Phone Edition 構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="70a7d-129">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="70a7d-130">Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="70a7d-130">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="70a7d-131">Lync Server 2013 での電話ロックの適用</span><span class="sxs-lookup"><span data-stu-id="70a7d-131">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


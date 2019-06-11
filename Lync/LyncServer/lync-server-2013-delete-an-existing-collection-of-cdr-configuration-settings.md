---
title: 'Lync Server 2013: CDR 構成設定の既存のコレクションを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="505e3-102">Lync Server 2013 で既存の CDR 構成設定のコレクションを削除する</span><span class="sxs-lookup"><span data-stu-id="505e3-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="505e3-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="505e3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="505e3-p101">通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="505e3-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="505e3-106">Microsoft Lync Server 2013 をインストールすると、1つのグローバルな CDR 構成設定が作成されます。</span><span class="sxs-lookup"><span data-stu-id="505e3-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="505e3-107">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="505e3-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="505e3-108">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="505e3-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="505e3-109">サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="505e3-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="505e3-p103">なお、"削除" はグローバル設定に対しても実行できます。ただし、グローバル設定は実際には削除されません。代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。たとえば、既定では CDR 構成設定のコレクションで削除が有効になります。削除が無効になるようにグローバル コレクションを変更すると想定します。後でグローバル設定を削除した場合、すべてのプロパティが既定値にリセットされます。この場合、削除が再び有効になります。</span><span class="sxs-lookup"><span data-stu-id="505e3-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="505e3-117">[Lync Server] コントロールパネルまたは[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration)コマンドレットを使用して、CDR 構成設定を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="505e3-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="505e3-118">Lync Server コントロールパネルで CDR の設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="505e3-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="505e3-119">Lync Server コントロールパネルで、[**監視とアーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="505e3-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="505e3-p104">[**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="505e3-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="505e3-122">[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="505e3-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="505e3-123">[Lync Server コントロールパネル] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="505e3-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="505e3-124">Windows PowerShell コマンドレットを使用して CDR 構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="505e3-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="505e3-125">Windows PowerShell と CsCdrConfiguration コマンドレットを使用して、通話の詳細**な**レコーディング設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="505e3-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="505e3-126">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="505e3-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="505e3-127">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="505e3-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="505e3-128">指定された CDR 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="505e3-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="505e3-129">このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="505e3-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="505e3-130">サイト スコープに適用されていた CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="505e3-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="505e3-131">このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="505e3-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="505e3-132">通話詳細記録を無効にする CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="505e3-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="505e3-133">このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="505e3-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="505e3-134">詳細については、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="505e3-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


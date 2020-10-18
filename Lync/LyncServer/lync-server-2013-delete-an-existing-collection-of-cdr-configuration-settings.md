---
title: 'Lync Server 2013: CDR 構成設定の既存コレクションの削除'
description: 'Lync Server 2013: CDR 構成設定の既存のコレクションを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e80f6d9e9d878dad258e494095b10c402029932b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572893"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c0d43-103">Lync Server 2013 での CDR 構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="c0d43-103">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0d43-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c0d43-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c0d43-p101">通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="c0d43-107">Microsoft Lync Server 2013 をインストールすると、CDR 構成設定のグローバルコレクションが1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="c0d43-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c0d43-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="c0d43-109">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="c0d43-110">サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="c0d43-p103">なお、"削除" はグローバル設定に対しても実行できます。ただし、グローバル設定は実際には削除されません。代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。たとえば、既定では CDR 構成設定のコレクションでパージが有効になります。パージが無効になるようにグローバル コレクションを変更すると想定します。後でグローバル設定を削除した場合、すべてのプロパティが既定値にリセットされます。この場合、パージが再び有効になります。</span><span class="sxs-lookup"><span data-stu-id="c0d43-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="c0d43-118">CDR 構成設定は、Lync Server コントロールパネルまたは [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-118">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="c0d43-119">Lync Server コントロールパネルを使用して CDR 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="c0d43-119">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c0d43-120">Lync Server コントロールパネルで、[ **監視とアーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0d43-120">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="c0d43-p104">[**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0d43-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="c0d43-123">[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0d43-123">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="c0d43-124">[Lync Server コントロールパネル] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0d43-124">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c0d43-125">Windows PowerShell コマンドレットを使用して CDR 構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="c0d43-125">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c0d43-126">通話詳細記録の構成設定は、Windows PowerShell と **set-cscdrconfiguration** コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="c0d43-127">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-127">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c0d43-128">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d43-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="c0d43-129">指定された CDR 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="c0d43-129">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="c0d43-130">このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-130">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="c0d43-131">サイトスコープに適用されているすべての CDR 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="c0d43-131">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="c0d43-132">このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-132">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="c0d43-133">通話詳細記録を無効にする CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="c0d43-133">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="c0d43-134">このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c0d43-134">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="c0d43-135">詳細については、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d43-135">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


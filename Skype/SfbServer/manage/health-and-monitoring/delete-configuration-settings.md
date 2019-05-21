---
title: Skype for Business Server で既にある CDR 構成設定のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '概要: Skype for Business Server で CDR 構成設定を削除する方法について説明します。'
ms.openlocfilehash: 91ee9676b3087c5b125c6cfe935f706bbfb22812
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305835"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="42a58-103">Skype for Business Server で既にある CDR 構成設定のコレクションを削除する</span><span class="sxs-lookup"><span data-stu-id="42a58-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="42a58-104">**概要:** Skype for Business Server で CDR の設定を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42a58-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="42a58-p101">通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="42a58-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="42a58-107">Skype for Business Server をインストールすると、1つのグローバルな CDR 構成設定が作成されます。</span><span class="sxs-lookup"><span data-stu-id="42a58-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="42a58-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="42a58-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="42a58-109">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="42a58-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="42a58-110">サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="42a58-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="42a58-111">グローバル設定を "削除" することもできます。</span><span class="sxs-lookup"><span data-stu-id="42a58-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="42a58-112">ただし、グローバル設定は実際に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="42a58-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="42a58-113">代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="42a58-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="42a58-114">たとえば、既定では CDR 構成設定のコレクションで削除が有効になります。</span><span class="sxs-lookup"><span data-stu-id="42a58-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="42a58-115">削除が無効になるようにグローバル コレクションを変更すると想定します。</span><span class="sxs-lookup"><span data-stu-id="42a58-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="42a58-116">後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="42a58-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="42a58-117">この場合、削除が再び有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="42a58-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="42a58-118">CDR 構成設定は、Skype for Business Server コントロールパネルまたは[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="42a58-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="42a58-119">Skype for Business Server コントロールパネルで CDR の設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="42a58-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="42a58-120">Skype for Business Server コントロールパネルで、[**監視とアーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42a58-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="42a58-p104">[**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="42a58-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="42a58-123">[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42a58-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="42a58-124">[Skype for Business Server コントロールパネル] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42a58-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="42a58-125">Windows PowerShell コマンドレットを使用して CDR 構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="42a58-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="42a58-126">Windows PowerShell と CsCdrConfiguration コマンドレットを使用して、通話の詳細**な**レコーディング設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="42a58-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="42a58-127">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="42a58-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="42a58-128">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42a58-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="42a58-129">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="42a58-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="42a58-130">指定された CDR 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="42a58-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="42a58-131">このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="42a58-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="42a58-132">サイト スコープに適用されていた CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="42a58-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="42a58-133">このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="42a58-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="42a58-134">通話詳細記録を無効にする CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="42a58-134">To remove all the CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="42a58-135">このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="42a58-135">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="42a58-136">詳細については、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42a58-136">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42a58-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="42a58-137">See also</span></span>

[<span data-ttu-id="42a58-138">Skype for Business Server で通話の記録とエクスペリエンスデータベースの再生の詳細を手動で削除する</span><span class="sxs-lookup"><span data-stu-id="42a58-138">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)


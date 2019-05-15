---
title: CDR 構成設定の Skype ビジネス サーバーの既存のコレクションを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '概要: は、Skype のビジネス サーバーの CDR 構成設定を削除する方法を説明します。'
ms.openlocfilehash: 2319cd8548b3f183af6e54bbe1f24870093ae641
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926551"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b9ca9-103">CDR 構成設定の Skype ビジネス サーバーの既存のコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b9ca9-104">**の概要:** Skype のビジネス サーバーの CDR 構成設定を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b9ca9-p101">通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="b9ca9-107">ビジネス サーバー、1 つの Skype をインストールすると、CDR 構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="b9ca9-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="b9ca9-109">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="b9ca9-110">サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="b9ca9-111">削除することも""グローバル設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="b9ca9-112">ただし、グローバル設定は実際に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="b9ca9-113">代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="b9ca9-114">たとえば、既定では CDR 構成設定のコレクションで削除が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="b9ca9-115">削除が無効になるようにグローバル コレクションを変更すると想定します。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="b9ca9-116">後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="b9ca9-117">この場合、削除が再び有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="b9ca9-118">CDR 構成設定を削除するには、Skype をビジネス サーバーのコントロール パネルの[削除 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="b9ca9-119">ビジネス サーバーのコントロール パネルの Skype で CDR 構成設定を削除するのには</span><span class="sxs-lookup"><span data-stu-id="b9ca9-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9ca9-120">ビジネス サーバーのコントロール パネルの Skype は、[**監視およびアーカイブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="b9ca9-p104">[**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="b9ca9-123">[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="b9ca9-124">[Skype ビジネス サーバーのコントロール パネル] ダイアログ ボックスでは、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b9ca9-125">Windows PowerShell コマンドレットを使用して、CDR 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b9ca9-126">Windows PowerShell と**削除 CsCdrConfiguration**コマンドレットを使用して構成設定を記録する呼び出しの詳細を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="b9ca9-127">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b9ca9-128">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b9ca9-129">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="b9ca9-130">指定された CDR 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="b9ca9-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="b9ca9-131">このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b9ca9-132">サイト スコープに適用されていた CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="b9ca9-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="b9ca9-133">このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="b9ca9-134">通話詳細記録を無効にする CDR 構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="b9ca9-134">To remove all the CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="b9ca9-135">このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-135">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="b9ca9-136">詳細については、[削除 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-136">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9ca9-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9ca9-137">See also</span></span>

[<span data-ttu-id="b9ca9-138">ビジネス サーバーの通話詳細記録と Skype で高品質なエクスペリエンスのデータベースを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="b9ca9-138">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)


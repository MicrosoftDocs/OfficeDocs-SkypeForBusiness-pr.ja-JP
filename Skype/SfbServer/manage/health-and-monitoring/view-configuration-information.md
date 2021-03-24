---
title: Skype for Business Server で CDR 構成情報を表示する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '概要: Skype for Business Server で通話詳細記録 (CDR) を使用する方法について説明します。'
ms.openlocfilehash: fb832a3e0fcde7500b0516fb9a9672ab228d47ae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098903"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="aa1e5-103">Skype for Business Server で CDR 構成情報を表示する</span><span class="sxs-lookup"><span data-stu-id="aa1e5-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="aa1e5-104">**概要:** Skype for Business Server で通話詳細記録 (CDR) を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="aa1e5-p101">通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="aa1e5-107">Skype for Business Server をインストールすると、CDR 構成設定の単一のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="aa1e5-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="aa1e5-109">Skype for Business Server コントロール パネルまたは [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) コマンドレットを使用して、組織内で使用されている CDR 構成設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="aa1e5-110">Skype for Business Server コントロール パネルを使用して CDR 構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="aa1e5-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="aa1e5-111">[Skype for Business Server コントロール パネル] で、[監視 **とアーカイブ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="aa1e5-p103">すべての CDR 構成設定の一覧が、[**通話詳細記録**] タブに表示されます。設定の各コレクションについて、コレクションの [**名前**]、CDR が有効になっているかどうか ([**CDR**] プロパティ)、削除が有効になっているかどうか ([**CDR の削除**] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して [**編集**] をクリックし、続いて [**詳細の表示**] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aa1e5-115">CDR 構成情報の表示には、Windows PowerShellコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="aa1e5-116">CDR 構成設定を表示するには、Windows PowerShellコマンドレットをGet-CsCdrConfigurationします。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="aa1e5-117">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aa1e5-118">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="aa1e5-119">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="aa1e5-120">CDR の構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="aa1e5-120">To view CDR configuration information</span></span>

- <span data-ttu-id="aa1e5-121">すべての CDR 構成設定に関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="aa1e5-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="aa1e5-123">詳細については [、Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa1e5-123">For more information, see the help topic for the [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

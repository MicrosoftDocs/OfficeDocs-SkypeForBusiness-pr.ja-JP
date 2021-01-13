---
title: Skype for Business Server での Quality of Experience 構成設定の削除
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '概要: Skype for Business Server で QoE (Quality of Experience) 設定を削除する方法について学習します。'
ms.openlocfilehash: 45150b6aa2e6f48eedb28f180cfff8f291f58abc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816937"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f4d61-103">Skype for Business Server での Quality of Experience 構成設定の削除</span><span class="sxs-lookup"><span data-stu-id="f4d61-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="f4d61-104">**概要:** Skype for Business Server で QoE (Quality of Experience) 設定を削除する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="f4d61-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="f4d61-p101">QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="f4d61-107">Skype for Business Server をインストールすると、QoE 構成設定の単一のグローバル コレクションが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="f4d61-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f4d61-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="f4d61-109">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="f4d61-110">サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="f4d61-111">グローバル設定を "削除" することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="f4d61-112">ただし、グローバル設定は実際に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f4d61-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="f4d61-113">代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="f4d61-114">たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f4d61-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="f4d61-115">仮にグローバル コレクションを変更して削除を無効にしたとします。</span><span class="sxs-lookup"><span data-stu-id="f4d61-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="f4d61-116">後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="f4d61-117">この場合、削除が再び有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f4d61-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="f4d61-118">QoE 構成設定は、Skype for Business Server コントロール パネルまたは [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f4d61-119">Skype for Business Server コントロール パネルを使用して QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="f4d61-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f4d61-p104">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d61-p104">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f4d61-122">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4d61-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f4d61-123">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d61-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="f4d61-124">[**QoE データ**] ページで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d61-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="f4d61-125">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d61-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f4d61-126">コマンドレットを使用した QoE 構成設定Windows PowerShell削除する</span><span class="sxs-lookup"><span data-stu-id="f4d61-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f4d61-127">QoE 構成設定を削除するには、次のWindows PowerShell **Remove-CsQoEConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f4d61-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="f4d61-128">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f4d61-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f4d61-129">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d61-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f4d61-130">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="f4d61-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="f4d61-131">指定した QoE 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="f4d61-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="f4d61-132">このコマンドは、Redmond サイトに適用された QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="f4d61-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f4d61-133">サイト スコープに適用されたすべての QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="f4d61-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="f4d61-134">このコマンドは、サイト スコープに適用されたすべての QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="f4d61-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="f4d61-135">QoE 監視が無効にされたすべての QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="f4d61-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="f4d61-136">このコマンドは、QoE 監視が無効にされたすべての QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="f4d61-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="f4d61-137">詳細については [、「Remove-CsQoEConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4d61-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4d61-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4d61-138">See also</span></span>

[<span data-ttu-id="f4d61-139">Skype for Business Server で通話詳細記録データベースと Quality of Experience データベースを手動で削除する</span><span class="sxs-lookup"><span data-stu-id="f4d61-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)


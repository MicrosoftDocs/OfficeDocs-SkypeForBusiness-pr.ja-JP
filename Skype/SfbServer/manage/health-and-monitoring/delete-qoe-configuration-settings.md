---
title: Skype for Business Server 2015 での QoE (Quality of Experience) 構成設定の削除
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '概要: ビジネス サーバー 2015 の Skype の高品質のエクスペリエンス (QoE) の設定を削除する方法を説明します。'
ms.openlocfilehash: 52008e14ca7a7b2a7a26726a2749f6d4dd083bbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="0fa33-103">Skype for Business Server 2015 での QoE (Quality of Experience) 構成設定の削除</span><span class="sxs-lookup"><span data-stu-id="0fa33-103">Delete Quality of Experience configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0fa33-104">**の概要:**ビジネス サーバー 2015 の Skype の高品質のエクスペリエンス (QoE) の設定を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0fa33-p101">Quality of Experience (QoE) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="0fa33-107">ビジネス サーバー 2015 年、1 つの Skype をインストールすると QoE 構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-107">When you install Skype for Business Server 2015, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="0fa33-108">また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0fa33-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="0fa33-109">設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="0fa33-110">サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="0fa33-111">削除することも""グローバル設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0fa33-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="0fa33-112">ただし、グローバル設定は実際に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0fa33-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="0fa33-113">代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="0fa33-114">たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0fa33-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="0fa33-115">仮にグローバル コレクションを変更して削除を無効にしたとします。</span><span class="sxs-lookup"><span data-stu-id="0fa33-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="0fa33-116">後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="0fa33-117">この場合、削除が再び有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="0fa33-118">ビジネス サーバーのコントロール パネルの Skype を使用して、または[削除 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)コマンドレットを使用して、QoE 構成設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="0fa33-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0fa33-119">ビジネス サーバーのコントロール パネルの Skype を使用して、QoE 構成設定を削除するのには</span><span class="sxs-lookup"><span data-stu-id="0fa33-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0fa33-120">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0fa33-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0fa33-121">詳細については、**セットアップのアクセス許可の委任**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fa33-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0fa33-122">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0fa33-123">左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fa33-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="0fa33-124">[**QoE データ**] ページで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fa33-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="0fa33-125">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fa33-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0fa33-126">Windows PowerShell コマンドレットを使用して、QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0fa33-127">QoE 構成設定を削除するには、Windows PowerShell と**削除 CsQoEConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="0fa33-128">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="0fa33-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0fa33-129">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fa33-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0fa33-130">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="0fa33-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="0fa33-131">指定した QoE 構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="0fa33-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="0fa33-132">このコマンドは、Redmond サイトに適用された QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="0fa33-133">サイト スコープに適用されたすべての QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="0fa33-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="0fa33-134">このコマンドは、サイト スコープに適用されたすべての QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="0fa33-135">QoE 監視が無効にされたすべての QoE 構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="0fa33-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="0fa33-136">このコマンドは、QoE 監視が無効にされたすべての QoE 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="0fa33-137">詳細については、[削除 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fa33-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0fa33-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fa33-138">See also</span></span>

[<span data-ttu-id="0fa33-139">ビジネス サーバー 2015 の通話の詳細記録と Skype で高品質なエクスペリエンスのデータベースを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="0fa33-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)


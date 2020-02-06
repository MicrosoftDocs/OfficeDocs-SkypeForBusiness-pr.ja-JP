---
title: Skype for Business Server で CDR データの保持を指定する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '概要: Skype for Business Server の通話の詳細記録 (CDR) データを管理する方法について説明します。'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817676"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="9a47f-103">Skype for Business Server で CDR データの保持を指定する</span><span class="sxs-lookup"><span data-stu-id="9a47f-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="9a47f-104">**概要:** Skype for Business Server の通話の詳細記録 (CDR) データを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a47f-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="9a47f-p101">既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。</span><span class="sxs-lookup"><span data-stu-id="9a47f-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a47f-p102">CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。</span><span class="sxs-lookup"><span data-stu-id="9a47f-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="9a47f-111">CDR データの削除設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a47f-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="9a47f-112">CDR データの保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="9a47f-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="9a47f-113">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="9a47f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="9a47f-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a47f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9a47f-115">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a47f-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="9a47f-116">[**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a47f-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="9a47f-117">削除を有効にするには、[**CDR の削除を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a47f-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="9a47f-118">[**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a47f-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="9a47f-119">[**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a47f-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="9a47f-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a47f-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a47f-121">Windows PowerShell コマンドレットを使用して CDR の保持期間を指定する</span><span class="sxs-lookup"><span data-stu-id="9a47f-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9a47f-122">CDR retention の設定は、Windows PowerShell と CsCdrConfiguration コマンドレットを使って作成できます。</span><span class="sxs-lookup"><span data-stu-id="9a47f-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="9a47f-123">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="9a47f-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a47f-124">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a47f-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9a47f-125">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="9a47f-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="9a47f-126">特定の場所の CDR の保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="9a47f-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="9a47f-127">このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="9a47f-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="9a47f-128">複数の場所の CDR の保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="9a47f-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="9a47f-129">このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持期間が構成されます。</span><span class="sxs-lookup"><span data-stu-id="9a47f-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="9a47f-130">詳細については、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a47f-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a47f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a47f-131">See also</span></span>

[<span data-ttu-id="9a47f-132">Skype for Business Server での通話の詳細記録 (CDR)</span><span class="sxs-lookup"><span data-stu-id="9a47f-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)

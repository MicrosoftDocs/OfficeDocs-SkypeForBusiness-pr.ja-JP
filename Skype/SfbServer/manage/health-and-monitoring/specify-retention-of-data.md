---
title: ビジネス サーバー用の Skype での CDR のデータ保存期間を指定します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 概要では、Skype のビジネス サーバー (CDR) データを記録する呼び出しの詳細を管理する方法について説明します。
ms.openlocfilehash: 72fbb679a260462086930fc0457b5c748447cc29
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197689"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="a5a97-103">ビジネス サーバー用の Skype での CDR のデータ保存期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="a5a97-104">**の概要:** Skype のビジネス サーバー (CDR) データを記録する呼び出しの詳細を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="a5a97-p101">既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。</span><span class="sxs-lookup"><span data-stu-id="a5a97-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5a97-p102">CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。</span><span class="sxs-lookup"><span data-stu-id="a5a97-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="a5a97-111">CDR データの削除設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="a5a97-112">CDR データの保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="a5a97-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="a5a97-113">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="a5a97-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a5a97-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a5a97-115">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5a97-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="a5a97-116">[**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5a97-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="a5a97-117">削除を有効にするには、[**CDR の削除を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="a5a97-118">[**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="a5a97-119">[**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="a5a97-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5a97-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5a97-121">Windows PowerShell コマンドレットを使用して、CDR の保存期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5a97-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a5a97-122">CDR 保存期間の設定は、Windows PowerShell とセット CsCdrConfiguration コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="a5a97-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="a5a97-123">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="a5a97-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5a97-124">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5a97-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a5a97-125">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="a5a97-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="a5a97-126">特定の場所の CDR の保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="a5a97-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="a5a97-127">このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="a5a97-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="a5a97-128">複数の場所の CDR の保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="a5a97-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="a5a97-129">このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持期間が構成されます。</span><span class="sxs-lookup"><span data-stu-id="a5a97-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="a5a97-130">詳細については、[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5a97-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5a97-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5a97-131">See also</span></span>

[<span data-ttu-id="a5a97-132">Skype のビジネス サーバー (CDR) を記録する詳細を呼び出す</span><span class="sxs-lookup"><span data-stu-id="a5a97-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)

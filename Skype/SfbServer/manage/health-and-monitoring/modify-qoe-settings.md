---
title: ビジネス サーバーの Skype の高品質のエクスペリエンスの設定を変更します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 概要では、Skype のビジネス サーバーの QoE データの保存期間を指定する方法について説明します。
ms.openlocfilehash: 4a2197d3d66a5b871682ba187bf607480f2da175
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887457"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="a21ed-103">ビジネス サーバーの Skype の高品質のエクスペリエンスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="a21ed-104">**の概要:** Skype のビジネス サーバーの QoE データの保存期間を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="a21ed-p101">既定では、QoE (Quality of Experience) データは 60 日後に削除されます。[**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。</span><span class="sxs-lookup"><span data-stu-id="a21ed-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="a21ed-p102">通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。</span><span class="sxs-lookup"><span data-stu-id="a21ed-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="a21ed-111">次の手順では、QoE データの削除設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a21ed-112">ビジネス サーバーのコントロール パネルの Skype を使用して、QoE データの保存期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="a21ed-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a21ed-p103">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21ed-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="a21ed-115">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a21ed-116">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21ed-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="a21ed-117">[**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21ed-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="a21ed-118">削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="a21ed-119">[**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="a21ed-120">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21ed-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a21ed-121">Windows PowerShell コマンドレットを使用して、QoE の保存期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21ed-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a21ed-122">QoE の保存期間の設定は、Windows PowerShell と**セット CsQoEConfiguration**コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="a21ed-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="a21ed-123">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="a21ed-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a21ed-124">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21ed-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a21ed-125">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="a21ed-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="a21ed-126">特定の場所で QoE の保持を指定するには</span><span class="sxs-lookup"><span data-stu-id="a21ed-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="a21ed-127">このコマンドを実行すると、レドモンド サイトでの QoE データの削除が有効になり、QoE データを 20 日間保持するようにサイトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="a21ed-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="a21ed-128">複数の場所で QoE の保持を指定するには</span><span class="sxs-lookup"><span data-stu-id="a21ed-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="a21ed-129">このコマンドを実行すると、組織で使用されているすべての QoE 構成設定で QoE の保持が構成されます。</span><span class="sxs-lookup"><span data-stu-id="a21ed-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="a21ed-130">詳細については、[セット CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21ed-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a21ed-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a21ed-131">See also</span></span>

[<span data-ttu-id="a21ed-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="a21ed-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

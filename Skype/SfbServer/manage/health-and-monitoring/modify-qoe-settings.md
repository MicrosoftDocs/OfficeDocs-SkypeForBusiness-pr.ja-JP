---
title: Skype for Business Server でエクスペリエンス設定の品質を変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '概要: Skype for Business Server で QoE データの保持を指定する方法について説明します。'
ms.openlocfilehash: c597c0e5e3fbd2a8a92304ffd55d866a15c121a9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992042"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="5bf89-103">Skype for Business Server でエクスペリエンス設定の品質を変更する</span><span class="sxs-lookup"><span data-stu-id="5bf89-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="5bf89-104">**概要:** Skype for Business Server で QoE データの保持を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bf89-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="5bf89-p101">既定では、QoE (Quality of Experience) データは 60 日後に削除されます。[**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。</span><span class="sxs-lookup"><span data-stu-id="5bf89-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="5bf89-p102">通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。</span><span class="sxs-lookup"><span data-stu-id="5bf89-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="5bf89-111">次の手順では、QoE データの削除設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bf89-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5bf89-112">Skype for Business Server コントロールパネルを使用して QoE データの保持を指定するには</span><span class="sxs-lookup"><span data-stu-id="5bf89-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5bf89-p103">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bf89-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="5bf89-115">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5bf89-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5bf89-116">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf89-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="5bf89-117">[**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf89-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="5bf89-118">削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf89-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="5bf89-119">[**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf89-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="5bf89-120">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf89-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5bf89-121">Windows PowerShell コマンドレットを使用した QoE 保持の指定</span><span class="sxs-lookup"><span data-stu-id="5bf89-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5bf89-122">QoE 保持設定を作成するには、Windows PowerShell と**Set-CsQoEConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5bf89-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="5bf89-123">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="5bf89-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5bf89-124">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bf89-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5bf89-125">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="5bf89-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="5bf89-126">特定の場所で QoE の保持を指定するには</span><span class="sxs-lookup"><span data-stu-id="5bf89-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="5bf89-127">このコマンドを実行すると、レドモンド サイトでの QoE データの削除が有効になり、QoE データを 20 日間保持するようにサイトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="5bf89-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="5bf89-128">複数の場所で QoE の保持を指定するには</span><span class="sxs-lookup"><span data-stu-id="5bf89-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="5bf89-129">このコマンドを実行すると、組織で使用されているすべての QoE 構成設定で QoE の保持が構成されます。</span><span class="sxs-lookup"><span data-stu-id="5bf89-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="5bf89-130">詳細については、「 [Set-CsQoEConfiguration 設定](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bf89-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bf89-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bf89-131">See also</span></span>

[<span data-ttu-id="5bf89-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="5bf89-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

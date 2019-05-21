---
title: Skype for Business Server のエクスペリエンスの品質を有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '概要: Skype for Business Server の Quality of Experience (QoE) を有効にする方法について説明します。'
ms.openlocfilehash: 90110c5664e80ac1d4f9d382c20e0fd58d9ce134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305711"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="18b4c-103">Skype for Business Server のエクスペリエンスの品質を有効にする</span><span class="sxs-lookup"><span data-stu-id="18b4c-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="18b4c-104">**概要:** Skype For business Server の Quality of Experience (qoe) を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18b4c-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="18b4c-p101">QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。詳細については、「計画」のドキュメントの「[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4c-p101">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions. For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="18b4c-107">組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="18b4c-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="18b4c-p102">QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。詳細については、「[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4c-p102">To enable QoE, you must first configure monitoring and a monitoring back-end database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="18b4c-110">Skype for Business Server コントロールパネルを使用して QoE を有効にするには</span><span class="sxs-lookup"><span data-stu-id="18b4c-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="18b4c-111">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="18b4c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="18b4c-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="18b4c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="18b4c-113">左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18b4c-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="18b4c-114">[**QoE データ**] ページで、表から該当するコレクションをクリックして、[**アクション**]、[**QoE を有効にする**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="18b4c-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="18b4c-115">Windows PowerShell コマンドレットを使用して QoE を有効にする</span><span class="sxs-lookup"><span data-stu-id="18b4c-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="18b4c-116">QoE を有効にするには、Windows PowerShell と**Set-CsQoEConfiguration**指定コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18b4c-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="18b4c-117">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="18b4c-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="18b4c-118">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4c-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="18b4c-119">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="18b4c-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="18b4c-120">1 つの場所に対して QoE を有効にするには</span><span class="sxs-lookup"><span data-stu-id="18b4c-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="18b4c-121">QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="18b4c-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="18b4c-122">1 つの場所に対して QoE を無効にするには</span><span class="sxs-lookup"><span data-stu-id="18b4c-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="18b4c-p104">QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。</span><span class="sxs-lookup"><span data-stu-id="18b4c-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="18b4c-126">複数の場所の QoE を 1 つのコマンドで有効にするには</span><span class="sxs-lookup"><span data-stu-id="18b4c-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="18b4c-127">このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="18b4c-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="18b4c-128">詳細については、「 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4c-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="18b4c-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="18b4c-129">See also</span></span>

[<span data-ttu-id="18b4c-130">モニタリングの計画</span><span class="sxs-lookup"><span data-stu-id="18b4c-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="18b4c-131">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="18b4c-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)


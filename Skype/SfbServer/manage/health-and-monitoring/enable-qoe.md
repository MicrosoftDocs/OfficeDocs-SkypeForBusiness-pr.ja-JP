---
title: Skype for Business Server でエクスペリエンスの品質を有効にする
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '概要: Skype for Business Server で QoE (Quality of Experience) を有効にする方法について学習します。'
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095211"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="a71aa-103">Skype for Business Server でエクスペリエンスの品質を有効にする</span><span class="sxs-lookup"><span data-stu-id="a71aa-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="a71aa-104">**概要:** Skype for Business Server で QoE (Quality of Experience) を有効にする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="a71aa-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="a71aa-105">QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。</span><span class="sxs-lookup"><span data-stu-id="a71aa-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="a71aa-106">詳細については、「計画」のドキュメントの「[Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a71aa-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="a71aa-107">組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a71aa-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="a71aa-108">QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71aa-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="a71aa-109">詳細については、「[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a71aa-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a71aa-110">Skype for Business Server コントロール パネルを使用して QoE を有効にするには</span><span class="sxs-lookup"><span data-stu-id="a71aa-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a71aa-111">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a71aa-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="a71aa-112">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a71aa-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a71aa-113">左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a71aa-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="a71aa-114">[**QoE データ**] ページで、表から該当するコレクションをクリックして、[**操作**]、[**QoE を有効にする**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a71aa-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a71aa-115">コマンドレットを使用して QoE をWindows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="a71aa-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a71aa-116">QoE を有効にするには、Windows PowerShell **Set-CsQoEConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="a71aa-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="a71aa-117">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a71aa-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a71aa-118">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a71aa-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a71aa-119">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="a71aa-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="a71aa-120">1 つの場所に対して QoE を有効にするには</span><span class="sxs-lookup"><span data-stu-id="a71aa-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="a71aa-121">QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a71aa-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="a71aa-122">1 つの場所に対して QoE を無効にするには</span><span class="sxs-lookup"><span data-stu-id="a71aa-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="a71aa-p104">QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。</span><span class="sxs-lookup"><span data-stu-id="a71aa-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="a71aa-126">複数の場所の QoE を 1 つのコマンドで有効にするには</span><span class="sxs-lookup"><span data-stu-id="a71aa-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="a71aa-127">このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a71aa-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="a71aa-128">詳細については [、「Set-CsQoEConfiguration」を参照してください](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a71aa-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="a71aa-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a71aa-129">See also</span></span>

[<span data-ttu-id="a71aa-130">監視の計画</span><span class="sxs-lookup"><span data-stu-id="a71aa-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="a71aa-131">監視の展開</span><span class="sxs-lookup"><span data-stu-id="a71aa-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)
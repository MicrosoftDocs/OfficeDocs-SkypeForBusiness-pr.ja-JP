---
title: ビジネス サーバーの Skype での通話の詳細記録を有効にします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: '概要: は、Skype のビジネス サーバー (CDR) のレコードを記録呼び出しの詳細を有効にする方法を説明します。'
ms.openlocfilehash: 8ba053c95dcb9e43b6951671853d2c064ad5542f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199715"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="d021e-103">ビジネス サーバーの Skype での通話の詳細記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d021e-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="d021e-104">**の概要:** Skype のビジネス サーバー (CDR) のレコードを記録呼び出しの詳細を有効にする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d021e-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="d021e-p101">通話詳細記録 (CDR) は、インスタント メッセージング、ボイス オーバー IP (VoIP) 通話、アプリケーション共有、ファイル送信などのピアツーピア アクティビティ、および会議に関する使用状況および診断情報を記録します。使用状況データは投資収益率 (ROI) の計算に、診断データはピアツーピア アクティビティおよび会議のトラブルシューティングに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d021e-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="d021e-107">組織全体または組織内の各サイトで CDR を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d021e-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d021e-p102">CDR を有効にするには、監視および監視データベースを構成する必要があります。詳細については、「[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d021e-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="d021e-110">ビジネス サーバーのコントロール パネルの Skype で CDR を有効にするには</span><span class="sxs-lookup"><span data-stu-id="d021e-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d021e-111">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="d021e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="d021e-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d021e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d021e-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d021e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="d021e-114">[**通話詳細記録**] ページで、表から該当するサイトをクリックして、[**アクション**] をクリックし、[**CDR の有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d021e-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d021e-115">CDR は、既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d021e-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d021e-116">Windows PowerShell コマンドレットを使用して、CDR を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d021e-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d021e-117">CDR を有効にするには、Windows PowerShell と**セット CsCdrConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d021e-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d021e-118">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="d021e-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d021e-119">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d021e-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d021e-120">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="d021e-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="d021e-121">1 つの場所の CDR を有効にするには</span><span class="sxs-lookup"><span data-stu-id="d021e-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="d021e-122">CDR を無効にするには、EnableCDR パラメーターを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d021e-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="d021e-123">1 つの場所の CDR を無効にするには</span><span class="sxs-lookup"><span data-stu-id="d021e-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="d021e-p104">CDR を無効にするには、EnableCDR パラメーターを False ($False) に設定します。CDR を無効にしても、監視がアンインストールされることはありません。CDR データの収集と保存が一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="d021e-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="d021e-127">1 つのコマンドで複数の場所にある CDR を有効にするには</span><span class="sxs-lookup"><span data-stu-id="d021e-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="d021e-128">このコマンドによって、組織で現在使用されているすべての CDR 構成設定の CDR が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d021e-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="d021e-129">詳細については、[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d021e-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d021e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="d021e-130">See also</span></span>

[<span data-ttu-id="d021e-131">監視の計画</span><span class="sxs-lookup"><span data-stu-id="d021e-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="d021e-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="d021e-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

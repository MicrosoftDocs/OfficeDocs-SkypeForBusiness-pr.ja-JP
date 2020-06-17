---
title: コール パーク アプリケーション設定の移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: コールパークアプリケーションの移行には、Skype for Business Server 2019 プールを、従来のインストールでアップロードされたカスタム音楽保留ファイルと共にプロビジョニングすること、およびサービスレベル設定を復元して、Skype for Business Server 2019 プールへのすべてのコールパークオービットを retargeting することが含まれます。 カスタマイズした保留音のファイルがプールに構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。 また、コールパーク用にアップロードされたカスタマイズされた保留音ファイルのバックアップコピーを別に保持するために、コールパークのカスタマイズされた保留音のファイルを別の場所にバックアップすることをお勧めします。 コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。 オーディオファイルをプールファイルストアから Skype for Business Server 2019 ファイルストアにコピーするには、Xcopy コマンドを次のパラメーターと共に使用します。
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752819"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="2444a-107">コール パーク アプリケーション設定の移行</span><span class="sxs-lookup"><span data-stu-id="2444a-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="2444a-108">コールパークアプリケーションの移行には、Skype for Business Server 2019 プールを、従来のインストールにアップロードされた任意のカスタムの保留中ファイルと共にプロビジョニングすること、サービスレベルの設定を復元すること、およびすべてのコールパークオービットを Skype for Business Server 2019 プールに再作成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2444a-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2444a-109">カスタマイズした保留音のファイルがプールに構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2444a-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2444a-110">また、コールパーク用にアップロードされたカスタマイズされた保留音ファイルのバックアップコピーを別に保存するために、コールパークのカスタマイズされた保留音ファイルをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2444a-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="2444a-111">コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。</span><span class="sxs-lookup"><span data-stu-id="2444a-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="2444a-112">オーディオファイルをプールファイルストアから Skype for Business Server 2019 ファイルストアにコピーするには、 **Xcopy**コマンドを次のパラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="2444a-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="2444a-113">カスタマイズしたすべてのオーディオファイルが Skype for business Server 2019 ファイルストアにコピーされている場合、Skype for Business Server 2019 プールのコールパークアプリケーション設定を構成する必要があります。また、従来のプールに関連付けられているコールパークオービット範囲は、Skype for Business Server の2019プールに再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2444a-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="2444a-114">コールパークアプリケーションの設定には、ピックアップタイムアウトのしきい値、保留音の保留を有効または無効にするか、最大通話ピックアップ試行回数、およびタイムアウト要求が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2444a-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="2444a-115">**New-cscpsconfiguration**コマンドレットを実行するには、Skype For Business Server 管理シェルを使用してコールパークアプリケーションの設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2444a-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="2444a-116">Skype for Business Server コントロールパネルを使用してコールパークアプリケーションの設定を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="2444a-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="2444a-117">Call Park Service の設定を再構成する</span><span class="sxs-lookup"><span data-stu-id="2444a-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="2444a-118">Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2444a-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="2444a-119">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2444a-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="2444a-120">Skype for Business Server 2019 コールパークアプリケーションの設定が従来の設定と同じ場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="2444a-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="2444a-121">コールパークアプリケーションの設定が Skype for Business Server 2019 と従来の環境で異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。</span><span class="sxs-lookup"><span data-stu-id="2444a-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="2444a-122">すべてのコールパークオービット範囲を従来のプールから Skype for Business Server 2019 プールに再割り当てするには、Skype for Business Server コントロールパネルまたは Skype for business Server 管理シェルのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2444a-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2444a-123">Skype for Business Server コントロールパネルを使用してすべてのコールパークオービット範囲を再割り当てする</span><span class="sxs-lookup"><span data-stu-id="2444a-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2444a-124">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2444a-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="2444a-125">左側のウィンドウで、[**音声機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2444a-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="2444a-126">[**コール パーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2444a-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="2444a-127">従来のプールに割り当てられているコールパークオービット範囲のそれぞれについて、[**宛先サーバーの FQDN** ] 設定を編集し、コールパーク要求を処理する Skype For business server 2019 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2444a-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="2444a-128">[**コミット**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="2444a-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2444a-129">Skype for Business Server 管理シェルを使用してすべてのコールパークオービット範囲を再割り当てする</span><span class="sxs-lookup"><span data-stu-id="2444a-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="2444a-130">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2444a-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="2444a-131">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2444a-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="2444a-132">このコマンドレットを実行すると、展開内のコール パーク オービットの範囲がすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="2444a-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="2444a-133">**CallParkServiceId**および**Callparkserverfqdn**パラメーターが従来のプールとして設定されているすべてのコールパークオービットを再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2444a-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="2444a-134">従来のコールパークオービット範囲を Skype for Business Server 2019 プールに再割り当てするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2444a-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="2444a-135">すべてのコールパークオービット範囲を Skype for Business Server 2019 プールに再割り当てした後、コールパークアプリケーションの移行プロセスが完了し、Skype for Business Server 2019 プールが、今後のコールパーク要求をすべて処理するようになります。</span><span class="sxs-lookup"><span data-stu-id="2444a-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>



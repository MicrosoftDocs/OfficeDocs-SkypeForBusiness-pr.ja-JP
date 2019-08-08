---
title: コール パーク アプリケーション設定の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: コールパークアプリケーションの移行には、Skype for Business Server 2019 プールのプロビジョニングが含まれています。このファイルには、従来のインストールでアップロードされたカスタム音楽が含まれています。また、サービスレベル設定を復元して、orbits の retargetingSkype for Business Server 2019 プール。 カスタマイズした音楽の保留中のファイルがプールで構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。 さらに、コールパーク用にアップロードされた、カスタマイズされた音楽の保存ファイルを別の場所にバックアップしておくことをお勧めします。これは、コールパーク用にアップロードされたカスタマイズされた音楽の保存ファイルの個別のバックアップコピーを保持するためです。 コールパークアプリケーション用にカスタマイズされた音楽保留のファイルは、プールのファイルストアに保存されます。 プールファイルストアから Skype for Business Server 2019 ファイルストアにオーディオファイルをコピーするには、次のパラメーターを使用して Xcopy コマンドを使用します。
ms.openlocfilehash: efb2bfbf8ac62ad05e2ee560c2aca4fb7b496006
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238033"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="6d391-107">コール パーク アプリケーション設定の移行</span><span class="sxs-lookup"><span data-stu-id="6d391-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="6d391-108">コールパークアプリケーションの移行には、Skype for Business Server 2019 プールのプロビジョニングが含まれます。このファイルには、従来のインストールでアップロードされたカスタムの音楽の保存ファイルが含まれています。サービスレベルの設定を復元して、すべてのコールパーク orbits を再ターゲット化します。Skype for Business Server 2019 プール。</span><span class="sxs-lookup"><span data-stu-id="6d391-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6d391-109">カスタマイズした音楽の保留中のファイルがプールで構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d391-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6d391-110">さらに、通話パークをカスタマイズして、コールパーク用にアップロードされたカスタマイズされた音楽の保存ファイルを別の場所に保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d391-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="6d391-111">コールパークアプリケーション用にカスタマイズされた音楽保留のファイルは、プールのファイルストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6d391-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="6d391-112">プールファイルストアから Skype for Business Server 2019 ファイルストアにオーディオファイルをコピーするには、次のパラメーターを使用して**Xcopy**コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d391-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="6d391-113">カスタマイズされたすべてのオーディオファイルが Skype for Business Server 2019 ファイルストアにコピーされると、Skype for Business Server 2019 プールのコールパークアプリケーションの設定が構成され、従来のプールと関連付けられている範囲がコールパークで呼び出されます。Skype for Business Server 2019 プールに再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d391-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="6d391-114">コールパークアプリケーションの設定には、ピックアップタイムアウトしきい値、保留中の音楽を有効または無効にする、最大通話ピックアップ試行回数、タイムアウト要求が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d391-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="6d391-115">**CsCpsConfiguration**コマンドレットを実行するには、Skype For Business Server 管理シェルを使用して、コールパークアプリケーションの設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d391-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="6d391-116">Skype for Business Server コントロールパネルを使用して、コールパークアプリケーションの設定を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d391-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="6d391-117">コールパークサービス設定を再構成する</span><span class="sxs-lookup"><span data-stu-id="6d391-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="6d391-118">Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d391-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="6d391-119">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d391-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d391-120">Skype for Business Server 2019 Call パークのアプリケーション設定が従来の設定と同じである場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="6d391-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="6d391-121">コールパークアプリケーションの設定が Skype for Business Server 2019 と従来の環境で異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。</span><span class="sxs-lookup"><span data-stu-id="6d391-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="6d391-122">すべてのコールパークを、従来のプールから Skype for Business Server 2019 プールに再割り当てするには、Skype for Business Server コントロールパネルまたは Skype for Business Server の管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d391-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6d391-123">Skype for Business Server コントロールパネルを使用してすべてのコールパークの範囲を再割り当てする</span><span class="sxs-lookup"><span data-stu-id="6d391-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6d391-124">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d391-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6d391-125">左側のウィンドウで、[**音声機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d391-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="6d391-126">[ **Call パーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d391-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="6d391-127">従来のプールに割り当てられている各通話パークの範囲は、[**宛先サーバーの FQDN** ] の設定を編集し、コールパーク要求を処理する Skype For business server 2019 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d391-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="6d391-128">[**コミット**] を選んで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="6d391-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6d391-129">Skype for Business Server 管理シェルを使用してすべてのコールパーク範囲を再割り当てする</span><span class="sxs-lookup"><span data-stu-id="6d391-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6d391-130">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d391-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="6d391-131">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d391-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="6d391-132">このコマンドレットは、展開内のすべてのコールパーク範囲の範囲を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6d391-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="6d391-133">**CallParkServiceId**と**Callparkserverfqdn**パラメーターが設定されているすべての Call パーク orbits は、再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d391-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="6d391-134">従来のコールパークの範囲を Skype for Business Server 2019 プールに再割り当てするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d391-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="6d391-135">すべてのコールパークの範囲を Skype for Business Server 2019 プールに再割り当てした後、コールパークアプリケーションの移行プロセスが完了し、Skype for Business Server 2019 プールは、今後のすべてのコールパーク要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="6d391-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>



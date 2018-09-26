---
title: コール パーク アプリケーションの設定を移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のインストールにアップロードされている保留中のファイルに、カスタムの音楽でのプールのビジネス サーバー 2019 Skype を提供するアプリケーションが含まれているパークの移行、サービス レベルの設定を復元して、すべてのコール パークの再ターゲット周囲を回りながらに、ビジネス サーバー 2019 プールの Skype です。 カスタマイズされた音楽-保留中のファイルは、プール内に構成されている場合、これらのファイルはビジネス サーバー 2019 プールの新しい Skype にコピーする必要があります。 さらに、音楽の保留中のファイルからのカスタマイズされた音楽-保留中のファイルのアップロードされたコール パークの独立したバックアップ ・ コピーを保持する別の出力先をカスタマイズ、コール パークをバックアップすることをお勧めします。 プールのファイル ストアには、コール パーク アプリケーションのカスタマイズされた音楽-保留中のファイルが格納されています。 プールのファイル ストアから、Skype ビジネス サーバー 2019 ファイル ストア用にオーディオ ファイルをコピーするには、次のパラメーターで Xcopy コマンドを使用します。
ms.openlocfilehash: a91c23f06d22d822567bd39ec9f18eb7289e201d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028825"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="01315-107">コール パーク アプリケーションの設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="01315-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="01315-108">コール パーク アプリケーションの移行は、従来のインストール、サービス ・ レベルの設定を復元して、すべてのコール パーク軌道を再ターゲットにアップロードされているカスタムの音楽の保留中のファイルでのビジネス サーバー 2019 プールの Skype の準備ビジネス サーバー 2019 プールの Skype です。</span><span class="sxs-lookup"><span data-stu-id="01315-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="01315-109">カスタマイズされた音楽-保留中のファイルは、プール内に構成されている場合、これらのファイルはビジネス サーバー 2019 プールの新しい Skype にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01315-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="01315-110">さらに、カスタマイズされた音楽-保留中のファイルのアップロードされたコール パークの独立したバックアップ ・ コピーを保持する別の出力先に保留中の音楽ファイルをカスタマイズ、コール パークをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01315-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="01315-111">プールのファイル ストアには、コール パーク アプリケーションのカスタマイズされた音楽-保留中のファイルが格納されています。</span><span class="sxs-lookup"><span data-stu-id="01315-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="01315-112">プールのファイル ストアから、Skype ビジネス サーバー 2019 ファイル ストア用にオーディオ ファイルをコピーするには、次のパラメーターで**Xcopy**コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="01315-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 
  
```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="01315-113">ビジネス サーバー 2019 ファイル ストアの Skype をカスタマイズしたすべてのオーディオ ファイルがコピーされたら、コール パーク アプリケーション設定、Skype のビジネス サーバー 2019 のプールを構成する必要があり、コール パーク オービット範囲が従来のプールに関連付けられています。ビジネス サーバー 2019 プールの Skype を再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01315-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>
  
<span data-ttu-id="01315-114">コール パーク アプリケーションの設定には、有効化または保留、ピックアップ呼び出しの最大試行回数、およびタイムアウトの要求上の音楽を無効にすると、ピックアップのタイムアウトのしきい値にはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="01315-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="01315-115">**セット CsCpsConfiguration**コマンドレットを実行するビジネス サーバー管理シェルの Skype を使用して、コール パーク アプリケーションの設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01315-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="01315-116">ビジネス サーバーのコントロール パネルの Skype を使用してコール パーク アプリケーションの設定を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="01315-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 
  
## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="01315-117">コール パーク サービスの設定を再構成します。</span><span class="sxs-lookup"><span data-stu-id="01315-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="01315-118">ビジネス 2019 フロント エンド サーバーの Skype、Skype ビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="01315-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="01315-119">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="01315-119">At the command line, type the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="01315-120">ビジネス サーバー 2019 コール パーク アプリケーションの設定は、Skype が従来の設定と同じ場合は、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="01315-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="01315-121">コール パーク アプリケーションの設定が異なる場合、Skype ビジネス サーバー 2019 および従来の環境のため、これらの変更を更新するテンプレートとして次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01315-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 
  
  ```
  Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
  
  ```

<span data-ttu-id="01315-122">ビジネス サーバー 2019 プールの Skype に従来のプールからのすべてのコール パーク ・軌道の範囲を割り当て直すには、ビジネスのサーバー管理シェルのビジネス サーバーのコントロール パネルの Skype または、Skype のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01315-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 
  
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="01315-123">ビジネス サーバーのコントロール パネルの Skype を使用するすべてのコール パーク軌道範囲を再割り当てください。</span><span class="sxs-lookup"><span data-stu-id="01315-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="01315-124">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="01315-124">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="01315-125">左側のウィンドウでは、**音声機能**を選択します。</span><span class="sxs-lookup"><span data-stu-id="01315-125">In the left pane, select **Voice Features**.</span></span>
    
3. <span data-ttu-id="01315-126">[**コール パーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="01315-126">Select the **Call Park** tab.</span></span> 
    
4. <span data-ttu-id="01315-127">レガシ プールに割り当てられている各コール パーク軌道範囲では、**宛先サーバーの FQDN**設定を編集する、コール パークの要求を処理するビジネス サーバー 2019 プールの Skype を選択してください。</span><span class="sxs-lookup"><span data-stu-id="01315-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 
    
5. <span data-ttu-id="01315-128">**コミット**変更を保存するを選択します。</span><span class="sxs-lookup"><span data-stu-id="01315-128">Select **Commit** to save the changes.</span></span> 
    
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="01315-129">ビジネス サーバー管理シェルの Skype を使用するすべてのコール パーク軌道範囲を再割り当てください。</span><span class="sxs-lookup"><span data-stu-id="01315-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="01315-130">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="01315-130">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="01315-131">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="01315-131">At the command line, type the following:</span></span>
    
  ```
  Get-CsCallParkOrbit
  ```

    <span data-ttu-id="01315-132">このコマンドレットには、すべての展開でコール パークの移動範囲が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="01315-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="01315-133">レガシ プールとして設定する**CallParkServiceId**と**CallParkServerFqdn**のパラメーターを持つすべてのコール パーク軌道を再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01315-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 
    
    <span data-ttu-id="01315-134">従来のパークの回り込みを再割り当てするには、ビジネス サーバー 2019 プールには、コマンド行に、Skype の範囲は次のとおり入力します。</span><span class="sxs-lookup"><span data-stu-id="01315-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>
    
  ```
  Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
  
  ```

<span data-ttu-id="01315-135">ビジネス サーバー 2019 プールの Skype へのすべてのコール パーク軌道範囲を再割り当てすることは後、は、コール パーク アプリケーションの移行プロセスが完了して、ビジネス サーバー 2019 プールの Skype は、コール パークのすべての要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="01315-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>
  


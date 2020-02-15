---
title: Skype for Business で SEFAUtil ツールを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Skype for Business Server に SEFAUtil ツールを展開します。
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986812"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="a5dbd-103">Skype for Business で SEFAUtil ツールを展開する</span><span class="sxs-lookup"><span data-stu-id="a5dbd-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="a5dbd-104">Skype for Business Server に SEFAUtil ツールを展開します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5dbd-105">グループ通話ピックアップを展開および管理するには、Skype for Business Server バージョンの SEFAUtil ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a5dbd-106">Microsoft 統合コミュニケーション管理 API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定の任意のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="a5dbd-107">この記事は、「[統合コミュニケーションマネージ API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344)」にダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="a5dbd-108">また、次のように、ランタイムを含む UCMA 5 SDK をダウンロードすることもできます。 [ucma 5.0 sdk](https://www.microsoft.com/download/details.aspx?id=47345)。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="a5dbd-109">SEFAUtil ツールは、展開内の任意のフロントエンドプールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="a5dbd-110">SEFAUtil ツールを実行するには、信頼されたアプリケーションコンピューターで Skype for Business 展開ウィザードから手順1、2、および3を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="a5dbd-111">SEFAUtil には、ローカル構成ストアと証明書の両方が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5dbd-112">SEFAUtil の実行の詳細については、ブログ記事「[How to Get SEFAUtil running?](https://go.microsoft.com/fwlink/?LinkId=278940)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="a5dbd-113">SEFAUtil を展開するには</span><span class="sxs-lookup"><span data-stu-id="a5dbd-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="a5dbd-114">Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「**セットアップのアクセス許可の委任**」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="a5dbd-115">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a5dbd-116">SEFAUtil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="a5dbd-117">必要に応じて、SEFAUtil の実行を計画しているフロントエンドプールの信頼されたアプリケーションプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="a5dbd-118">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="a5dbd-119">[プールの FQDN]: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は、Skype for Business のフロントエンドサーバーまたはプール)。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="a5dbd-120">プールレジストラー FQDN: このアプリケーションプールに関連付けられている Skype for Business フロントエンドサーバーまたはプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="a5dbd-121">プールサイト: このプールが所属しているサイトのサイト ID。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="a5dbd-122">SEFAUtil ツールを信頼済みアプリケーションとして定義します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="a5dbd-123">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="a5dbd-124">必要に応じて、別のポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="a5dbd-125">変更したトポロジを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-125">Enable the topology with your changes.</span></span> <span data-ttu-id="a5dbd-126">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="a5dbd-127">まだお持ちでない場合は、[この場所](https://www.microsoft.com/download/details.aspx?id=52631)から Skype For business Server バージョンの SEFAUtil ツールをダウンロードして、手順3で作成した信頼されたアプリケーションプールにインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="a5dbd-128">SEFAUtil ツールが正常に実行されていることを、次のように確認します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="a5dbd-129">a. </span><span class="sxs-lookup"><span data-stu-id="a5dbd-129">a.</span></span> <span data-ttu-id="a5dbd-130">管理者特権を使用して Windows コマンドプロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="a5dbd-131">b. </span><span class="sxs-lookup"><span data-stu-id="a5dbd-131">b.</span></span> <span data-ttu-id="a5dbd-132">ユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="a5dbd-133">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="a5dbd-134">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5dbd-134">The call forwarding settings for the user will be displayed.</span></span>
    


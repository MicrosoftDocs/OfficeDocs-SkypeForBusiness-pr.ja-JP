---
title: ビジネス用の Skype で SEFAUtil ツールを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: ビジネス サーバーの Skype で SEFAUtil ツールを展開します。
ms.openlocfilehash: 1b2f981a438b71b44eb5d4c760e98d1d777f7235
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532785"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="5aa65-103">ビジネス用の Skype で SEFAUtil ツールを展開します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="5aa65-104">ビジネス サーバーの Skype で SEFAUtil ツールを展開します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="5aa65-105">展開し、コール ピックアップのグループを管理、ビジネス サーバーのバージョンの SEFAUtil ツールは、Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa65-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5aa65-106">マイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 5 のランタイムは、SEFAUtil ツールを実行しようとするすべてのコンピューターにインストールしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5aa65-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="5aa65-107">ここからダウンロード:[ユニファイド コミュニケーション マネージ API 5.0 ランタイム](https://www.microsoft.com/en-us/download/details.aspx?id=47344)です。</span><span class="sxs-lookup"><span data-stu-id="5aa65-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="5aa65-108">ここでは、ランタイムが含まれています、UCMA 5 SDK をダウンロードすることもできます: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345)です。</span><span class="sxs-lookup"><span data-stu-id="5aa65-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="5aa65-109">すべてのフロント エンド プールで SEFAUtil ツールを実行するには、展開に。</span><span class="sxs-lookup"><span data-stu-id="5aa65-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="5aa65-110">SEFAUtil ツールを実行するには、必要がありますを実行するステップ 1、2、3、Skype からビジネス展開ウィザードのアプリケーションの信頼されたコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="5aa65-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="5aa65-111">SEFAUtil は、証明書と同様に、ローカル構成ストアが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa65-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5aa65-112">SEFAUtil を実行しているの詳細については、ブログの記事を参照してください"[を実行している SEFAutil を取得する方法ですか?](https://go.microsoft.com/fwlink/?LinkId=278940)"です。</span><span class="sxs-lookup"><span data-stu-id="5aa65-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="5aa65-113">SEFAUtil を展開するには</span><span class="sxs-lookup"><span data-stu-id="5aa65-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="5aa65-114">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5aa65-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="5aa65-115">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aa65-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5aa65-116">SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="5aa65-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="5aa65-117">必要な場合は、SEFAUtil を実行しようとするフロント エンド プール用の信頼されたアプリケーション プールを定義します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="5aa65-118">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="5aa65-119">プールの FQDN: SEFAUtil アプリケーション (通常は、ビジネスのフロント エンド サーバーまたはプールの Skype) をホストするプールまたはサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5aa65-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="5aa65-120">プール FQDN をレジストラー: ビジネスのフロント エンド サーバーまたはこのアプリケーション プールに関連付けられているプールの Skype の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5aa65-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="5aa65-121">プール サイト: このプールは、ホーム サーバーをサイトのサイト ID です。</span><span class="sxs-lookup"><span data-stu-id="5aa65-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="5aa65-p105">SEFAUtil ツールを信頼済みアプリケーションとして定義します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-p105">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="5aa65-124">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5aa65-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="5aa65-p106">変更を加えたトポロジを有効にします。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-p106">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="5aa65-127">まだインストールしていない場合は、[この場所](https://www.microsoft.com/en-us/download/details.aspx?id=52631)、およびインストールの手順 3 で作成する信頼されたアプリケーション プールにから SEFAUtil ツールのビジネスのサーバーのバージョンの Skype をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5aa65-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="5aa65-128">次のように、SEFAUtil ツールが正常に実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="5aa65-129">a.</span><span class="sxs-lookup"><span data-stu-id="5aa65-129">a.</span></span> <span data-ttu-id="5aa65-130">管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="5aa65-131">b.</span><span class="sxs-lookup"><span data-stu-id="5aa65-131">b.</span></span> <span data-ttu-id="5aa65-132">ユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="5aa65-133">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5aa65-133">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="5aa65-134">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aa65-134">The call forwarding settings for the user will be displayed.</span></span>
    


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
description: Skype for Business Server で SEFAUtil ツールを展開する。
ms.openlocfilehash: ab0d41990e0c4bf9d4d2abb635ce447180899de8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767500"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="f9617-103">Skype for Business で SEFAUtil ツールを展開する</span><span class="sxs-lookup"><span data-stu-id="f9617-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="f9617-104">Skype for Business Server で SEFAUtil ツールを展開する。</span><span class="sxs-lookup"><span data-stu-id="f9617-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="f9617-105">グループ通話のピックアップを展開して管理するには、Skype for Business Server バージョンの SEFAUtil ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9617-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f9617-106">Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9617-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="f9617-107">ここからダウンロードしてください。[統合通信マネージ API 5.0 ランタイム](https://www.microsoft.com/en-us/download/details.aspx?id=47344)。</span><span class="sxs-lookup"><span data-stu-id="f9617-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="f9617-108">また、ランタイムを含む UCMA 5 SDK をダウンロードすることもできます。 [ucma 5.0 sdk](https://www.microsoft.com/en-us/download/details.aspx?id=47345)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9617-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="f9617-109">SEFAUtil ツールは、展開の任意のフロントエンドプールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9617-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="f9617-110">SEFAUtil ツールを実行するには、信頼済みアプリケーションコンピューターの Skype for Business 展開ウィザードで手順1、2、3を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9617-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="f9617-111">SEFAUtil には、ローカル構成ストアと証明書の両方が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9617-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9617-112">SEFAUtil の実行の詳細については、ブログ記事「[SEFAUtil を実行する方法](https://go.microsoft.com/fwlink/?LinkId=278940)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9617-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="f9617-113">SEFAUtil を展開するには</span><span class="sxs-lookup"><span data-stu-id="f9617-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="f9617-114">Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="f9617-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f9617-115">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9617-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f9617-116">SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9617-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="f9617-117">必要に応じて、SEFAUtil を実行する予定のフロントエンドプールの信頼されたアプリケーションプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="f9617-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="f9617-118">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9617-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="f9617-119">プールの FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は、Skype for Business のフロントエンドサーバーまたはプール)。</span><span class="sxs-lookup"><span data-stu-id="f9617-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="f9617-120">プールレジストラー FQDN: このアプリケーションプールに関連付けられている Skype for Business フロントエンドサーバーまたはプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="f9617-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="f9617-121">プールサイト: このプールが所属しているサイトのサイト ID です。</span><span class="sxs-lookup"><span data-stu-id="f9617-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="f9617-p105">SEFAUtil ツールを信頼済みアプリケーションとして定義します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9617-p105">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="f9617-124">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9617-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="f9617-p106">変更を加えたトポロジを有効にします。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9617-p106">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="f9617-127">まだインストールしていない場合は、[この場所](https://www.microsoft.com/en-us/download/details.aspx?id=52631)から Skype For business Server バージョンの SEFAUtil ツールをダウンロードして、手順3で作成した信頼されたアプリケーションプールにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9617-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="f9617-128">次のように、SEFAUtil ツールが正常に実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9617-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="f9617-129">a.</span><span class="sxs-lookup"><span data-stu-id="f9617-129">a.</span></span> <span data-ttu-id="f9617-130">管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="f9617-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="f9617-131">b.</span><span class="sxs-lookup"><span data-stu-id="f9617-131">b.</span></span> <span data-ttu-id="f9617-132">ユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="f9617-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="f9617-133">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9617-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="f9617-134">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9617-134">The call forwarding settings for the user will be displayed.</span></span>
    


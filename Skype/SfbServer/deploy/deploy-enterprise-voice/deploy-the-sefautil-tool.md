---
title: Skype for Business 2015 での SEFAUtil ツールの展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: ビジネス サーバーの Skype で SEFAUtil ツールを展開します。
ms.openlocfilehash: f0bb660218b761e513e120f4ea5786eb9278b12a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="97fe5-103">Skype for Business 2015 での SEFAUtil ツールの展開</span><span class="sxs-lookup"><span data-stu-id="97fe5-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="97fe5-104">ビジネス サーバーの Skype で SEFAUtil ツールを展開します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="97fe5-105">展開し、コール ピックアップのグループを管理、ビジネス サーバーのバージョンの SEFAUtil ツールは、Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97fe5-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="97fe5-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK を、SEFAUtil ツールを実行する予定のすべてのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97fe5-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="97fe5-107">すべてのフロント エンド プールで SEFAUtil ツールを実行するには、展開に。</span><span class="sxs-lookup"><span data-stu-id="97fe5-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97fe5-108">SEFAUtil を実行しているの詳細については、Technet のブログ記事を参照してください"[を実行している SEFAutil を取得する方法ですか?](https://go.microsoft.com/fwlink/?LinkId=278940)"です。</span><span class="sxs-lookup"><span data-stu-id="97fe5-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="97fe5-109">SEFAUtil を展開するには</span><span class="sxs-lookup"><span data-stu-id="97fe5-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="97fe5-110">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="97fe5-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="97fe5-111">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97fe5-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="97fe5-112">SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="97fe5-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="97fe5-113">必要な場合は、SEFAUtil を実行しようとするフロント エンド プール用の信頼されたアプリケーション プールを定義します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="97fe5-114">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="97fe5-p102">SEFAUtil ツールを信頼済みアプリケーションとして定義します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="97fe5-117">必要に応じて、別のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="97fe5-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="97fe5-p103">変更を加えたトポロジを有効にします。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="97fe5-120">まだインストールしていない場合は、[この場所](https://www.microsoft.com/en-us/download/details.aspx?id=52631)、およびインストールの手順 3 で作成する信頼されたアプリケーション プールにから SEFAUtil ツールのビジネスのサーバーのバージョンの Skype をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="97fe5-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="97fe5-121">次のように、SEFAUtil ツールが正常に実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="97fe5-122">a.</span><span class="sxs-lookup"><span data-stu-id="97fe5-122">a.</span></span> <span data-ttu-id="97fe5-123">管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="97fe5-124">b.</span><span class="sxs-lookup"><span data-stu-id="97fe5-124">b.</span></span> <span data-ttu-id="97fe5-125">ユーザーの着信転送設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="97fe5-126">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97fe5-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="97fe5-127">ユーザーの着信転送設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97fe5-127">The call forwarding settings for the user will be displayed.</span></span>
    


---
title: Skype for Business Server の前提条件をインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: f8ecb50525a9bb312975bf71b55a5f71c19db205
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791765"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="68439-104">Skype for Business Server の前提条件をインストールする</span><span class="sxs-lookup"><span data-stu-id="68439-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="68439-105">**概要:** Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="68439-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="68439-106">[Microsoft の評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server の無料トライアルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="68439-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="68439-107">前提条件のインストールは、トポロジの各サーバーに必要な役割と機能をインストールして、Windows Server をセットアップすることで構成されています。</span><span class="sxs-lookup"><span data-stu-id="68439-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="68439-108">要件は、トポロジでサーバーが満たす役割に基づいています。</span><span class="sxs-lookup"><span data-stu-id="68439-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="68439-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="68439-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="68439-110">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68439-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="68439-111">前提条件のインストールは、手順 1/8 です。</span><span class="sxs-lookup"><span data-stu-id="68439-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="68439-113">Windows Server をセットアップする</span><span class="sxs-lookup"><span data-stu-id="68439-113">Setup Windows Server</span></span>

<span data-ttu-id="68439-114">Skype for Business Server をインストールするには、Windows Server オペレーティングシステムといくつかの前提条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="68439-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="68439-115">前提条件の計画の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68439-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="68439-116">この手順では Windows Server 2012 R2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68439-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="68439-117">別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="68439-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="68439-118">作業を始める前に、windows Server が Windows Update を使用して最新の状態になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68439-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="68439-120">**前提条件のインストール**手順に関するビデオを見てください。</span><span class="sxs-lookup"><span data-stu-id="68439-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="68439-121">フロントエンド サーバーに必要な役割と機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="68439-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="68439-122">サーバーマネージャーを使用して、必要な役割と機能をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="68439-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="68439-123">「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」に記載されている必須ソフトウェア機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="68439-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="68439-124">必要なソフトウェアは、Skype for Business Server を実行するサーバー上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="68439-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="68439-125">既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="68439-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="68439-126">サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68439-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="68439-127">ソース ファイルは sources\sxs ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="68439-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="68439-128">たとえば、Windows Server 2012 R2 メディアがドライブ D にある場合は、パスをに`d:\sources\sxs`設定します。</span><span class="sxs-lookup"><span data-stu-id="68439-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="68439-129">Windows Update で最新の更新プログラムを入手しておいてください。</span><span class="sxs-lookup"><span data-stu-id="68439-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="68439-130">インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68439-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="68439-131">ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="68439-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="68439-132">インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="68439-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="68439-133">このサーバーで Skype for Business Server コントロールパネルを使用する場合は、Silverlight をインストールする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="68439-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="68439-134">Silverlight をインストールするには、「 [Microsoft silverlight](https://www.microsoft.com/silverlight/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68439-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="68439-135">ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="68439-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="68439-136">各サーバーの種類に必要な前提条件の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68439-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  


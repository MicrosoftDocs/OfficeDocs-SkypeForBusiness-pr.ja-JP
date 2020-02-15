---
title: Skype for Business Server の必須コンポーネントをインストールする
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
description: '概要: Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。 次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018258"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="b2a0e-104">Skype for Business Server の必須コンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="b2a0e-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="b2a0e-105">**概要:** Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="b2a0e-106">[Microsoft 評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から、無料の Skype For business Server の試用版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b2a0e-107">前提条件のインストールは、トポロジ内の各サーバーに必要な役割と機能をインストールすることによって、Windows Server をセットアップすることで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="b2a0e-108">要件は、サーバーがトポロジで満たす役割に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="b2a0e-109">手順1から5までを任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="b2a0e-110">ただし、手順6、7、および8は、図に示されているように、手順 1 ~ 5 の後で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="b2a0e-111">必須コンポーネントのインストール手順は 1 ~ 8 です。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概要図-必須コンポーネントをインストールします。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="b2a0e-113">Windows Server のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b2a0e-113">Setup Windows Server</span></span>

<span data-ttu-id="b2a0e-114">Skype for Business Server をインストールするには、Windows Server オペレーティングシステムといくつかの前提条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="b2a0e-115">前提条件の計画の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="b2a0e-116">この手順では、Windows Server 2012 R2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="b2a0e-117">異なるバージョンの Windows Server を使用している場合は、手順が若干異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b2a0e-118">作業を開始する前に、windows Update を使用して Windows Server が最新の状態になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server を最新の状態にします。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="b2a0e-120">**必須コンポーネントをインストール**するためのビデオの手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="b2a0e-121">フロントエンドサーバーに必要な役割と機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="b2a0e-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="b2a0e-122">サーバーマネージャーを使用して、必要な役割と機能をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="b2a0e-123">「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」に記載されている前提条件のソフトウェア機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="b2a0e-124">必要なソフトウェアは、Skype for Business Server を実行するサーバー上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b2a0e-125">Windows Server 2012 R2 では、既定で必要な機能のソースファイルの一部がインストールされません。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="b2a0e-126">サーバーがインターネットに接続されていない場合は、Windows Server 2012 R2 メディアを挿入して、必要な機能をインストールするために**別のソースパスを指定**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="b2a0e-127">ソースファイルは sources\sxs ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="b2a0e-128">たとえば、Windows Server 2012 R2 メディアがドライブ D にある場合は、パスをに`d:\sources\sxs`設定します。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="b2a0e-129">Windows Update から最新の更新プログラムを入手することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="b2a0e-130">インターネットに接続していない場合は、必要な更新プログラムに関連するすべての更新プログラムおよび必須コンポーネントを手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="b2a0e-131">インストールが完了したことを示すダイアログボックスが表示されたら、サーバーを再起動して処理を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="b2a0e-132">**Windows Update**を再度実行して、インストールされた役割とサービスに対する更新があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="b2a0e-133">このサーバーで Skype for Business Server コントロールパネルを使用する場合は、Silverlight もインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="b2a0e-134">Silverlight をインストールするには、「 [Microsoft silverlight](https://www.microsoft.com/silverlight/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="b2a0e-135">ディレクター、常設チャット、エッジの役割など、フロントエンドサーバー以外の役割を実行しているサーバーの前提条件には、独自の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="b2a0e-136">各サーバーの種類で必要とされる正確な前提条件の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2a0e-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  


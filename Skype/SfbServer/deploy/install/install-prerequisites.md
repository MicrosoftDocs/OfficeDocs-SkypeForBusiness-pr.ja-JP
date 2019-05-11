---
title: ビジネス サーバーの Skype のための前提条件をインストールします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: については、サーバーとサーバーの役割の業務サーバーの Skype をインストールする前に構成する必要があります。 ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 6a5b6728f65d1f541687cb55811157531c70456d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891811"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="f321c-104">ビジネス サーバーの Skype のための前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f321c-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="f321c-105">**の概要:** サーバーとサーバーのビジネスの Skype をインストールする前に構成する必要がありますサーバーの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="f321c-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="f321c-106">[マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からビジネス サーバー用には、Skype の無料試用版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f321c-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="f321c-107">必須コンポーネントのインストールは、トポロジ内のサーバーごとに必要な役割と機能をインストールすることによって Windows のサーバーを設定するので構成されます。</span><span class="sxs-lookup"><span data-stu-id="f321c-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="f321c-108">要件は、サーバーをトポロジに満たす役割に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f321c-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="f321c-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f321c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="f321c-110">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="f321c-111">8 のステップ 1 は、必須コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f321c-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="f321c-113">Windows Server をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f321c-113">Setup Windows Server</span></span>

<span data-ttu-id="f321c-114">Skype ビジネス サーバー用には、インストールする前に Windows サーバー オペレーティング システムおよび前提条件の数値が必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="f321c-115">前提条件の計画に関する詳細については、 [Skype ビジネス サーバー用のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f321c-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="f321c-116">この手順では Windows Server 2012 R2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="f321c-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="f321c-117">別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="f321c-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f321c-118">作業を開始する前に、Windows Server は、Windows Update を使用して最新の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f321c-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="f321c-120">**前提条件のインストール**手順に関するビデオを見てください。</span><span class="sxs-lookup"><span data-stu-id="f321c-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="f321c-121">フロントエンド サーバーに必要な役割と機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="f321c-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="f321c-122">必要な役割と機能はサーバー マネージャーを使用してをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="f321c-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="f321c-123">[Skype ビジネス サーバー用のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)に記載されている前提条件のソフトウェア機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f321c-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="f321c-124">Skype ビジネス サーバーを実行するサーバー上で必要なソフトウェアがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f321c-125">既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f321c-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="f321c-126">サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="f321c-127">ソース ファイルは sources\sxs ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="f321c-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="f321c-128">たとえば、Windows Server 2012 R2 のメディアがドライブ D の場合は、設定のパス`d:\sources\sxs`。</span><span class="sxs-lookup"><span data-stu-id="f321c-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="f321c-129">Windows Update で最新の更新プログラムを入手しておいてください。</span><span class="sxs-lookup"><span data-stu-id="f321c-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="f321c-130">インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="f321c-131">ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="f321c-132">インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="f321c-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="f321c-133">使用する Skype ビジネス サーバーのコントロール パネルのこのサーバーの場合、Silverlight もインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="f321c-134">Silverlight をインストールするには、 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f321c-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f321c-135">ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="f321c-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="f321c-136">サーバーの種類ごとに必要な正確な前提条件の詳細については、 [Skype ビジネス サーバー用のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f321c-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  


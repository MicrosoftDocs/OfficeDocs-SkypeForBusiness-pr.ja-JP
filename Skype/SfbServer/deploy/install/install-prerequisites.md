---
title: Skype for Business Server の前提条件のインストール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801717"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="7863b-104">Skype for Business Server の前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="7863b-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="7863b-105">**概要:** Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について確認します。</span><span class="sxs-lookup"><span data-stu-id="7863b-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="7863b-106">Microsoft Evaluation Center から Skype for Business Server の無料試用版 [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="7863b-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="7863b-107">前提条件のインストールは、トポロジ内の各サーバーに必要な役割と機能をインストールして、Windows Server をセットアップすることで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7863b-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="7863b-108">要件は、サーバーがトポロジで果たす役割に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="7863b-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="7863b-109">手順 1. ~ 5. は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="7863b-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="7863b-110">ただし、手順 6、7、および 8 は、図に示されている順序、および手順 1 ~ 5 の後に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="7863b-111">前提条件のインストールは、手順 1/8 です。</span><span class="sxs-lookup"><span data-stu-id="7863b-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概要図 - 前提条件をインストールします。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="7863b-113">Windows Server のセットアップ</span><span class="sxs-lookup"><span data-stu-id="7863b-113">Setup Windows Server</span></span>

<span data-ttu-id="7863b-114">Skype for Business Server をインストールするには、Windows Server オペレーティング システムと多くの前提条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="7863b-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="7863b-115">前提条件の計画の詳細については [、「Skype for Business Server のサーバー要件」を参照してください](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7863b-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="7863b-116">この手順では、R2 Windows Server 2012使用します。</span><span class="sxs-lookup"><span data-stu-id="7863b-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="7863b-117">別のバージョンの Windows Server を使用している場合は、手順が若干異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7863b-118">始める前に、Windows Update を使用して Windows Server が最新の情報に更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server を最新の情報に更新しました。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="7863b-120">インストールの前提条件については、ビデオ **の手順をご覧ください**。</span><span class="sxs-lookup"><span data-stu-id="7863b-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="7863b-121">フロントエンド サーバーに必要な役割と機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="7863b-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="7863b-122">サーバー マネージャーを使用して、必要な役割と機能をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7863b-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="7863b-123">Skype for Business Server のサーバー要件に記載 [されている必要なソフトウェア機能をインストールします](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7863b-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="7863b-124">必要なソフトウェアは、Skype for Business Server を実行するサーバー上に必要です。</span><span class="sxs-lookup"><span data-stu-id="7863b-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7863b-125">Windows Server 2012 R2 では、既定で必要な機能のすべてのソース ファイルがインストールされるという動作ではありません。</span><span class="sxs-lookup"><span data-stu-id="7863b-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="7863b-126">サーバーがインターネットに接続されていない場合、必要な機能をインストールするには、Windows Server 2012 R2 メディアを挿入し、[代替ソース パスの指定] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="7863b-127">ソース ファイルは sources\sxs ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="7863b-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="7863b-128">たとえば、R2 メディアWindows Server 2012ドライブ D にある場合は、パスを次の値に設定します `d:\sources\sxs` 。</span><span class="sxs-lookup"><span data-stu-id="7863b-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="7863b-129">Windows Update から最新の更新プログラムを取得することが重要です。</span><span class="sxs-lookup"><span data-stu-id="7863b-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="7863b-130">インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="7863b-131">インストールが完了したというダイアログ ボックスが表示された場合は、サーバーを再起動してプロセスを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="7863b-132">**Windows Update を再度** 実行して、インストールされた役割とサービスに対する更新プログラムがインストールされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="7863b-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="7863b-133">このサーバーで Skype for Business Server コントロール パネルを使用する場合は、Silverlight もインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="7863b-134">Silverlight をインストールするには [、Microsoft Silverlight を参照してください](https://www.microsoft.com/silverlight/)。</span><span class="sxs-lookup"><span data-stu-id="7863b-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="7863b-135">ディレクター、常設チャット、エッジの役割など、フロントエンド サーバー以外の役割を実行するサーバーの前提条件には、独自の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="7863b-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="7863b-136">各サーバーの種類に必要な正確な前提条件の詳細については [、「Skype for Business Server のサーバー要件」を参照してください](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7863b-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  


---
title: 'Lync Server 2013: 計画ツールのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e528062d5fd04e1a11df934cbc01b2dc8c92aa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="e0734-102">Lync Server 2013 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="e0734-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0734-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e0734-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e0734-104">Microsoft Lync Server 2013、計画ツールを使用して、Lync Server 2013 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0734-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="e0734-105">計画ツールは、Lync Server 2013 をインストールする予定のドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e0734-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="e0734-106">計画ツールに付随する Readme ファイルには、ツールのインストールと使用に関する重要な情報が説明されています。</span><span class="sxs-lookup"><span data-stu-id="e0734-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="e0734-107">わかりやすくするために、Readme ファイルの情報の一部をここに転載します。</span><span class="sxs-lookup"><span data-stu-id="e0734-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0734-108">計画ツールをインストールするには、ツールをインストールするコンピューターの管理者権限と権限を持つユーザーによるインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0734-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="e0734-109">計画ツールのインストールと運用でサポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0734-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="e0734-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="e0734-110">Windows 8</span></span>

  - <span data-ttu-id="e0734-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e0734-111">Windows 8.1</span></span>

  - <span data-ttu-id="e0734-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e0734-112">Windows Server 2012</span></span>

  - <span data-ttu-id="e0734-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e0734-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="e0734-114">Windows 7、32 ビット版</span><span class="sxs-lookup"><span data-stu-id="e0734-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="e0734-115">Windows 7、64 ビット版、Windows on Win32 (WOW) 使用</span><span class="sxs-lookup"><span data-stu-id="e0734-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="e0734-116">Windows Server 2008 R2、WOW 使用</span><span class="sxs-lookup"><span data-stu-id="e0734-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="e0734-117">さらに、計画ツールには Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0734-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="e0734-118">プレインストールの要件が満たされたら、計画ツールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0734-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="e0734-119">計画ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e0734-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="e0734-120">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e0734-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="e0734-121">Windows エクスプローラーまたはコマンドウィンドウを使って、計画ツールのインストールファイルをダウンロードしたディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e0734-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="e0734-122">LyncPlanningTool を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e0734-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="e0734-123">Windows Explorer で、ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0734-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="e0734-124">コマンド ウィンドウで、ファイル名を入力してから、**Enter** キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0734-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="e0734-125">**Microsoft Lync Server 2013、計画ツールのセットアップウィザード**の [ようこそ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0734-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="e0734-126">[**使用許諾契約書**] を読んでから、使用許諾契約書に同意する場合には [**使用許諾契約書に同意します**] チェック ボックスをオンにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0734-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="e0734-127">計画ツール ファイルをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0734-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="e0734-128">既定の場所は C:\\Program Files (x86)\\Microsoft Lync Server 2013\\計画ツールです。</span><span class="sxs-lookup"><span data-stu-id="e0734-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="e0734-129">インストール先を変更するには、[\*\*変更 \*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0734-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="e0734-130">[**インストール先フォルダーの変更**] で、ファイルをインストールする場所を参照または入力し、[**OK **] をクリックしてから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0734-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="e0734-131">これで、インストーラーで計画ツールをインストールする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="e0734-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="e0734-132">[**インストール**] をクリックして、インストール プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e0734-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="e0734-133">インストールが開始され、進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0734-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="e0734-134">インストールが正常に完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0734-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="e0734-135">計画ツールを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e0734-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0734-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0734-136">See Also</span></span>


[<span data-ttu-id="e0734-137">Lync Server 2013 でオプションのソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="e0734-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 計画ツールのインストール'
description: 'Lync Server 2013: 計画ツールをインストールしています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11836e2c86cb01d6f911670a9eeafef0c31c0af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575063"
---
# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="c74b2-103">Lync Server 2013 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="c74b2-103">Installing the Planning Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c74b2-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c74b2-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c74b2-105">Microsoft Lync Server 2013、計画ツールを使用して Lync Server 2013 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74b2-105">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="c74b2-106">計画ツールは、Lync Server 2013 のインストールを計画しているドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c74b2-106">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="c74b2-107">計画ツールに付属する Readme ファイルは、ツールのインストールと使用に関する重要な情報を詳細に説明しています。</span><span class="sxs-lookup"><span data-stu-id="c74b2-107">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="c74b2-108">わかりやすくするために、Readme ファイルの情報の一部をここに転載します。</span><span class="sxs-lookup"><span data-stu-id="c74b2-108">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c74b2-109">計画ツールでは、ツールをインストールするコンピューターに対する管理者権限とアクセス許可を持つユーザーがインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74b2-109">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="c74b2-110">計画ツールのインストールと運用のためにサポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c74b2-110">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="c74b2-111">Windows 8</span><span class="sxs-lookup"><span data-stu-id="c74b2-111">Windows 8</span></span>

  - <span data-ttu-id="c74b2-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c74b2-112">Windows 8.1</span></span>

  - <span data-ttu-id="c74b2-113">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c74b2-113">Windows Server 2012</span></span>

  - <span data-ttu-id="c74b2-114">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c74b2-114">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="c74b2-115">Windows 7、32 ビット版</span><span class="sxs-lookup"><span data-stu-id="c74b2-115">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="c74b2-116">Windows 7、64 ビット版、Windows on Win32 (WOW) 使用</span><span class="sxs-lookup"><span data-stu-id="c74b2-116">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="c74b2-117">Windows Server 2008 R2、WOW 使用</span><span class="sxs-lookup"><span data-stu-id="c74b2-117">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="c74b2-118">また、計画ツールには、Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c74b2-118">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="c74b2-119">プレインストールの要件を満たした後、計画ツールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c74b2-119">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="c74b2-120">計画ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c74b2-120">To install the Planning Tool</span></span>

1.  <span data-ttu-id="c74b2-121">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-121">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="c74b2-122">Windows エクスプローラーまたはコマンドウィンドウを使用して、計画ツールのインストールファイルをダウンロードしたディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c74b2-122">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="c74b2-123">LyncPlanningTool.msi を検索します。</span><span class="sxs-lookup"><span data-stu-id="c74b2-123">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="c74b2-124">Windows Explorer で、ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-124">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="c74b2-125">コマンドウィンドウで、ファイルの名前を入力し、enter キーを押して **ファイルを実行** します。</span><span class="sxs-lookup"><span data-stu-id="c74b2-125">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="c74b2-126">**Microsoft Lync Server 2013、計画ツールセットアップウィザード**の [ようこそ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-126">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="c74b2-127">**[使用許諾契約書]** を読んでから、使用許諾契約書に同意する場合には **[使用許諾契約書に同意します]** チェック ボックスをオンにして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-127">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="c74b2-128">計画ツール ファイルをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c74b2-128">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="c74b2-129">既定の場所は C: \\ Program Files (x86) \\ Microsoft Lync Server 2013 \\ Planning Tool です。</span><span class="sxs-lookup"><span data-stu-id="c74b2-129">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="c74b2-130">インストール先を変更するには、**[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-130">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="c74b2-131">**[インストール先フォルダの変更]** で、ファイルをインストールする場所を参照または入力し、**[OK]** をクリックしてから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-131">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="c74b2-132">これで、インストーラーは計画ツールをインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c74b2-132">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="c74b2-133">**[インストール]** をクリックして、インストール プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c74b2-133">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="c74b2-134">インストールが開始され、進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c74b2-134">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="c74b2-135">インストールが正常に完了したら、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74b2-135">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="c74b2-136">計画ツールを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c74b2-136">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c74b2-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c74b2-137">See Also</span></span>


[<span data-ttu-id="c74b2-138">Lync Server 2013 でオプションのソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="c74b2-138">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


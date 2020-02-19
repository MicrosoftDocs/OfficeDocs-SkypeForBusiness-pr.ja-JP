---
title: 'Lync Server 2013: 計画ツールのインストール'
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
ms.openlocfilehash: 183f63a0a08fbe74561319831d0aea3ea9f46d62
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="26604-102">Lync Server 2013 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="26604-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26604-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="26604-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="26604-104">Microsoft Lync Server 2013、計画ツールを使用して Lync Server 2013 インフラストラクチャの設計と計画を開始する前に、まず計画ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="26604-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="26604-105">計画ツールは、Lync Server 2013 のインストールを計画しているドメインまたはインフラストラクチャの一部であるワークステーションまたはサーバーに展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="26604-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="26604-106">計画ツールに付属する Readme ファイルは、ツールのインストールと使用に関する重要な情報を詳細に説明しています。</span><span class="sxs-lookup"><span data-stu-id="26604-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="26604-107">わかりやすくするために、Readme ファイルの情報の一部をここに転載します。</span><span class="sxs-lookup"><span data-stu-id="26604-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="26604-108">計画ツールでは、ツールをインストールするコンピューターに対する管理者権限とアクセス許可を持つユーザーがインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="26604-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="26604-109">計画ツールのインストールと運用のためにサポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26604-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="26604-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="26604-110">Windows 8</span></span>

  - <span data-ttu-id="26604-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="26604-111">Windows 8.1</span></span>

  - <span data-ttu-id="26604-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="26604-112">Windows Server 2012</span></span>

  - <span data-ttu-id="26604-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="26604-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="26604-114">Windows 7、32 ビット版</span><span class="sxs-lookup"><span data-stu-id="26604-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="26604-115">Windows 7、64 ビット版、Windows on Win32 (WOW) 使用</span><span class="sxs-lookup"><span data-stu-id="26604-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="26604-116">Windows Server 2008 R2、WOW 使用</span><span class="sxs-lookup"><span data-stu-id="26604-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="26604-117">また、計画ツールには、Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="26604-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="26604-118">プレインストールの要件を満たした後、計画ツールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="26604-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="26604-119">計画ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="26604-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="26604-120">Administrators グループのメンバーとして、ローカル コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="26604-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="26604-121">Windows エクスプローラーまたはコマンドウィンドウを使用して、計画ツールのインストールファイルをダウンロードしたディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="26604-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="26604-122">LyncPlanningTool.msi を検索します。</span><span class="sxs-lookup"><span data-stu-id="26604-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="26604-123">Windows Explorer で、ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="26604-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="26604-124">コマンドウィンドウで、ファイルの名前を入力し、enter キーを押して**ファイルを実行**します。</span><span class="sxs-lookup"><span data-stu-id="26604-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="26604-125">**Microsoft Lync Server 2013、計画ツールセットアップウィザード**の [ようこそ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26604-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="26604-126">**[使用許諾契約書]** を読んでから、使用許諾契約書に同意する場合には **[使用許諾契約書に同意します]** チェック ボックスをオンにして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26604-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="26604-127">計画ツール ファイルをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="26604-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="26604-128">既定の場所は C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool です。</span><span class="sxs-lookup"><span data-stu-id="26604-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="26604-129">インストール先を変更するには、**[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26604-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="26604-130">**[インストール先フォルダの変更]** で、ファイルをインストールする場所を参照または入力し、**[OK]** をクリックしてから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26604-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="26604-131">これで、インストーラーは計画ツールをインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="26604-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="26604-132">**[インストール]** をクリックして、インストール プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="26604-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="26604-133">インストールが開始され、進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26604-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="26604-134">インストールが正常に完了したら、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26604-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="26604-135">計画ツールを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="26604-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26604-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="26604-136">See Also</span></span>


[<span data-ttu-id="26604-137">Lync Server 2013 でオプションのソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="26604-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


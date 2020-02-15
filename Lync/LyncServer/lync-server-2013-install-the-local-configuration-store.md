---
title: 'Lync Server 2013: ローカル構成ストアのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00b4ffc463412064b578938516c4ea33b0dbb663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="9867f-102">Lync Server 2013 でのローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="9867f-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9867f-103">_**トピックの最終更新日:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="9867f-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="9867f-104">これらの手順を実行する前に、ローカル管理者および RTCUniversalReadOnlyAdmin グループのメンバーの両方のドメインユーザーアカウントを使用してサーバーにログオンしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9867f-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="9867f-105">Lync Server 展開ウィザードを使用して操作できるようにするには、ローカル構成ストアがサーバー上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9867f-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="9867f-106">ローカル構成ストアは、SQL Server Express のローカルインストールの後に作成される中央管理ストアの読み取り専用コピーです。</span><span class="sxs-lookup"><span data-stu-id="9867f-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="9867f-107">中央管理ストア自体が、Standard Edition サーバーまたは SQL Server Express ベースのデータベースにインストールされている既存の SQL Server データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9867f-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9867f-108">このサーバーで Lync Server 2013 セットアップを実行していない場合は、Lync Server 2013 をインストールするためのドライブとパスの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="9867f-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="9867f-109">これにより、システムドライブ以外のドライブにインストールすることができます。組織で必要な場合、または容量に関する懸念がある場合。</span><span class="sxs-lookup"><span data-stu-id="9867f-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="9867f-110">[セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを新しい、利用可能なドライブに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9867f-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="9867f-111">このパス (OCSCore を含む) にセットアップファイルをインストールすると、残りの Lync Server 2013 ファイルも同様に展開されます。</span><span class="sxs-lookup"><span data-stu-id="9867f-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="9867f-112">ローカル構成ストアをインストールするには</span><span class="sxs-lookup"><span data-stu-id="9867f-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="9867f-113">インストールメディア\\から amd64\\セットアップを参照\\し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9867f-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="9867f-114">Microsoft Visual C++ 2012 の再頒布可能パッケージをインストールするように求めるメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9867f-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="9867f-115">[**Lync Server 2013 のインストール先**] ページで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9867f-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="9867f-116">[使用許諾**契約書**] ページで、ライセンス条項を確認し、[「**使用許諾契約書**」の条項に同意します] を選択し、[ **OK** ] をクリックして続行することができます。</span><span class="sxs-lookup"><span data-stu-id="9867f-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="9867f-117">[展開ウィザード] ページで、**[Lync Server システムのインストールまたは更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9867f-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="9867f-118">[**Lync Server 2013**] ページの [**ステップ 1: ローカル構成ストアのインストール**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9867f-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="9867f-119">[**ローカル構成ストアのインストール**] ページで、[**中央管理ストアから直接取得**する] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9867f-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="9867f-120">ローカルサーバー構成のインストールが完了したら、[**完了**] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9867f-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


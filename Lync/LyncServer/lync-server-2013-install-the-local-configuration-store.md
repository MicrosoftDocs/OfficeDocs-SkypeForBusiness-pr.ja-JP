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
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="8b6bd-102">Lync Server 2013 でのローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="8b6bd-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b6bd-103">_**最終更新日:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="8b6bd-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="8b6bd-104">次の手順を実行する前に、ローカル管理者と RTCUniversalReadOnlyAdmin グループの両方のドメインユーザーアカウントでサーバーにログオンしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="8b6bd-105">Lync Server 展開ウィザードで何かを実行できるようにするには、サーバー上にローカル構成ストアが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="8b6bd-106">ローカル構成ストアは、SQL Server Express のローカルインストールの後に作成される、中央管理ストアの読み取り専用コピーです。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="8b6bd-107">サーバーの全体管理ストアは、Standard Edition server または SQL Server Express ベースのデータベースにインストールされている既存の SQL Server データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b6bd-108">このサーバーで Lync Server 2013 セットアップを実行していない場合は、Lync Server 2013 をインストールするためのドライブとパスを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="8b6bd-109">これにより、必要に応じて、システムドライブ以外のドライブにインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="8b6bd-110">[セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを、使用可能な新しいドライブに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="8b6bd-111">このパス (OCSCore など) にセットアップファイルをインストールすると、Lync Server の他の2013ファイルも一緒に展開されます。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="8b6bd-112">ローカル構成ストアをインストールするには</span><span class="sxs-lookup"><span data-stu-id="8b6bd-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="8b6bd-113">インストールメディアから\\、setup\\amd64\\Setup.exe を参照し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="8b6bd-114">Microsoft Visual C++ 2012 の再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="8b6bd-115">**Lync Server 2013 のインストール場所**のページで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="8b6bd-116">[**エンドユーザーライセンス契約**] ページで、ライセンス条項を確認し、[使用許諾**契約書の条項に同意**します] を選択してから、[ **OK** ] をクリックして続行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="8b6bd-117">展開ウィザードのページで、[ **Lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="8b6bd-118">**Lync Server 2013**ページで、[ステップ 2 **: ローカル構成ストアをインストール**します] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="8b6bd-119">[**ローカル構成ストアのインストール**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="8b6bd-120">ローカルサーバー構成のインストールが完了したら、[**完了**] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b6bd-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


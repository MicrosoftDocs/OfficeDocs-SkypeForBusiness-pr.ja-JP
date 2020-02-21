---
title: 'Lync Server 2013: 評価版からの更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787aa9f1983dc755f1ce9b35ff66320be1d5dba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="9bb4d-102">Lync Server 2013 の評価版からの更新</span><span class="sxs-lookup"><span data-stu-id="9bb4d-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bb4d-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9bb4d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9bb4d-104">Microsoft Lync Server 2013 の評価バージョンをインストールしている場合は、最終的に、そのインストールにライセンスされたソフトウェアのコピーを更新する必要があります。これは、評価版がインストールされてから180日で期限切れになるためです。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="9bb4d-105">ただし、評価版を完全にアンインストールしてからライセンス版をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="9bb4d-106">代わりに、有効なライセンスキーを取得した後で、lync server フロントエンドサーバー、ディレクター、またはエッジサーバーとして動作する各コンピューターで次の手順を実行することによって、Lync Server 2013 の評価バージョンを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="9bb4d-107">なお、監視サーバーまたはアーカイブサーバーなど、他のサーバーの役割を実行するコンピューターを更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="9bb4d-108">Microsoft Lync Server 2013 の評価版からの更新</span><span class="sxs-lookup"><span data-stu-id="9bb4d-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="9bb4d-109">Lync Server 2013 の評価版からライセンス版のソフトウェアにコンピューターを更新するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="9bb4d-110">**Microsoft Lync Server 2013 の評価版からの更新**</span><span class="sxs-lookup"><span data-stu-id="9bb4d-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="9bb4d-111">ローカル管理者としてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="9bb4d-112">[**スタート**]、[**すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9bb4d-113">Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="9bb4d-114">場合によっては、server.msi ファイルへの完全なパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="9bb4d-115">このファイルは、Lync Server ボリュームメディアのインストールファイルのセットアップフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="9bb4d-116">セットアップの実行が終了したら、コマンド プロンプトから以下のコマンドを実行して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="9bb4d-117">評価版の Lync Server を実行している他のフロントエンドサーバー、ディレクター、またはエッジサーバーでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="9bb4d-118">この手順は、Lync Server メディアインストールファイルを使用して展開されたすべてのブランチオフィスサーバーでも実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="9bb4d-119">評価版の Lync Server が特定のコンピューターで実行されているかどうかがわからない場合は、Lync Server 管理シェルから次のコマンドを実行して確認できます。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="9bb4d-120">[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) コマンドレットは、ローカル コンピューターを分析して、以下のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="9bb4d-121">Lync Server ボリュームライセンスキーがコンピューターにインストールされていること、つまり更新が不要であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="9bb4d-122">Lync Server 評価ライセンスキーがインストールされていることを意味します。つまり、コンピューターを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="9bb4d-p104">ボリューム ライセンス キーはこのコンピューターでは不要。評価版からライセンス版への更新は、フロントエンド サーバー、ディレクター、およびエッジ サーバーのみで必要。</span><span class="sxs-lookup"><span data-stu-id="9bb4d-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


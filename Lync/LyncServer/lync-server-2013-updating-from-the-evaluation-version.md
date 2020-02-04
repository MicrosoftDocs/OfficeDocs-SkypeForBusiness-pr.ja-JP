---
title: 'Lync Server 2013: 評価版から更新する'
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
ms.openlocfilehash: 2b4cc704a77f824cbf7b2ec8ab4920c25454f3c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="8498f-102">Lync Server 2013 の評価版からの更新</span><span class="sxs-lookup"><span data-stu-id="8498f-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8498f-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="8498f-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="8498f-104">Microsoft Lync Server 2013 の評価版をインストールしている場合、最終的にソフトウェアのライセンスコピーをインストールする必要があります。これは、評価バージョンがインストールされてから180日後に期限切れになるためです。</span><span class="sxs-lookup"><span data-stu-id="8498f-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="8498f-105">ただし、評価版を完全にアンインストールしてから、ライセンスを取得したバージョンをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8498f-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="8498f-106">有効なライセンスキーを取得した後は、lync server のフロントエンドサーバー、ディレクター、またはエッジサーバーとして機能するコンピューターごとに、次の手順を実行して、Lync Server 2013 の評価バージョンを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8498f-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="8498f-107">監視サーバーやアーカイブサーバーなど、他のサーバーの役割を実行しているコンピューターは更新する必要がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8498f-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="8498f-108">Microsoft Lync Server 2013 の評価版からの更新</span><span class="sxs-lookup"><span data-stu-id="8498f-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="8498f-109">Lync Server 2013 の評価版から、ライセンスを付与されたバージョンのソフトウェアにコンピューターを更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8498f-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="8498f-110">**Microsoft Lync Server 2013 の評価版からの更新**</span><span class="sxs-lookup"><span data-stu-id="8498f-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="8498f-111">ローカル管理者としてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8498f-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="8498f-112">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **Lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8498f-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8498f-113">Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8498f-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="8498f-114">ファイルサーバー .msi への完全なパスを指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8498f-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="8498f-115">このファイルは、Lync Server ボリュームメディアインストールファイルのセットアップフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="8498f-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="8498f-116">セットアップの実行が完了したら、コマンドプロンプトで次を入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8498f-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="8498f-117">評価版の Lync Server が実行されている他のフロントエンドサーバー、ディレクター、またはエッジサーバーで、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8498f-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="8498f-118">この手順は、Lync Server メディアインストールファイルを使用して展開されたブランチオフィスサーバーでも実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8498f-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="8498f-119">Lync Server の評価版が特定のコンピューターで実行されているかどうかがわからない場合は、Lync Server 管理シェルで次のコマンドを実行して確認できます。</span><span class="sxs-lookup"><span data-stu-id="8498f-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="8498f-120">[CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion)コマンドレットを実行すると、ローカルコンピューターが分析され、次のいずれかが返されます。</span><span class="sxs-lookup"><span data-stu-id="8498f-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="8498f-121">Lync Server ボリュームライセンスキーがコンピューターにインストールされていることを意味します。つまり、更新は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8498f-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="8498f-122">Lync Server 評価ライセンスキーがインストールされていることを意味します。つまり、コンピューターを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8498f-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="8498f-123">これは、コンピューター上にボリュームライセンスキーが必要ないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8498f-123">That no volume license key is required on the computer.</span></span> <span data-ttu-id="8498f-124">評価版からライセンス版への更新は、フロントエンドサーバー、監督、エッジサーバーでのみ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8498f-124">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


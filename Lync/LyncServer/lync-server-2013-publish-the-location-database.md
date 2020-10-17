---
title: 'Lync Server 2013: 場所データベースの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512374"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="2b8ed-102">Lync Server 2013 からの場所データベースの公開</span><span class="sxs-lookup"><span data-stu-id="2b8ed-102">Publish the location database from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b8ed-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="2b8ed-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="2b8ed-104">場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="2b8ed-105">詳細については、次のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="2b8ed-106">**Export-cslisconfiguration**</span><span class="sxs-lookup"><span data-stu-id="2b8ed-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="2b8ed-107">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合、ELINs を公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="2b8ed-108">PSTN キャリアでは、ELIN レコードに特定の形式を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="2b8ed-109">詳細については、PSTN キャリアにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="2b8ed-110">場所情報サービスデータベースからレコードをエクスポートし、必要に応じて書式設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="2b8ed-111">場所データベースを公開するには</span><span class="sxs-lookup"><span data-stu-id="2b8ed-111">To publish the location database</span></span>

  - <span data-ttu-id="2b8ed-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="2b8ed-113">次のコマンドレットを実行して、場所データベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="2b8ed-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>


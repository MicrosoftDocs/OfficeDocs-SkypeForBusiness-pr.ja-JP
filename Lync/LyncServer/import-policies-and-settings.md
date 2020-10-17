---
title: ポリシーと設定をインポートする
description: ポリシーと設定をインポートします。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569033"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="118c5-103">ポリシーと設定をインポートする</span><span class="sxs-lookup"><span data-stu-id="118c5-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="118c5-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="118c5-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="118c5-105">Office Communications Server 2007 R2 のトポロジ情報を Lync Server 2013 パイロットプールに結合した後、lync Server 2013 Management Shell コマンドレットを実行して、Office Communications Server の 2007 R2 ポリシーと構成設定を Lync 2013 Server のパイロットプールに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="118c5-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="118c5-106">**Import-cslegacyconfiguration**コマンドレットでは、ポリシー、音声ルート、ダイヤルプラン、Communicator Web access url、およびダイヤルインアクセス番号が Lync Server 2013 にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="118c5-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="118c5-107">ポリシーと設定を移行するには</span><span class="sxs-lookup"><span data-stu-id="118c5-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="118c5-108">Lync Server 2013 のフロントエンドサーバーで、Lync Server 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="118c5-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="118c5-109">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="118c5-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="118c5-110">ポリシーがインポートされたら、次の手順を使用して、Lync Server コントロールパネルにインポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="118c5-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="118c5-111">インポートされたポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="118c5-111">To view imported policies</span></span>

1.  <span data-ttu-id="118c5-112">Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="118c5-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="118c5-113">[**音声のルーティング**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="118c5-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="118c5-114">[**電話会議**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="118c5-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="118c5-115">[ **フェデレーションと外部アクセス** ] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="118c5-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="118c5-116">[**監視およびアーカイブ**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="118c5-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


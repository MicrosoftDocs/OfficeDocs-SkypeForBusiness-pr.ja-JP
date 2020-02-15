---
title: ポリシーと設定をインポートする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12a47ffde7d09fa7e216312211b6f0118b89233
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="9fe8d-102">ポリシーと設定をインポートする</span><span class="sxs-lookup"><span data-stu-id="9fe8d-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fe8d-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9fe8d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9fe8d-104">Office Communications Server 2007 R2 のトポロジ情報を Lync Server 2013 パイロットプールと統合した後、Office Communications Server の 2007 R2 ポリシーと構成設定を移行するには、Lync Server 2013 Management Shell コマンドレットを実行する必要があります。Lync Server 2013 パイロットプールに展開します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="9fe8d-105">**Import-cslegacyconfiguration**コマンドレットでは、ポリシー、音声ルート、ダイヤルプラン、Communicator Web access url、およびダイヤルインアクセス番号が Lync Server 2013 にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="9fe8d-106">ポリシーと設定を移行するには</span><span class="sxs-lookup"><span data-stu-id="9fe8d-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="9fe8d-107">Lync Server 2013 のフロントエンドサーバーで、Lync Server 管理シェルを起動します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="9fe8d-108">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="9fe8d-109">ポリシーがインポートされたら、次の手順を使用して、Lync Server コントロールパネルにインポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="9fe8d-110">インポートされたポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="9fe8d-110">To view imported policies</span></span>

1.  <span data-ttu-id="9fe8d-111">Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="9fe8d-112">[**音声のルーティング**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="9fe8d-113">[**電話会議**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="9fe8d-114">[**フェデレーションと外部アクセス**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="9fe8d-115">[**監視およびアーカイブ**] をクリックし、インポートされたポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 既存の展開環境からトポロジをダウンロードする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b68459a1923fcb4a066cafe02c5226b24f9321
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="ffff2-102">既存の展開環境からトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ffff2-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffff2-103">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="ffff2-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="ffff2-104">Lync Server 2013 プールを作成する場合は、Lync Server 2010 に関連付けられている中央管理ストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="ffff2-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="ffff2-105">初めてトポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffff2-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="ffff2-106">既に Lync Server 2010 トポロジが定義されており、中央管理ストアが確立されているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffff2-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="ffff2-107">トポロジ ビルダーは、データベースを読み取り、現在の定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="ffff2-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="ffff2-108">**既存の展開環境からトポロジをダウンロードするには**</span><span class="sxs-lookup"><span data-stu-id="ffff2-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="ffff2-109">[**Lync Server 展開ウィザード**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="ffff2-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="ffff2-110">[**Lync Server 2013 – 展開ウィザード**] ページで、[**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffff2-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="ffff2-111">トポロジビルダーを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013** ]、[ **lync server トポロジビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffff2-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="ffff2-112">[**既存の展開からトポロジをダウンロードする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffff2-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="ffff2-113">![展開ウィザードのトポロジビルダーの設定](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "展開ウィザードのトポロジビルダーの設定")</span><span class="sxs-lookup"><span data-stu-id="ffff2-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="ffff2-114">ファイル名を選択して、既定のファイルの種類である .tbxml でトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="ffff2-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="ffff2-115">示されているように、Lync Server ノードを展開して、展開に含まれるさまざまなサーバーの役割を表示させます。</span><span class="sxs-lookup"><span data-stu-id="ffff2-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="ffff2-116">![トポロジビルダーサーバーの役割全般プロパティ](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "トポロジビルダーサーバーの役割全般プロパティ")</span><span class="sxs-lookup"><span data-stu-id="ffff2-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


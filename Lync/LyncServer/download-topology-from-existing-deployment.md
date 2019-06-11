---
title: 既存の展開環境からトポロジをダウンロードする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c47e6d78d3bd9522b8f0369924f05f8f939037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="08f11-102">既存の展開環境からトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="08f11-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f11-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="08f11-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="08f11-104">Lync Server 2013 プールを作成する場合は、Lync Server 2010 に関連付けられている中央管理ストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="08f11-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="08f11-105">最初の使用時と後続の編集セッションでトポロジビルダーを起動すると、トポロジビルダーで現在の構成ドキュメントを読み込む場所を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08f11-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="08f11-106">既に Lync Server 2010 トポロジを定義しており、全体管理ストアを確立しているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f11-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="08f11-107">トポロジビルダーはデータベースを読み取り、現在の定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="08f11-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="08f11-108">**既存の展開からトポロジをダウンロードするには**</span><span class="sxs-lookup"><span data-stu-id="08f11-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="08f11-109">**Lync Server 展開ウィザード**を開きます。</span><span class="sxs-lookup"><span data-stu-id="08f11-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="08f11-110">[ **Lync Server 2013-展開ウィザード**] ページで、[**管理ツールのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08f11-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="08f11-111">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013** ]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="08f11-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="08f11-112">[**既存の展開からトポロジをダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08f11-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="08f11-113">![展開ウィザードのトポロジビルダーの設定](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "展開ウィザードのトポロジビルダーの設定")</span><span class="sxs-lookup"><span data-stu-id="08f11-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="08f11-114">ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="08f11-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="08f11-115">表示されている [Lync Server] ノードを展開して、展開内のさまざまなサーバーの役割を表示します。</span><span class="sxs-lookup"><span data-stu-id="08f11-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="08f11-116">![トポロジビルダーサーバーの役割の全般プロパティ](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "トポロジビルダーサーバーの役割の全般プロパティ")</span><span class="sxs-lookup"><span data-stu-id="08f11-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 音声番号の正規化とルーティングの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92809d018bf8b69e6bc3fd5cc640c40836249de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="a1905-102">Lync Server 2013 での音声番号の正規化とルーティングの検証</span><span class="sxs-lookup"><span data-stu-id="a1905-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1905-103">_**トピックの最終更新日:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="a1905-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="a1905-104">適切な番号の正規化とルーティングは、機能するエンタープライズ Voip 環境にとって非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="a1905-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="a1905-105">特に、構内交換 (PBX) からスタンドアロンの Lync Server 環境への移行では、移行を成功させるためのキーの1つは、既存のすべてのダイヤルルールを明らかにして文書化し、適切な正規化ルール、音声ポリシー、およびを作成することです。電話の使用状況とルート。</span><span class="sxs-lookup"><span data-stu-id="a1905-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="a1905-106">番号の正規化とルーティングを検証することは、移行時だけでなく、通常のシステムの安定した運用時においても重要です。</span><span class="sxs-lookup"><span data-stu-id="a1905-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="a1905-107">Lync server コントロールパネルを使用して毎日この検証を行うことをお勧めします。まず、lync Server のグローバル設定で発行された現在の正規化ルールのセットに対して、堅牢なテストケースのセットを開発することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1905-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="a1905-108">これらのテストケースは、ダイヤルプランに対して行われた不要な変更を強調表示するために、毎日実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1905-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="a1905-109">Lync Server コントロールパネルを使用すると、音声ルーティングに関する構成情報を視覚化、テスト、変更、アーカイブ、および共有することができます。また、エンタープライズ Voip 番号の正規化ルール、ダイヤルプラン、音声ポリシー、およびルートを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1905-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="a1905-110">これには、次のような追加の機能があります。</span><span class="sxs-lookup"><span data-stu-id="a1905-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="a1905-111">システム間での音声ルーティングデータのエクスポートとインポートまたはバックアップ。</span><span class="sxs-lookup"><span data-stu-id="a1905-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="a1905-112">ライブシステムにアップロードする前に、構成の変更をテストします。</span><span class="sxs-lookup"><span data-stu-id="a1905-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="a1905-113">構成テストケースを作成して実行することにより、データを変更した後、展開されたシステムへの変更をコミットする前に、データをルーティングする際の利便性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a1905-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="a1905-114">必要な正規表現を記述せずに、数字の正規化ルール、場所のプロファイル、音声ポリシー、およびルーティングデータを作成および変更する。</span><span class="sxs-lookup"><span data-stu-id="a1905-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="a1905-115">Lync Server Phone Edition との互換性のための場所プロファイルの分析。</span><span class="sxs-lookup"><span data-stu-id="a1905-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="a1905-116">音声ルーティングテストの詳細については[、「Lync Server 2013 のテスト用音声ルーティング」](lync-server-2013-test-voice-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1905-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a1905-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1905-117">See Also</span></span>


[<span data-ttu-id="a1905-118">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="a1905-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


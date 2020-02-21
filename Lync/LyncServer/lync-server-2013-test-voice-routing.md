---
title: 'Lync Server 2013: 音声ルーティングのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a9130a0020ce6b64119bd1704a9e585491fadd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="34a6f-102">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="34a6f-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34a6f-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="34a6f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="34a6f-104">[Lync Server コントロールパネル] [**音声ルーティングのテスト**] タブを使用して、テストケースシナリオを構成できます。</span><span class="sxs-lookup"><span data-stu-id="34a6f-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="34a6f-105">テスト ケースを定義するには、ダイヤル プラン、音声ポリシー、PSTN 使用法、およびボイス ルートを、テストする特定の電話番号に対して指定します。</span><span class="sxs-lookup"><span data-stu-id="34a6f-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="34a6f-106">音声ルーティング構成を実際に展開する前に、さまざまな電話番号でテストして、期待している結果が得られることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34a6f-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="34a6f-107">[<STRONG>テスト ケースのエクスポート</STRONG>] コマンドおよび [<STRONG>テスト ケースのインポート</STRONG>] コマンドを使用して、音声ルーティングのテスト ケースを保存したり、他のコンピューターで使用するためにインポートしたりできます。</span><span class="sxs-lookup"><span data-stu-id="34a6f-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="34a6f-108">ダイヤル プラン、音声ポリシー、ボイス ルート、電話使用法などの音声ルーティング構成の一部を削除した場合、音声ルーティング テスト ケースを確認して更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a6f-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="34a6f-109">Lync Server コントロールパネルは、構成が変更されたために有効でなくなったケースをテストすることを警告しません。</span><span class="sxs-lookup"><span data-stu-id="34a6f-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="34a6f-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="34a6f-110">In This Section</span></span>

  - [<span data-ttu-id="34a6f-111">Lync Server 2013 での音声ルーティングテストケースの作成</span><span class="sxs-lookup"><span data-stu-id="34a6f-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="34a6f-112">Lync Server 2013 での音声ルーティングテストケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="34a6f-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="34a6f-113">Lync Server 2013 での音声ルーティングテストケースのインポート</span><span class="sxs-lookup"><span data-stu-id="34a6f-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="34a6f-114">Lync Server 2013 での音声ルーティングテストの実行</span><span class="sxs-lookup"><span data-stu-id="34a6f-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


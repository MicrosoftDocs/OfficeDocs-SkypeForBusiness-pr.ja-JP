---
title: 'Lync Server 2013: 音声ルーティングのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac9fdac24178bfec7ebce97cbdfdd15707913d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="cc74d-102">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="cc74d-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc74d-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cc74d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="cc74d-104">Lync Server コントロールパネルの [**ボイスルーティングのテスト**] タブを使用して、テストケースのシナリオを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cc74d-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="cc74d-105">テストケースを定義するには、指定した電話番号をテストするためのダイヤルプラン、音声ポリシー、PSTN 使用量、および音声ルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc74d-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="cc74d-106">実際にボイスルーティング構成を展開する前に、さまざまな電話番号でテストして、期待どおりの結果が得られていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cc74d-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="cc74d-107">[<STRONG>テストケースのエクスポート</STRONG>] と [<STRONG>テストケースのインポート</STRONG>] コマンドを使用して、ボイスルーティングテストケースを保存し、別のコンピューターで使用するためにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc74d-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="cc74d-108">ダイヤルプラン、ボイスポリシー、ボイスルート、または電話の使用状況など、音声ルーティング構成の一部を削除する場合は、ボイスルーティングテストケースを確認して更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc74d-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="cc74d-109">Lync Server コントロールパネルでは、設定が変更されたために無効になったケースをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cc74d-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc74d-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="cc74d-110">In This Section</span></span>

  - [<span data-ttu-id="cc74d-111">Lync Server 2013 での音声ルーティング テスト ケースの作成</span><span class="sxs-lookup"><span data-stu-id="cc74d-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="cc74d-112">Lync Server 2013 での音声ルーティング テスト ケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="cc74d-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="cc74d-113">Lync Server 2013 音声ルーティング テスト ケースのインポート</span><span class="sxs-lookup"><span data-stu-id="cc74d-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="cc74d-114">Lync Server 2013 での音声ルーティング テストの実行</span><span class="sxs-lookup"><span data-stu-id="cc74d-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


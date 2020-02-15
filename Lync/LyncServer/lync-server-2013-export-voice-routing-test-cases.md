---
title: 'Lync Server 2013: 音声ルーティングテストケースのエクスポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d014d9c2748a5e6479c0f86ebd32255f3361ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="a5a0e-102">Lync Server 2013 での音声ルーティングテストケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="a5a0e-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5a0e-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a5a0e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a5a0e-104">テストケースでは、組織内のボイスルートをテストする方法が提供されます。ダイヤルする番号、使用するダイヤルプラン、音声ポリシーなどを定義することができます。また、これらの条件が満たされた場合に、指定された番号を使用して、PSTN ネットワークに正常にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="a5a0e-105">Lync Server コントロールパネルを使用して作成できるテストケースは、通常、ケースが最初に作成されて実行されたサーバーにのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="a5a0e-106">ただし、これらのテスト ケースは XML ファイル (拡張子 .vtest) としてエクスポートし、他のサーバーにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="a5a0e-107">これにより、トポロジ内のさまざまな地点にあるさまざまなコンピューターで同じテストを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="a5a0e-108">音声ルーティングのテスト ケースをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a5a0e-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="a5a0e-109">Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="a5a0e-p102">[**音声ルーティングのテスト**] タブで、エクスポート対象のテスト ケースを選択します。複数のテスト ケースを選択するには、エクスポートする 1 番目のケースをクリックし、Ctrl キーを押し下げたまま、エクスポートするその他のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="a5a0e-112">[**操作**] メニューの [**テスト ケースのエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="a5a0e-p103">[**名前を付けて保存**] ダイアログ ボックスで、エクスポートされたテスト ケースを保存するフォルダーを選択し、[**ファイル名**] ボックスに作成される XML ファイルの名前を入力します。複数のテスト ケースをエクスポートする場合は、テスト ケースのすべてが 1 つの XML ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="a5a0e-115">テスト ケースを保存するには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5a0e-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5a0e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5a0e-116">See Also</span></span>


[<span data-ttu-id="a5a0e-117">Lync Server 2013 での音声ルーティングテストケースのインポート</span><span class="sxs-lookup"><span data-stu-id="a5a0e-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


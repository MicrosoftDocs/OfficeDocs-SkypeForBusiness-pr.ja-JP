---
title: 'Lync Server 2013: 音声ルーティング テスト ケースのエクスポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e47158d9ea3da6f04a1424026c7edb73c1d482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="2a1ac-102">Lync Server 2013 での音声ルーティング テスト ケースのエクスポート</span><span class="sxs-lookup"><span data-stu-id="2a1ac-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a1ac-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a1ac-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2a1ac-104">テストケースは、組織内のボイスルートをテストするための手段を提供します。ダイヤルする番号や、使用するダイヤルプランや音声ポリシーなどを定義し、そのような条件が満たされた場合に、指定された電話番号が表示されるようにします。PSTN ネットワークに正常にルーティングされました。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="2a1ac-105">Lync Server コントロールパネルを使用して作成できるテストケースは、通常、ケースが最初に作成されて実行されたサーバーにのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="2a1ac-106">ただし、これらのテストケースは XML ファイルとしてエクスポートし、他のサーバーにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="2a1ac-107">これにより、トポロジ内のさまざまな場所にあるさまざまなコンピューターで同じテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="2a1ac-108">ボイスルーティングテストケースをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="2a1ac-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="2a1ac-109">Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="2a1ac-110">[**テスト用のボイスルーティング**] タブで、エクスポートするテストケース (またはテストケース) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-110">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported.</span></span> <span data-ttu-id="2a1ac-111">複数のテストケースを選択するには、エクスポートする最初のケースをクリックして、Ctrl キーを押しながら、エクスポートする追加のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-111">To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="2a1ac-112">[**アクション**] をクリックし、[**テストケースのエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="2a1ac-113">[名前**を付けて保存**] ダイアログボックスで、エクスポートされたテストケースを保存するフォルダーを選択し、結果の XML ファイルの名前を [**ファイル名**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-113">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box.</span></span> <span data-ttu-id="2a1ac-114">複数のテストケースをエクスポートする場合、これらのすべてのテストケースは1つの XML ファイルに保存されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-114">Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="2a1ac-115">テストケースを保存するには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a1ac-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a1ac-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a1ac-116">See Also</span></span>


[<span data-ttu-id="2a1ac-117">Lync Server 2013 音声ルーティング テスト ケースのインポート</span><span class="sxs-lookup"><span data-stu-id="2a1ac-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


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

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013 での音声ルーティング テスト ケースのエクスポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

テストケースは、組織内のボイスルートをテストするための手段を提供します。ダイヤルする番号や、使用するダイヤルプランや音声ポリシーなどを定義し、そのような条件が満たされた場合に、指定された電話番号が表示されるようにします。PSTN ネットワークに正常にルーティングされました。

Lync Server コントロールパネルを使用して作成できるテストケースは、通常、ケースが最初に作成されて実行されたサーバーにのみ保存されます。 ただし、これらのテストケースは XML ファイルとしてエクスポートし、他のサーバーにインポートすることができます。 これにより、トポロジ内のさまざまな場所にあるさまざまなコンピューターで同じテストを実行できます。

<div>

## <a name="to-export-a-voice-routing-test-case"></a>ボイスルーティングテストケースをエクスポートするには

1.  Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

2.  [**テスト用のボイスルーティング**] タブで、エクスポートするテストケース (またはテストケース) を選択します。 複数のテストケースを選択するには、エクスポートする最初のケースをクリックして、Ctrl キーを押しながら、エクスポートする追加のケースを選択します。

3.  [**アクション**] をクリックし、[**テストケースのエクスポート**] をクリックします。

4.  [名前**を付けて保存**] ダイアログボックスで、エクスポートされたテストケースを保存するフォルダーを選択し、結果の XML ファイルの名前を [**ファイル名**] ボックスに入力します。 複数のテストケースをエクスポートする場合、これらのすべてのテストケースは1つの XML ファイルに保存されることに注意してください。

5.  テストケースを保存するには、[**保存**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 音声ルーティング テスト ケースのインポート](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


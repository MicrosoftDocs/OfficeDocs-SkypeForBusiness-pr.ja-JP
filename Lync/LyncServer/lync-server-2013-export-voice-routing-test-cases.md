---
title: 'Lync Server 2013: 音声ルーティングテストケースのエクスポート'
description: 'Lync Server 2013: 音声ルーティングテストケースをエクスポートします。'
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
ms.openlocfilehash: 934bd183a17c46cf82fe5bc04faaa55a9bbe4731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564783"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013 での音声ルーティングテストケースのエクスポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

テストケースでは、組織内の音声ルートをテストする方法が提供されます。ダイヤルする番号、使用するダイヤルプラン、音声ポリシーなどを定義します。また、これらの条件が満たされた場合に、指定した番号を PSTN ネットワークにルーティングすることができます。

Lync Server コントロールパネルを使用して作成できるテストケースは、通常、ケースが最初に作成されて実行されたサーバーにのみ保存されます。 ただし、これらのテスト ケースは XML ファイル (拡張子 .vtest) としてエクスポートし、他のサーバーにインポートできます。 これにより、トポロジ内のさまざまな地点にあるさまざまなコンピューターで同じテストを実行できるようになります。

<div>

## <a name="to-export-a-voice-routing-test-case"></a>音声ルーティングのテスト ケースをエクスポートするには

1.  Lync Server コントロールパネルで、[ **音声ルーティング** ] をクリックし、[ **音声ルーティングのテスト**] をクリックします。

2.  [**音声ルーティングのテスト**] タブで、エクスポート対象のテスト ケースを選択します。複数のテスト ケースを選択するには、エクスポートする 1 番目のケースをクリックし、Ctrl キーを押し下げたまま、エクスポートするその他のケースを選択します。

3.  [**操作**] メニューの [**テスト ケースのエクスポート**] をクリックします。

4.  [**名前を付けて保存**] ダイアログ ボックスで、エクスポートされたテスト ケースを保存するフォルダーを選択し、[**ファイル名**] ボックスに作成される XML ファイルの名前を入力します。複数のテスト ケースをエクスポートする場合は、テスト ケースのすべてが 1 つの XML ファイルに保存されます。

5.  テスト ケースを保存するには、[**保存**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングテストケースのインポート](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


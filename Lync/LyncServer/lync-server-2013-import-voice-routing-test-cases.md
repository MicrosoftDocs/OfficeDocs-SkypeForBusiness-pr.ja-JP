---
title: 'Lync Server 2013: 音声ルーティングテストケースのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43ab26d61009683623d3c536a26c8be04a3846e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013 での音声ルーティングテストケースのインポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

テストケースでは、組織内のボイスルートをテストする方法が提供されます。ダイヤルする番号、使用するダイヤルプランと音声ポリシーなどを定義し、Lync Server 2013 は、これらの条件が満たされた場合に、指定された数の successfully に PSTN ネットワークにルーティングされます。

Lync Server コントロールパネルを使用して作成できるテストケースは、通常、ケースが最初に作成されて実行されたサーバーにのみ保存されます。 ただし、これらのテスト ケースは XML ファイル (拡張子 .vtest) としてエクスポートし、他のサーバーにインポートできます。 これにより、同じテストをトポロジの別の地点に配置された別のコンピューターで実行できます。

<div>

## <a name="to-import-a-voice-routing-test-case"></a>音声ルーティングのテスト ケースをインポートするには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**操作**] メニューの [**テスト ケースのインポート**] をクリックします。

5.  インポートするテスト ケースのファイル (.vtest) を探して、[**開く**] をクリックします。

6.  [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > .vtest ファイルをインポートするときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、テスト ケースを公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングテストケースのエクスポート](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


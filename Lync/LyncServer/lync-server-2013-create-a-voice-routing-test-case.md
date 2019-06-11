---
title: 'Lync Server 2013: 音声ルーティング テスト ケースの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Lync Server 2013 での音声ルーティング テスト ケースの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>テストケースを作成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [**テスト用の音声ルーティング**] ページで [**新規**] をクリックして、新しいテストケースを作成します。

5.  [**名前**] に、テストケースの一意の名前を入力します。
    
    この名前は、エンタープライズ Voip 展開では、すべてのボイスルーティングテストケースの間で一意である必要があります。 長さは最長32文字で、バックスラッシュ (\\)、ピリオド (.)、またはアンダースコア (\_) に加えて、英数字を含めることができます。

6.  [**ダイヤルする番号**] に、このテストケースに指定したルーティング構成のテストに使用するダイヤルされた番号を入力します。 この番号は、ダイヤルプラン、ルーティング、および音声ポリシーに基づいて正規化され、出力として表示されます。

7.  [**ダイヤルプラン**] ボックスの一覧で、テストの実行時に使用するダイヤルプランを選択します。 [既定値はグローバルダイヤルプランです。

8.  [**音声ポリシー** ] ボックスの一覧で、テストの実行時に使用する音声ポリシーを選択します。 [既定値はグローバルボイスポリシーです。

9.  **期待される翻訳**では、翻訳後に表示されるはずの形式で電話番号を入力します。 これは、選択したダイヤルプランで一致する最初の正規化ルールによって翻訳された後に、テストする電話番号の値です。 テストケースを実行したときに、テストしている数値が予期した**翻訳**の値ではない場合、テストは失敗します。

10. 省略[予期される**PSTN 使用量**] ボックスの一覧で、指定したダイヤルプランとボイスポリシーに基づいてテストケースを実行するときに使用されると予想される公衆交換電話網 (PSTN) 利用状況レコードを選ぶことができます。 別の PSTN 利用状況レコードが使用されている場合、テストは失敗します。

11. 省略[想定される**ルート**] ボックスの一覧で、指定したダイヤルプランとボイスポリシーに基づいてテストケースを実行するときに使用されると予想されるボイスルートを選ぶことができます。 別のボイスルートが使用されている場合、テストは失敗します。

12. 省略[**実行**] をクリックしてテストケースを実行します。 結果がページの右側のパネルに表示されます。

13. **[OK]** をクリックします。

14. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ボイスルーティングテストケースを作成するたびに、[<STRONG>すべてコミット</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。

    
    </div>
    
    テストで採用されているダイヤルプランが、プラス記号 (+ 12065551219 など) で始まる電話番号を正規化していない場合、そのプランが原因でボイスルーティングテストが失敗する可能性があります。 (ダイヤルプランとボイスルートは動作しますが、実際にはテスト-CsDialPlan は成功します。 ただし、音声ルーティングテストが失敗することがあります。)ボイスルートをテストするときは、この点に注意してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティング テスト ケースのエクスポート](lync-server-2013-export-voice-routing-test-cases.md)  
[Lync Server 2013 音声ルーティング テスト ケースのインポート](lync-server-2013-import-voice-routing-test-cases.md)  


[Lync Server 2013 でのダイヤル プランの構成](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


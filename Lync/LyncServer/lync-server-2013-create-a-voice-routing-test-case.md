---
title: 'Lync Server 2013: 音声ルーティングテストケースを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da110d7e3bfb7188384163cb572591d0bf7f8ff3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501774"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Lync Server 2013 での音声ルーティングテストケースの作成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>テスト ケースを作成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [**音声ルーティングのテスト**] ページで、[**新規**] をクリックして、新しいテスト ケースを作成します。

5.  [**名前**] フィールドに、テスト ケースの一意の名前を入力します。
    
    名前は、エンタープライズ VoIP 展開内のすべての音声ルーティング テスト ケースの中で一意である必要があります。 最大で32文字まで指定でき、円記号 ( \\ )、ピリオド (.)、またはアンダースコア () に加えて、英数字を含めることができ \_ ます。

6.  [**テスト対象のダイヤル番号**] に、このテスト ケースで指定しているルーティング構成のテストに使用されるダイヤル番号を入力します。この番号は、ダイヤル プラン、ルート、および音声ポリシーに基づいて正規化され、出力として表示されます。

7.  [**ダイヤル プラン**] リストで、テスト実行時に使用するダイヤル プランを選択します。 既定値はグローバル ダイヤル プランです。

8.  [**音声ポリシー**] リストで、テスト実行時に使用する音声ポリシーを選択します。 既定値はグローバル音声ポリシーです。

9.  [**予想される変換**] に、変換後の予想表示形式で電話番号を入力します。これは、選択したダイヤル プランで最初に一致する正規化ルールによって変換された後の、テスト対象の電話番号の値です。テスト ケースの実行時に、テスト対象の番号が [**予想される変換**] の値にならない場合、テストは不合格です。

10. (オプション) [**予想される PSTN 使用法**] リストで、指定したダイヤル プランおよび音声ポリシーに基づいて、テスト ケースの実行時に使用されることが予想される公衆交換電話網 (PSTN) 使用法レコードを選択できます。別の PSTN 使用法レコードが使用される場合、テストは不合格です。

11. (オプション) [**予想されるルート**] リストで、指定したダイヤル プランおよび音声ポリシーに基づいて、テスト ケースの実行時に使用されることが予想されるボイス ルートを選択できます。 別のボイス ルートが使用される場合、テストは不合格です。

12. (オプション) [**実行**] をクリックして、テスト ケースを実行します。 結果は、ページの右パネルに表示されます。

13. [**OK**] をクリックします。

14. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 音声ルーティング テスト ケースを作成するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A> 」を参照してください。

    
    </div>
    
    テストで採用されているダイヤルプランが、プラス記号 (+ 12065551219 など) で始まる電話番号を正規化している場合、そのプランでは音声ルーティングテストが失敗する可能性があります。 (実際には、ダイヤルプランと音声ルートは機能しますが、実際には Test-CsDialPlan は成功します。 ただし、音声ルーティングテストは失敗する可能性があります。)これは、音声ルートをテストするときに留意すべきことです。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングテストケースのエクスポート](lync-server-2013-export-voice-routing-test-cases.md)  
[Lync Server 2013 での音声ルーティングテストケースのインポート](lync-server-2013-import-voice-routing-test-cases.md)  


[Lync Server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


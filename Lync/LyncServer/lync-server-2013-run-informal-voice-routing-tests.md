---
title: 'Lync Server 2013: 非公式の音声ルーティングテストを実行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Lync Server 2013 で非公式の音声ルーティングテストを実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-07_

[**音声ルーティングのテストケース情報の作成**] ダイアログボックスを使用して、実際のテストケースを作成する前に非公式なテストを実行することができます。 テストの結果に問題がなければ、正式なテストケースとして保存するオプションがあります。

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>非公式のボイスルーティングテストを実行するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [**音声ルーティングのテスト**] ページで、[**ボイスルーティングテストケース情報の作成**] をクリックします。

5.  [**ダイヤル先番号**] フィールドに、このテストに使用する電話番号を入力します。 この数値は正規化され、[**結果**] ウィンドウの [正規化された**数値**] フィールドに表示されます。

6.  [**ダイヤルプラン**] ボックスの一覧で、ダイヤルした番号のテストに使用するダイヤルプランを選択します。 [既定値はグローバルダイヤルプランです。
    
    テストを実行すると、ダイヤルした番号に一致するこのダイヤルプランの最初の正規化ルールが、[**結果**] ウィンドウの [**正規化ルール**] フィールドに表示されます。

7.  [**音声ポリシー** ] ボックスの一覧で、ダイヤルした番号のテストに使用する音声ポリシーを選択します。 [既定値はグローバルボイスポリシーです。
    
    テストを実行すると、この音声ポリシーの最初に一致した PSTN 使用状況レコードが、[**結果**] ウィンドウの**最初の pstn 使用状況**フィールドに表示されます。 また、この PSTN 使用状況レコードに関連付けられている最初の音声ルートは、 **1 番目の route**フィールドに表示されます。

8.  省略特定のユーザーに割り当てられている音声ポリシーを使ってダイヤルした番号をテストする場合は、[**ユーザーから**] チェックボックスをオンにします。
    
    1.  [**参照**] をクリックして、[**エンタープライズ Voip ユーザーの選択**] ダイアログボックスを表示します。
    
    2.  [**検索**] をクリックすると、エンタープライズ voip が有効になっているユーザーの一覧が表示されます。
    
    3.  このテストに使用する、割り当てられた音声ポリシーを持つユーザー名をダブルクリックします。 [**ポリシー** ] フィールドに、選択したユーザーに割り当てられた音声ポリシーが設定されます。
    
    テストを実行すると、この音声ポリシーの最初に一致する公衆交換電話網 (PSTN) 利用状況レコードが、[**結果**] ウィンドウの**最初の PSTN 使用状況**フィールドに表示されます。 また、この PSTN 使用状況レコードに関連付けられている最初の音声ルートは、 **1 番目の route**フィールドに表示されます。

9.  [**実行**] をクリックしてテストケースを実行します。 結果は、ダイアログボックスの右側のパネルに表示されます。

10. 省略このテスト構成を正式なテストケースとして保存する場合は、[**名前を付けて保存**] をクリックします。
    
    1.  [**ボイスルーティングテストケース情報の保存**] ダイアログボックスの [**名前**] フィールドに、テストケースの一意の名前を入力します。
        
        この名前は、エンタープライズ Voip 展開では、すべてのボイスルーティングテストケースの間で一意である必要があります。 長さは最長32文字で、バックスラッシュ (\\)、ピリオド (.)、またはアンダースコア (\_) に加えて、英数字を含めることができます。
    
    2.  [**ボイスルーティングテストケース情報の保存**] ダイアログボックスの残りのフィールドは読み取り専用であり、非公式なテスト構成*と*結果から事前に設定されていることに注意してください。 これが、テストケースに対して保存する構成であることを確認します。
        
        <div>
        

        > [!NOTE]  
        > テスト結果からの値は、[<STRONG>ボイスルーティングテストケース情報の保存</STRONG>] ダイアログボックスで、次のようにフィールドを事前に事前生成するために使用されます。 
        > <UL>
        > <LI>
        > <P><STRONG>期待される翻訳</STRONG>には、[正規化された<STRONG>数値</STRONG>] フィールドの値があらかじめ表示されています。</P>
        > <LI>
        > <P><STRONG>期待されるルート</STRONG>には、[<STRONG>第1ルート</STRONG>] フィールドの値があらかじめ記載されています。</P>
        > <LI>
        > <P><STRONG>期待される pstn 使用状況レコード</STRONG>には、<STRONG>最初の pstn 利用状況</STRONG>フィールドの値があらかじめ登録されています。</P></LI></UL>テストの実行時にこれらのいずれかの値との一致が見つからなかった場合、[<STRONG>ボイスルーティングテストケース情報の保存</STRONG>] ダイアログボックスで対応するフィールドが空になります。

        
        </div>
    
    3.  [ **Ok]** をクリックしてテストケースを保存するか、[**キャンセル**] をクリックして [**音声ルーティングテストケース情報の表示**] ダイアログボックスに戻り、保存する前にさらにテストを作成します。

11. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ボイスルーティングテストケースを作成するたびに、[<STRONG>すべてコミット</STRONG>] コマンドを実行してテストケースを公開する必要があります。 詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティング テスト ケースの作成](lync-server-2013-create-a-voice-routing-test-case.md)  
[Lync Server 2013 でボイスルーティングテストケースを実行する](lync-server-2013-run-voice-routing-test-cases.md)  
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


---
title: 'Lync Server 2013: 音声ルーティングテストケースを実行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013 でボイスルーティングテストケースを実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

ボイスルーティングテストケーススイートですべてのテストケースを実行するか、1つ以上の選択されたテストケースを実行することができます。

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>すべての音声ルーティングテストケースを実行するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [**ボイスルーティングのテスト**] ページで、[**アクション**] をクリックし、[**すべて実行**] をクリックします。
    
    各テストケースの合格状態または失敗状態は、 **pass/fail**列に表示されます。 テストケースがまだ実行されていない場合は、**合格/失敗**列に該当する N/a が表示されます。

5.  省略各テストケースの詳細な結果を確認するには、テストケースの名前をダブルクリックします。 結果は、[**テストケースの編集**] ページの右側の影付きの領域に表示されます。
    
    1.  **テスト結果:** テストケース実行の全体の合否または失敗の状態。
    
    2.  **正規化ルール:** ダイヤルされた番号 ([指定した**番号**] フィールドの値) と一致する、このテストケースに対して選択したダイヤルプランの最初の正規化ルール。
    
    3.  正規化された**数値:** 正規化ルールによって翻訳されたダイヤルされた番号の値。
    
    4.  **第1の PSTN 使用量:** ダイヤルされた番号に一致する、このテストケースで選択された音声ポリシーの最初の公衆交換電話網 (PSTN) 使用状況レコード。
    
    5.  **第1のルート:** ダイヤルされた番号に一致する最初の PSTN 利用状況レコードの最初のボイスルート。
        
        <div>
        

        > [!NOTE]  
        > ボイスルーティングテストケース構成では、予期される<STRONG>PSTN 使用状況レコード</STRONG>と予期される<STRONG>ルート</STRONG>フィールドは省略可能です。 テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>選択した1つ以上のボイスルーティングテストケースを実行するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [**ボイスルーティングのテスト**] ページで、実行するテストケースの名前をクリックします。

5.  [**操作**] メニューの [**選択**して実行] をクリックします。
    
    各テストケースの合格状態または失敗状態は、 **pass/fail**列に表示されます。 テストケースがまだ実行されていない場合は、**合格/失敗**列に該当する N/a が表示されます。

6.  省略各テストケースの詳細な結果を確認するには、テストケースの名前をダブルクリックします。 結果は、[**テストケースの編集**] ページの右側の影付きの領域に表示されます。
    
    1.  **テスト結果:** テストケース実行の全体の合否または失敗の状態。
    
    2.  **正規化ルール:** ダイヤルされた番号 ([指定した**番号**] フィールドの値) と一致する、このテストケースに対して選択したダイヤルプランの最初の正規化ルール。
    
    3.  正規化された**数値:** 正規化ルールによって翻訳されたダイヤルされた番号の値。
    
    4.  **第1の PSTN 使用量:** このテストケースで、ダイヤルされた番号と一致するボイスポリシーの最初の PSTN 使用状況レコード。
    
    5.  **第1のルート:** ダイヤルされた番号に一致する最初の PSTN 利用状況レコードの最初のボイスルート。
        
        <div>
        

        > [!NOTE]  
        > ボイスルーティングテストケース構成では、予期される<STRONG>PSTN 使用状況レコード</STRONG>と予期される<STRONG>ルート</STRONG>フィールドは省略可能です。 テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。

        
        </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
[Lync Server 2013 での音声ルーティング テストの実行](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 音声ルーティングテストケースの実行'
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
ms.openlocfilehash: 06c7119d8b011a805ffbc19c3b63f8832f302556
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511150"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013 での音声ルーティングテストケースの実行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

音声ルーティングテストケーススイートですべてのテストケースを実行することも、1つ以上の選択したテストケースを実行することもできます。

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>すべての音声ルーティングテストケースを実行するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [ **音声ルーティングのテスト** ] ページで、[ **アクション** ] をクリックし、[ **すべて実行**] をクリックします。
    
    各テストケースの成功または失敗の状態は、[ **成功/失敗** ] 列に表示されます。 テストケースがまだ実行されていない場合は、[ **成功/失敗** ] 列に N/a が表示されます。

5.  オプション各テストケースの詳細な結果を確認するには、テストケース名をダブルクリックします。 結果は、[ **テストケースの編集** ] ページの右側の影付き領域に表示されます。
    
    1.  **テスト結果:** テストケース実行の全体的な合格または失敗の状態。
    
    2.  **正規化ルール:** ダイヤル番号 ([ **テストする番号** ] フィールドの値) と一致する、このテストケースで選択されているダイヤルプランの最初の正規化ルール。
    
    3.  正規化された**数値:** 正規化ルールによって変換された後のダイヤル番号の値。
    
    4.  **最初の PSTN 使用法:** ダイヤル番号に一致する、このテストケースで選択した音声ポリシーに含まれる最初の公衆交換電話網 (PSTN) 使用法レコード。
    
    5.  **最初のルート:** ダイヤル番号に一致する最初の PSTN 使用法レコードの最初のボイスルート。
        
        <div>
        

        > [!NOTE]  
        > 音声ルーティングテストケース構成では、予想される <STRONG>PSTN 使用法レコード</STRONG> および予想される <STRONG>ルート</STRONG> フィールドはオプションです。 テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>選択した1つ以上の音声ルーティングテストケースを実行するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [ **音声ルーティングのテスト** ] ページで、実行するテストケースの名前をクリックします。

5.  [ **アクション** ] メニューの [ **選択した**ものを実行] をクリックします。
    
    各テストケースの成功または失敗の状態は、[ **成功/失敗** ] 列に表示されます。 テストケースがまだ実行されていない場合は、[ **成功/失敗** ] 列に N/a が表示されます。

6.  オプション各テストケースの詳細な結果を確認するには、テストケース名をダブルクリックします。 結果は、[ **テストケースの編集** ] ページの右側の影付き領域に表示されます。
    
    1.  **テスト結果:** テストケース実行の全体的な合格または失敗の状態。
    
    2.  **正規化ルール:** ダイヤル番号 ([ **テストする番号** ] フィールドの値) と一致する、このテストケースで選択されているダイヤルプランの最初の正規化ルール。
    
    3.  正規化された**数値:** 正規化ルールによって変換された後のダイヤル番号の値。
    
    4.  **最初の PSTN 使用法:** ダイヤル番号と一致する、このテストケースで選択されている音声ポリシーの最初の PSTN 使用法レコード。
    
    5.  **最初のルート:** ダイヤル番号に一致する最初の PSTN 使用法レコードの最初のボイスルート。
        
        <div>
        

        > [!NOTE]  
        > 音声ルーティングテストケース構成では、予想される <STRONG>PSTN 使用法レコード</STRONG> および予想される <STRONG>ルート</STRONG> フィールドはオプションです。 テストケースでこれらの値が指定されていない場合、テスト結果の対応するフィールドは空になります。

        
        </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
[Lync Server 2013 での音声ルーティングテストの実行](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


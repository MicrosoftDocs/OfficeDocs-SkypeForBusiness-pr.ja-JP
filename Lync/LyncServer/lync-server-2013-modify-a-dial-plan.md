---
title: 'Lync Server 2013: ダイヤル プランの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4c007933eb7186e412ada1a3f4c35b241f5eff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Lync Server 2013 でのダイヤル プランの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

既存のダイヤルプランを変更するには、次の手順を実行します。 新しいダイヤルプランを作成する場合は、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください。

<div>

## <a name="to-modify-a-dial-plan"></a>ダイヤル プランを変更するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**ダイヤル プラン**] をクリックします。

4.  [**ダイヤル プラン**] ページで、ダイヤル プラン名をダブルクリックします。
    
    <div>
    

    > [!NOTE]  
    > ダイヤル プランのスコープと名前は、ダイヤル プラン作成時に設定されています。これらは変更できません。

    
    </div>

5.  (オプション) [**ダイヤル プランの編集**] で [**簡単な名前**] フィールドを編集します。このフィールドには、ダイヤル プランを適用するサイト、サービス、またはユーザーを反映したよりわかりやすい名前を示す、[**名前**] フィールドの表示と同じ名前があらかじめ入力されています。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>簡易名</STRONG>は、Lync Server 2013 展開内のすべてのダイヤルプランの間で一意である必要があります。 英字、数字、ハイフン (-)、ピリオド (.)、正符号 (+)、またはアンダースコア (_) の Unicode 文字を 256 文字まで使用できます。<BR>スペースは [<STRONG>簡単な名前</STRONG>] フィールドでは使用できません。

    
    </div>

6.  (オプション) [**説明**] フィールドにダイヤル プランの説明情報を入力します。

7.  (オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、[**ダイヤルイン会議の地域**] を指定します。このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。
    
    <div>
    

    > [!NOTE]  
    > ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。

    
    </div>

8.  (オプション) ユーザーが外線に接続する際、先頭に 1 つまたは複数の数字 (9 など) を付けてダイヤルする必要がある場合のみ、[**外部アクセス プレフィックス**] フィールドに値を指定します。 最大4文字のプレフィックス値 ( \# \*、、、および 0-9) を入力できます。
    
    <div>
    

    > [!NOTE]  
    > 外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。

    
    </div>

9.  ダイヤル プランの正規化ルールを関連付けて構成します。
    
      - エンタープライズ Voip 展開で利用できるすべての正規化ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。 [**正規化ルールの選択**] ダイアログ ボックスで、ダイヤル プランに関連付けるルールを選択状態にして、[**OK**] をクリックします。
    
      - 新しい正規化ルールを定義してダイヤル プランに関連付けるには、[**新規**] をクリックします。 新しいルールの定義の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。
    
      - 既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして [**詳細の表示**] をクリックします。 ルールの編集の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。
    
      - 既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして [**コピー**] をクリックし、[**貼り付け**] をクリックします。 コピーの編集の詳細については、「 [Lync Server 2013 で正規化ルールを定義](lync-server-2013-defining-normalization-rules.md)する」を参照してください。
    
      - ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして [**削除**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。 ダイヤルプランで必要なすべての正規化ルールを決定する方法の詳細については、計画ドキュメントの「 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 でのダイヤルプランと正規化ルール</A>」を参照してください。

    
    </div>

10. ダイヤル プランの正規化ルールが、正しい順序で並んでいることを確認します。一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server は、[正規化ルール] リストを上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。 ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上になるように並び替えてください。<BR>既定では、<STRONG>すべて</STRONG>の正規化ルール<STRONG>^{11}(\d) $</STRONG>は11桁の数字と一致します。 たとえば、1425で始まる11桁の数字と一致する正規化ルールを追加する場合は、[<STRONG>すべて保持</STRONG>] が、より制限された<STRONG>^ (1425 \{7}d) $</STRONG>ルールの下に並べ替えられていることを確認してください。

    
    </div>

11. (オプション) ダイヤル プランをテストする番号を入力して、[**実行**] をクリックします。テスト結果が [**テストする番号の入力**] の下に表示されます。
    
    <div>
    

    > [!NOTE]  
    > まだテストに成功していないダイヤル プランを保存して、後で再構成することができます。 詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。

    
    </div>

12. [**OK**] をクリックします。

13. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ダイヤル プランを作成または変更したときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。 詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


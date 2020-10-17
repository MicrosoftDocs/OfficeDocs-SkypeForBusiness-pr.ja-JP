---
title: 'Lync Server 2013: 非公式の音声ルーティングテストの実行'
description: 'Lync Server 2013: 非公式の音声ルーティングテストを実行します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6029be34f4e4e7b366cb73f56ca611b4773331fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545033"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Lync Server 2013 での非公式の音声ルーティングテストの実行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-07_

[**音声ルーティング テスト ケース情報の作成**] ダイアログ ボックスを使用して、実際のテスト ケースを作成する前に非公式のテストを実行できます。 テスト結果に問題がなければ、それを公式のテスト ケースとして保存するオプションも用意されています。

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>非公式の音声ルーティング テストを実行するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ルーティングのテスト**] をクリックします。

4.  [**音声ルーティングのテスト**] ページで、[**音声ルーティング テスト ケース情報の作成**] をクリックします。

5.  [**ダイヤル番号**] フィールドに、このテストで使用する電話番号を入力します。 この番号は正規化され、[**結果**] ページの [**正規化番号**] フィールドに表示されます。

6.  [**ダイヤル プラン**] リストから、ダイヤル番号のテストで使用するダイヤル プランを選択します。 既定値はグローバル ダイヤル プランです。
    
    テストを実行すると、このダイヤル プランでダイヤル番号と一致する最初の正規化ルールが [**結果**] ウィンドウの [**正規化ルール**] フィールドに表示されます。

7.  [**音声ポリシー**] リストから、ダイヤル番号のテストで使用する音声ポリシーを選択します。 既定値はグローバル音声ポリシーです。
    
    テストを実行すると、この音声ポリシーで最初に一致する PSTN 使用法レコードが [**結果**] ウィンドウの [**最初の PSTN 使用法**] フィールドに表示されます。 また、この PSTN 使用法レコードに関連付けられており、最初に一致するボイス ルートが、[**最初のルート**] フィールドに表示されます。

8.  (オプション) 特定のユーザーに割り当てられた音声ポリシーに対してダイヤル番号をテストする場合は、[**ユーザーから値を入力**] チェック ボックスをオンにします。
    
    1.  [**参照**] をクリックして [**エンタープライズ VoIP ユーザーの選択**] ダイアログ ボックスを表示します。
    
    2.  [**検索**] をクリックして、エンタープライズ VoIP が有効なユーザーの一覧を表示します。
    
    3.  このテストで使用する音声ポリシーが割り当てられているユーザーの名前をダブルクリックします。 これにより、選択したユーザーに割り当てられている音声ポリシーが [**ポリシー**] フィールドに入力されます。
    
    テストを実行すると、この音声ポリシーで最初に一致する PSTN 使用法レコードが [**結果**] ウィンドウの [**最初の PSTN 使用法**] フィールドに表示されます。また、この PSTN 使用法レコードに関連付けられており、最初に一致するボイス ルートが、[**最初のルート**] フィールドに表示されます。

9.  [**実行**] をクリックしてテスト ケースを実行します。 結果はダイアログ ボックスの右パネルに表示されます。

10. (オプション) このテスト構成を公式のテスト ケースとして保存する場合は、[**名前を付けて保存**] をクリックします。
    
    1.  [**音声ルーティング テスト ケース情報の保存**] ダイアログ ボックスの [**名前**] フィールドに、テスト ケースの一意の名前を入力します。
        
        名前は、エンタープライズ VoIP 展開内のすべての音声ルーティング テスト ケースの中で一意である必要があります。 最大で32文字まで指定でき、円記号 ( \\ )、ピリオド (.)、またはアンダースコア () に加えて、英数字を含めることができ \_ ます。
    
    2.  [**音声ルーティング テスト ケース情報の保存**] ダイアログ ボックスにある残りのフィールドは読み取り専用です。値は、非公式のテスト構成*および*結果から事前に入力されます。 テスト ケースとして保存する構成で間違いないか確認してください。
        
        <div>
        

        > [!NOTE]  
        > テスト結果の値は、次に示すように、[<STRONG>音声ルーティング テスト ケース情報の保存</STRONG>] ダイアログ ボックスのフィールドに値を事前入力するために使用されます。 
        > <UL>
        > <LI>
        > <P>[<STRONG>予期される変換値</STRONG>] には、[<STRONG>正規化番号</STRONG>] フィールドの値が事前入力されます。</P>
        > <LI>
        > <P>[<STRONG>予期されるルート</STRONG>] には、[<STRONG>最初のルート</STRONG>] フィールドの値が事前入力されます。</P>
        > <LI>
        > <P>[<STRONG>予期される PSTN 使用法レコード</STRONG>] には、[<STRONG>最初の PSTN 使用法</STRONG>] フィールドの値が事前入力されます。</P></LI></UL>テストの実行中にこれらの値に一致する値が何も検出されなかった場合、[<STRONG>音声ルーティング テスト ケース情報の保存</STRONG>] ダイアログ ボックスの対応するフィールドは空になります。</div>
    
    3.  [**OK**] をクリックしてテスト ケースを保存するか、[**キャンセル**] をクリックして [**音声ルーティング テスト ケース情報の表示**] ダイアログ ボックスに戻り、保存する前にテストをさらに構成します。

11. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 音声ルーティング テスト ケースを作成するときにはいつでも、[<STRONG>すべて確定</STRONG>] コマンドを実行してテスト ケースを公開する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A> 」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングテストケースの作成](lync-server-2013-create-a-voice-routing-test-case.md)  
[Lync Server 2013 での音声ルーティングテストケースの実行](lync-server-2013-run-voice-routing-test-cases.md)  
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


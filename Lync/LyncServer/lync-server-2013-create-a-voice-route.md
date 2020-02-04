---
title: 'Lync Server 2013: ボイスルートを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a25f9d070c81d45ffc966be49560dc67c292c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Lync Server 2013 での音声ルートの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

次の手順では、Lync Server 2013 コントロールパネルを使用して、新しいボイスルートを作成する方法について説明します。 既存のルートを編集するには、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)(手順)」を参照してください。

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してボイスルートを作成するには

1.  RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**ルート**] をクリックします。

5.  [**新規**] をクリックして、[**新規音声ルート**] ダイアログ ボックスを表示します。

6.  [**名前**] に、音声ルートのわかりやすい名前を入力します。

7.  (オプション) [**説明**] に、音声ルートのわかりやすい追加情報を入力します。

8.  このルートが対応するパターンを指定するには、**照合するパターンの作成**ツールを使用して正規表現を生成するか、手動で正規表現を記述します。
    
      - **照合するパターンの作成**ツールを使用して正規表現を生成するには、次の値を入力します。次の 2 種類の照合パターンを指定できます。
        
          - **許可する数値の開始数字:** このルートに含める必要のあるプレフィックスの値を入力します (先頭の + が必要な場合)。 たとえば、「**+425**」と入力して、[**追加**] をクリックします。 このルートに含める各プレフィックス値について、この手順を繰り返します。
        
          - **例外:** プレフィックス値に1つまたは複数の例外を指定する場合は、プレフィックスを強調表示し、[**例外処理**] をクリックします。 このルートが*対応しない*照合パターンの値を 1 つまたは複数入力します。 たとえば、ルートから +425237 で始まる番号を除外するには、"**例外**" フィールドに「**+425237**」と入力して、[**OK**] をクリックします。
    
      - 照合パターンを手動で定義するには、**照合するパターンの作成**ツールの [**編集**] をクリックし、.NET Framework の正規表現を入力して、ルートが適用される相手電話番号の照合パターンを指定します。 正規表現の記述方法の詳細については、「」の「.NET [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)Framework の正規表現」を参照してください。

9.  通話を発信する電話の ID を呼び出し先に表示しない場合は、[**発信者番号を表示しない**] を選択します。このオプションを選択した場合、呼び出し先の発信者 ID 表示に表示される、[**代替発信者番号**] を指定する必要があります。

10. 1 つまたは複数のトランクを音声ルートに関連付けるには、[**追加**] をクリックして、一覧からトランクを選択します。
    
    <div>
    

    > [!NOTE]  
    > 展開に Microsoft Office Communications Server 2007 R2 仲介サーバーが含まれている場合は、それらも一覧で利用できます。

    
    </div>

11. 1つ以上の公衆交換電話網 (PSTN) の使用状況をボイスルートに関連付けるには、[**選択**] をクリックし、エンタープライズ voip 展開用に定義されている pstn 使用状況レコードのリストからレコードを選びます。
    
    <div>
    

    > [!NOTE]  
    > 利用可能な各 PSTN 使用状況レコードのプロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013 で pstn 使用状況レコードを表示</A>する」を参照してください。<BR>PSTN 使用状況レコードを作成または編集するには、「lync server <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">2013</A> <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">2013 でボイスポリシーを作成</A>する」および「pstn 使用状況レコードを構成する」を参照してください。

    
    </div>

12. 最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。
    
    <div>
    

    > [!NOTE]  
    > PSTN 利用状況レコードが表示される順序が重要である場合とは異なり、pstn 使用状況レコードがボイスルートに表示される順序は重要ではありません。 ただし、使用頻度を指定してリストを整理することをお勧めします。 たとえば、"RedmondLocal" RedmondLongDist、Redmondlocal、Redmondlocal。 (Lync Server は、一覧を上から下に移動します。)

    
    </div>

13. (オプション) "**テストする変換後の番号**" フィールドに値を入力して、[**実行**] をクリックします。テスト結果がフィールドの下に表示されます。
    
    <div>
    

    > [!NOTE]  
    > まだテストに合格しない音声ルートを保存し、後で再構成することができます。 詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。

    
    </div>

14. [**OK**] をクリックして音声ルートを保存します。

<div>


> [!IMPORTANT]  
> 音声ルートを作成したときは毎回、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)  
[Lync Server 2013 での PSTN 使用状況レコードの表示](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成する](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 音声ルートの作成'
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
ms.openlocfilehash: 37f62b6ba64456b8e892c94117750bf1bc209bc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Lync Server 2013 での音声ルートの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

次の手順では、Lync Server 2013 コントロールパネルを使用して、新しい音声ルートを作成する方法について説明します。 既存のルートを編集するには、手順について「 [Lync Server 2013 で音声ルートを変更](lync-server-2013-modify-a-voice-route.md)する」を参照してください。

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して音声ルートを作成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または**CsVoiceAdministrator**、 **csserveradministrator**、または**csadministrator**管理者役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックします。

4.  [**ルート**] をクリックします。

5.  [**新規**] をクリックして、[**新しい音声ルート**] ダイアログボックスを表示します。

6.  [**名前**] に、音声ルートのわかりやすい名前を入力します。

7.  オプション[**説明**] に、音声ルートのわかりやすい追加情報を入力します。

8.  このルートが対応するパターンを指定するには、[**一致パターンを作成**する] ツールを使用して正規表現を生成するか、手動で正規表現を記述します。
    
      - **一致パターン構築**ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。
        
          - **許可する番号の先頭の数字:** このルートが対応する必要があるプレフィックス値を入力します (必要に応じて、先頭に + を含めます)。 たとえば、「 **+ 425**」と入力し、[**追加**] をクリックします。 このルートに含める各プレフィックス値について、この手順を繰り返します。
        
          - **例外:** プレフィックス値に対して1つ以上の例外を指定する場合は、プレフィックスを強調表示して [**例外**] をクリックします。 このルートが対応*しない*一致パターンの値を 1 つまたは複数入力します。 たとえば、ルートから + 425237 で始まる番号を除外するには、[**例外**] フィールドに **+ 425237**の値を入力し、[ **OK**] をクリックします。
    
      - 一致パターンを手動で定義するには、**一致パターン構築**ツールの **[編集]** をクリックし、.NET Framework 正規表現を入力して、ルートが適用される相手電話番号の一致パターンを指定します。 正規表現の記述方法の詳細については、「」の「.NET [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)Framework の正規表現」を参照してください。

9.  通話を発信する電話の ID を呼び出し先に表示しない場合は、**[発信者 ID を表示しない]** を選択します。 このオプションを選択した場合、呼び出し先の発信者 ID 表示に表示される、**[代替発信者 ID]** を指定する必要があります。

10. 1つまたは複数のトランクを音声ルートに関連付けるには、[**追加**] をクリックして、一覧からトランクを選択します。
    
    <div>
    

    > [!NOTE]  
    > 展開に Microsoft Office Communications Server 2007 R2 仲介サーバーが含まれている場合は、それらも一覧で利用できます。

    
    </div>

11. 1つまたは複数の公衆交換電話網 (PSTN) の使用法を音声ルートに関連付けるには、[**選択**] をクリックして、エンタープライズ voip 展開に対して定義されている pstn 使用法レコードの一覧からレコードを選択します。
    
    <div>
    

    > [!NOTE]  
    > 使用可能な PSTN 使用法レコードの各プロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">VIEW pstn usage records In Lync Server 2013</A>」を参照してください。<BR>PSTN 使用法レコードを作成または編集するには、「 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">create a voice policy and CONFIGURE pstn usage records In Lync server 2013</A> 」または「 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy」および「configure pstn Usage Records in lync server 2013</A>」を参照してください。

    
    </div>

12. 最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。
    
    <div>
    

    > [!NOTE]  
    > PSTN 使用法レコードが表示される順序が重要である音声ポリシーとは対照的に、PSTN 使用法レコードが音声ルートに表示される順序は重要ではありません。 ただし、使用頻度でリストを整理することをお勧めします。 例: RedmondLocal、RedmondLongDist、Redmondlocal、Redmondlocal。 (Lync Server は、リストを上から下に移動します。)

    
    </div>

13. (オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。
    
    <div>
    

    > [!NOTE]  
    > まだテストに成功していないボイス ルートを保存して、後で再構成することができます。 詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。

    
    </div>

14. [ **OK]** をクリックして音声ルートを保存します。

<div>


> [!IMPORTANT]  
> 音声ルートを作成するたびに、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 の音声ルーティング構成に対する保留中の変更を公開する</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)  
[Lync Server 2013 での PSTN 使用法レコードの表示](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


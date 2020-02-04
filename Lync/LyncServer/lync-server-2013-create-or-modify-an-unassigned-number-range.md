---
title: 'Lync Server 2013: 未割り当ての番号範囲を作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Lync Server 2013 で、割り当てられていない番号範囲を作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

次のいずれかの手順を使用して、アナウンスメントアプリケーションの未割り当ての番号範囲を構成します。

<div>


> [!IMPORTANT]  
> [割り当てられていない番号] テーブルを構成する前に、1つ以上のアナウンスを既に定義しているか、Exchange ユニファイドメッセージング (UM) 自動応答をセットアップしている必要があります。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Lync Server コントロールパネルを使用して、割り当てられていない電話番号を設定するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。

4.  [**割り当てられていない番号**] ページで、次のいずれかの操作を行います。
    
      - 新しい番号範囲を作成するには、[**新規**] をクリックします。[**名前**] にこの番号範囲の識別名を入力します。
        
        <div>
        

        > [!NOTE]  
        > 割り当てられていない番号の新しい範囲をデータベースに送信した後は、この名前を変更することはできません。

        
        </div>
    
      - 既存の番号範囲を変更するには、番号範囲の名前または名前の一部を検索フィールドに入力します。結果の番号範囲の一覧で、対象の名前をクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5.  最初の [**数値の範囲**] フィールドに範囲の開始番号を入力し、2 番目の [**数値の範囲**] フィールドに範囲の終了番号を入力します。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>範囲の開始番号が終了番号より大きくならないようにしてください。</P>
    > <LI>
    > <P>範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</P>
    > <LI>
    > <P>数値は正規表現 (tel:) に一致する必要があります。 (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})? これは、数値が文字列 "tel" で始まる可能性があることを意味します (文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、1 ~ 9 桁の数字です。 電話番号は最大17桁で、その後に形式の内線番号、内線番号、内線番号が続く場合があります。</P></LI></UL>

    
    </div>

6.  [**アナウンス サービス**] で、次のいずれかの手順を実行します。
    
      - [**アナウンス**] をクリックします。
    
      - [**Exchange UM**] をクリックします。

7.  前の手順で [**アナウンス**] をクリックした場合は、次の手順を実行します。
    
    1.  [**宛先サーバーの FQDN**] で [**選択**] をクリックし、この範囲の未割り当て番号への着信通話を処理するアナウンスメントアプリケーションを実行するアプリケーションサービスのサービス ID をクリックして、[ **OK]** をクリックします。
    
    2.  [**アナウンス**] で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。

8.  前の手順で [**Exchange UM**] をクリックした場合は、[**自動応答の電話番号**] で、[**選択**] をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、[**OK**] をクリックします。

9.  [**OK**] をクリックします。

10. [**割り当てられていない番号**] ページで、割り当てられていない番号範囲が希望どおりの順序で並んでいることを確認します。表で範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックして、上矢印または下矢印をクリックします。
    
    <div>
    

    > [!TIP]  
    > Lync Server は、割り当てられていない番号テーブルを上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。 重複する範囲があり、そのうちの 1 つが最後のアクションを指定している場合は、その範囲が一覧の一番下にあることを確認します。

    
    </div>

11. 割り当てられていない番号範囲が希望どおりの順序で並んでいることを確認したら、[**すべて確定**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Windows PowerShell を使用して、割り当てられていない電話番号を構成するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  新しい割り当てられていない番号範囲を作成するには、**New-CsUnassignedNumber** を使用します。 既存の割り当てられていない番号範囲を変更するには、**Set-CsUnassignedNumber** を使用します。
    
    <div>
    

    > [!TIP]  
    > 重複する範囲があり、それらを特定の順序で適用する場合は、Priority パラメーターを含めます。最も優先度の高い範囲が通話に適用されます。

    
    </div>
    
    コマンド ラインで、次のいずれかを実行します。
    
      - アナウンス サービスの番号範囲を作成するには、次のコマンドレットを実行します。
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Exchange UM 自動応答の番号範囲を作成するには、次のコマンドレットを実行します。
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    例:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    または
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で、割り当てられていない番号範囲を削除する](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


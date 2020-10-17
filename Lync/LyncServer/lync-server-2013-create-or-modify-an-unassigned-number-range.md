---
title: 'Lync Server 2013: 割り当てられていない番号範囲を作成または変更する'
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
ms.openlocfilehash: 4409a0c5688d131b34c792230c992142dd4f9c51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514684"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Lync Server 2013 で割り当てられていない番号範囲を作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

アナウンスアプリケーションに割り当てられていない番号範囲を構成するには、次のいずれかの手順を使用します。

<div>


> [!IMPORTANT]  
> 割り当てられていない番号の表を構成する前に、既に1つ以上のアナウンスを定義しているか、Exchange ユニファイドメッセージング (UM) 自動応答を設定している必要があります。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Lync Server コントロールパネルを使用して割り当てられていない電話番号を構成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [ **音声機能**] をクリックし、[割り当てられていない **番号**] をクリックします。

4.  [割り当てられていない **番号** ] ページで、次のいずれかの操作を行います。
    
      - 新しい番号範囲を作成するには、[ **新規**] をクリックします。 [**名前**] に、この番号範囲の識別名を入力します。
        
        <div>
        

        > [!NOTE]  
        > 新しい割り当てられていない番号範囲をデータベースにコミットした後に、この名前を変更することはできません。

        
        </div>
    
      - 既存の番号範囲を変更するには、検索フィールドに番号範囲の名前の全体または一部を入力します。 結果の番号範囲の一覧で、必要な名前をクリックし、[ **編集**] をクリックして、[ **詳細の表示**] をクリックします。

5.  最初の **[数値の範囲]** フィールドに範囲の開始番号を入力し、2 番目の **[数値の範囲]** フィールドに範囲の終了番号を入力します。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>範囲の開始番号が終了番号より大きくならないようにしてください。</P>
    > <LI>
    > <P>範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</P>
    > <LI>
    > <P>数値は正規表現 (tel:)? () と一致する必要があり \+ ますか?[1-9] \d {0,17} (; ext = [1-9] \d {0,9} )?. これは、数値が文字列 tel: (文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、数字 1 ~ 9 で始まることを意味します。 電話番号は最大17桁にすることができ、その後に形式で内線番号を続け、内線番号を続けて指定することができます。</P></LI></UL>

    
    </div>

6.  **[アナウンス サービス]** で、次のいずれかの手順を実行します。
    
      - **[アナウンス]** をクリックします。
    
      - **[Exchange UM]** をクリックします。

7.  前の手順で **[アナウンス]** をクリックした場合は、次の手順を実行します。
    
    1.  **[宛先サーバーの FQDN]** で、**[選択]** をクリックし、この割り当てられていない番号範囲への着信通話を処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID をクリックし、**[OK]** をクリックします。
    
    2.  **[アナウンス]** で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。

8.  前の手順で **[Exchange UM]** をクリックした場合は、**[自動応答の電話番号]** で、**[選択]** をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、**[OK]** をクリックします。

9.  **[OK]** をクリックします。

10. [割り当てられていない **番号** ] ページで、割り当てられていない番号範囲が目的の順序で並んでいることを確認します。 表の範囲の位置を変更するには、範囲の一覧で1つ以上の連続する名前をクリックし、上矢印または下矢印をクリックします。
    
    <div>
    

    > [!TIP]  
    > Lync Server は、割り当てられていない番号の表を上から下へ検索し、割り当てられていない番号に一致する最初の範囲を使用します。 重複する範囲があり、1つの範囲が最後のリゾートアクションを指定している場合は、その範囲がリストの一番下にあることを確認してください。

    
    </div>

11. 割り当てられていない番号範囲が目的の順序で表示されている場合は、[ **すべて確定**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Windows PowerShell を使用して割り当てられていない電話番号を構成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  新しい未使用の番号範囲を作成するには **、remove-csunassignednumber** を使用します。 既存の割り当てられていない番号範囲を変更するには、 **remove-csunassignednumber** を使用します。
    
    <div>
    

    > [!TIP]  
    > 重複する範囲があり、範囲が特定の順序で適用されるようにする場合は、Priority パラメーターを含めます。 優先度の高い範囲が通話に適用されます。

    
    </div>
    
    コマンドラインで、次のいずれかの操作を行います。
    
      - アナウンスサービスの番号範囲を作成するには、次を実行します。
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - または、Exchange UM 自動応答の番号範囲を作成するには、次のように実行します。
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    次に例を示します。
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    または
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で割り当てられていない番号範囲を削除する](lync-server-2013-delete-an-unassigned-number-range.md)  


[Remove-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Remove-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Remove-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 割り当てられていない番号範囲の作成または変更'
TOCTitle: 割り当てられていない番号範囲の作成または変更
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48273026
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での割り当てられていない番号範囲の作成または変更

 

_**トピックの最終更新日:** 2012-11-01_

アナウンス アプリケーションの割り当てられていない番号範囲を構成するには、次のいずれかの手順を使用します。


> [!IMPORTANT]
> 割り当てられていない番号の表を構成する前に、アナウンスを 1 つ以上既に定義しているか、Exchange ユニファイド メッセージング (UM) の自動応答を設定する必要があります。



## Lync Server コントロール パネルを使用して割り当てられていない電話番号を構成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声機能**\] をクリックし、\[**割り当てられていない番号**\] をクリックします。

4.  \[**割り当てられていない番号**\] ページで、次のいずれかの操作を行います。
    
      - 新しい番号範囲を作成するには、\[**新規**\] をクリックします。\[**名前**\] にこの番号範囲の識別名を入力します。
        
        > [!NOTE]  
        > 割り当てられていない番号の新しい範囲をデータベースに送信した後は、この名前を変更することはできません。
    
      - 既存の番号範囲を変更するには、番号範囲の名前または名前の一部を検索フィールドに入力します。結果の番号範囲の一覧で、対象の名前をクリックして、\[**編集**\] をクリックし、\[**詳細の表示**\] をクリックします。

5.  最初の \[**数値の範囲**\] フィールドに範囲の開始番号を入力し、2 番目の \[**数値の範囲**\] フィールドに範囲の終了番号を入力します。
    
    > [!NOTE]  
    > <ul><li><p>範囲の開始番号が終了番号より大きくならないようにしてください。</p></li>
    > <li><p>範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</p></li>
    > <li><p>この番号は正規表現 (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})? に一致する必要があります。これは、番号が文字列 tel: で始まり (この文字列を指定しなかった場合は、自動的に追加されます)、正符号 (+)、1 ～ 9 の数字であることを意味します。使用できる電話番号は最大 17 桁で、その後に内線番号を付けることができます。内線番号は ;ext= の後に番号が続く形式です。</p></li></ul>


6.  \[**アナウンス サービス**\] で、次のいずれかの手順を実行します。
    
      - \[**アナウンス**\] をクリックします。
    
      - \[**Exchange UM**\] をクリックします。

7.  前の手順で \[**アナウンス**\] をクリックした場合は、次の手順を実行します。
    
    1.  \[**宛先サーバーの FQDN**\] で、\[**選択**\] をクリックし、この割り当てられていない番号範囲への着信通話を処理する アナウンス アプリケーションを実行するアプリケーション サービスのサービス ID をクリックし、\[**OK**\] をクリックします。
    
    2.  \[**アナウンス**\] で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。

8.  前の手順で \[**Exchange UM**\] をクリックした場合は、\[**自動応答の電話番号**\] で、\[**選択**\] をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、\[**OK**\] をクリックします。

9.  \[**OK**\] をクリックします。

10. \[**割り当てられていない番号**\] ページで、割り当てられていない番号範囲が希望通りの順序で並んでいることを確認します。表で範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックして、上矢印または下矢印をクリックします。
    

    > [!TIP]
    > Lync Server は、割り当てられていない番号の表を上から順に検索して、割り当てられていない番号に最初に一致する範囲を使用します。重複する範囲があり、そのうちの 1 つが最後のアクションを指定している場合は、その範囲が一覧の一番下にあることを確認します。



11. 割り当てられていない番号範囲が希望通りの順序で並んでいることを確認したら、\[**すべて確定**\] をクリックします。

## Windows PowerShellを使用して割り当てられていない電話番号を構成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  新しい割り当てられていない番号範囲を作成するには、 **New-CsUnassignedNumber** を使用します。既存の割り当てられていない番号範囲を変更するには、 **Set-CsUnassignedNumber** を使用します。
    

    > [!TIP]
    > 重複する範囲があり、それらを特定の順序で適用する場合は、Priority パラメーターを含めます。最も優先度の高い範囲が通話に適用されます。

    
    コマンド ラインで、次のいずれかを実行します。
    
      - アナウンス サービスの番号範囲を作成するには、次のコマンドレットを実行します。
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Exchange UM 自動応答の番号範囲を作成するには、次のコマンドレットを実行します。
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    次に例を示します。
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    または
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## 関連項目

#### タスク

[割り当てられていない番号の範囲の削除](lync-server-2013-delete-an-unassigned-number-range.md)  

#### その他のリソース

[New-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)


---
title: 'Lync Server 2013: コール パーク オービット範囲の作成または変更'
TOCTitle: コール パーク オービット範囲の作成または変更
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48272111
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのコール パーク オービット範囲の作成または変更

 

_**トピックの最終更新日:** 2012-11-01_

コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。

## Lync Server コントロール パネルを使用してコール パークの番号範囲を作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声機能**\] をクリックし、\[**コール パーク**\] をクリックします。

4.  \[**コール パーク**\] ページで、次のいずれかを実行します。
    
      - 新しいオービット範囲を作成するには、\[**新規作成**\] をクリックします。\[**名前**\] に、この番号範囲の識別名を入力します。
        
        > [!NOTE]  
        > オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。
    
      - 既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。

5.  最初の \[**番号範囲**\] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の \[**番号範囲**\] フィールドに、範囲の終了番号を入力します。
    
    > [!NOTE]  
    > <ul><li><p>範囲の開始番号が終了番号より大きくならないようにしてください。</p></li>
    > <li><p>範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</p></li>
    > <li><p>オービット範囲は一意である必要があります。 この範囲が他のどの範囲とも重ならないようにしてください。</p></li>
    > <li><p>オービット範囲が、文字 * または # で始まる場合、範囲は 100 を超える必要があります。</p></li>
    > <li><p>有効な値: 正規表現文字列 ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}) に一致する必要があります。つまり、値には * または # の文字あるいは 1 ～ 9 の数字で始まる文字列を指定する必要があります (最初の文字を 0 にすることはできません)。最初の文字が * または # である場合、次の文字には 1 ～ 9 の数字 (0 は不可) を指定します。この後には 0 ～ 9 の数字を最大 7 文字まで追加できます (&quot;#6000&quot;、&quot;*92000&quot;、&quot;*95551212&quot;、&quot;915551212&quot; など)。最初の文字が * または # ではない場合、最初の文字には 1 ～ 9 の数字 (0 は不可) を指定し、その後に 0 ～ 9 の数字を最大 8 文字まで指定します (&quot;915551212&quot;、&quot;41212&quot;、&quot;300&quot; など)。</p></li>
    > <li><p>プール当たりの合計が 50,000 オービットを超えないようにしてください。 各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。 たとえば、開始番号 &quot;7000000&quot;、終了番号 &quot;8000000&quot; を指定するのではなく、開始番号 &quot;7000000&quot;、終了番号 &quot;7000100&quot; を指定することを検討してください。</p></li></ul>


6.  \[**接続先サーバーの FQDN**\] で、コール パーク アプリケーションをホストするアプリケーション サービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。オービット範囲の開始番号と終了番号で指定された範囲内の番号にパークされる通話は、すべてこのサーバーまたはプールにルーティングされます。

7.  \[**確定**\] をクリックします。

## Windows PowerShellを使用してコール パークの番号範囲を作成または変更するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。
    
    コマンド ラインで、次のコマンドを実行します。
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    次に例を示します。
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    次の例は、既存のオービット範囲内の番号を変更する方法を示しています。
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

## 関連項目

#### タスク

[Lync Server 2013 でのコール パーク オービット範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### その他のリソース

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)


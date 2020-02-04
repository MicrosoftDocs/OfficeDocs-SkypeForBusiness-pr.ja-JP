---
title: 'Lync Server 2013: コールパークを作成または変更する範囲'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf215caacd0e380a14429bd2d34791048878fc96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>通話パークの作成または変更 Lync Server 2013 の範囲の軌道

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Lync Server コントロールパネルを使用して、パーキング通話の番号の範囲を作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。

4.  [**コール パーク**] ページで、次のいずれかを実行します。
    
      - 新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。
        
        <div>
        

        > [!NOTE]  
        > オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。

        
        </div>
    
      - 既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>範囲の開始番号が終了番号より大きくならないようにしてください。</P>
    > <LI>
    > <P>範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</P>
    > <LI>
    > <P>オービット範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</P>
    > <LI>
    > <P>オービット範囲が、文字 * または # で始まる場合、範囲は 100 を超える必要があります。</P>
    > <LI>
    > <P>有効な値: 正規表現の文字列と一致する\*必要があります ([| #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8}) つまり、値には * または # の文字あるいは 1 ～ 9 の数字で始まる文字列を指定する必要があります (最初の文字を 0 にすることはできません)。 最初の文字が * または # である場合、次の文字には 1 ～ 9 の数字 (0 は不可) を指定します。 後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば、"#6000"、"*92000"*、"95551212"、"915551212")。 最初の文字が * または # ではない場合、最初の文字には 1 ～ 9 の数字 (0 は不可) を指定し、その後に 0 ～ 9 の数字を最大 8 文字まで指定します ("915551212"、"41212"、"300" など)。</P>
    > <LI>
    > <P>プール当たりの合計が 50,000 オービットを超えないようにしてください。各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</P></LI></UL>

    
    </div>

6.  [**宛先サーバーの fqdn**] で、コールパークアプリケーションをホストするアプリケーションサービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。 オービット範囲の開始番号と終了番号で指定された範囲内の番号にパークされる通話は、すべてこのサーバーまたはプールにルーティングされます。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Windows PowerShell を使用してパーキング通話の数値の範囲を作成または変更するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。 オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。
    
    コマンド ラインで、次のコマンドを実行します。
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    例:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    次の例は、既存のオービット範囲内の番号を変更する方法を示しています。
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのコールパークの範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)  


[新規-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


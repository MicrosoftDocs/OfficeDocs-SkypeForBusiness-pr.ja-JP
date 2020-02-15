---
title: 'Lync Server 2013: コールパークオービット範囲の作成または変更'
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
ms.openlocfilehash: 9cd2e91ac2ae56d7ddffcaa8688ca305a6d377ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Lync Server 2013 でのコールパークオービット範囲の作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Lync Server コントロールパネルを使用して、保留呼び出しの番号範囲を作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

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
    > <P>オービット範囲は一意である必要があります。 この範囲が他のどの範囲とも重ならないようにしてください。</P>
    > <LI>
    > <P>オービット範囲が、文字 * または # で始まる場合、範囲は 100 を超える必要があります。</P>
    > <LI>
    > <P>有効な値: 正規表現文字列と一致する必要\*があります ([| #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8})。 つまり、値には * または # の文字あるいは 1 ～ 9 の数字で始まる文字列を指定する必要があります (最初の文字を 0 にすることはできません)。 最初の文字が * または # である場合、次の文字には 1 ～ 9 の数字 (0 は不可) を指定します。 後続の文字には、0から9までの任意の文字を追加できます (たとえば、"#6000"、"*92000"、*"95551212"、"915551212" など)。 最初の文字が * または # ではない場合、最初の文字には 1 ～ 9 の数字 (0 は不可) を指定し、その後に 0 ～ 9 の数字を最大 8 文字まで指定します ("915551212"、"41212"、"300" など)。</P>
    > <LI>
    > <P>プール当たりの合計が 50,000 オービットを超えないようにしてください。 各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。 たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</P></LI></UL>

    
    </div>

6.  **[宛先サーバーの FQDN]** で、コール パーク アプリケーションをホストするアプリケーション サービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。 オービット範囲の開始番号と終了番号で指定された範囲の番号にパークされるすべての通話は、このサーバーまたはプールにルーティングされます。

7.  **[確定]** をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Windows PowerShell を使用して、保留呼び出しの番号範囲を作成または変更するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。 オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。
    
    コマンド ラインで、次のコマンドを実行します。
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    次に例を示します。
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    次の例は、既存のオービット範囲内の番号を変更する方法を示しています。
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのコールパークオービット範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)  


[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 での Skype for Business クライアントの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 632eed40992bfcff53072d618313afe3501431be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configure the client experience with Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-09-17_

**概要:** このトピックでは、Lync Server 2013 環境での Skype for Business クライアントユーザー向けのクライアントエクスペリエンスを構成する方法について説明します。 クライアントエクスペリエンスを構成できるのは、2014年12月の累積更新プログラム (5.0.8308.857) 以降がインストールされている Lync Server 2013 を実行している場合のみです。 Lync Server 2013 の更新については、「 [Lync server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=532651)」を参照してください。

Skype for Business は、Skype コンシューマーの製品エクスペリエンスに基づいた新しいユーザーエクスペリエンスを提供します。 Skype for Business には、Lync のすべての機能に加えて、簡単なコントロールと使い慣れたアイコンが付いた新機能が用意されています。 新しいクライアントエクスペリエンスの詳細については、「 [Lync が Skype For business に変わりました。新機能」](http://go.microsoft.com/fwlink/?linkid=529022)を参照してください。

Lync Server 2013 では、新しい Skype for Business クライアントエクスペリエンスと Lync クライアントエクスペリエンスがサポートされています。 管理者は、ユーザー用に優先するクライアント エクスペリエンスを選択できます。 たとえば、新しい Skype for Business のエクスペリエンスで組織内のユーザーが完全にトレーニングを受けられるまで、Lync クライアントエクスペリエンスを展開することができます。 または、すべてのユーザーを Skype for Business Server 2015 にアップグレードしていない場合、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーが同じクライアントエクスペリエンスを使用できるようにする必要があります。

<div>


> [!IMPORTANT]  
> 組織に Skype for Business Server 2015 と Lync Server 2013 の両方が展開されている場合、既定のクライアントエクスペリエンスは、サーバーのバージョンと UI の設定によって異なります。 ユーザーが Skype for Business を初めて起動すると、Lync ユーザーインターフェイスを選んだ場合でも、常に Skype for business のユーザーインターフェイスが表示されます。 数分後に、ユーザーは Lync モードに切り替えるように求められます。 詳細については、このトピックの後半にある「<STRONG>最初の起動クライアントの動作</STRONG>」を参照してください。



</div>

<div>


> [!NOTE]  
> Lync 2013 クライアントエクスペリエンスは、Skype for Business 2016 クライアントバージョンでは使用できません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。



</div>

<div>

## <a name="configure-the-client-experience"></a>Configure the client experience

組織内のユーザーに表示されるクライアントエクスペリエンスを指定するには、EnableSkypeUI パラメーターを使用して、 **Set-CSClientPolicy**コマンドレットを使用します。 次のコマンドは、組織内のすべてのユーザーに対してグローバルポリシーの影響を受ける Skype for Business クライアントのエクスペリエンスを選択します (「サイトまたはユーザー固有のポリシーはグローバルポリシーを上書きします)」を選択します。

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

次のコマンドでは、組織内のすべてのユーザーに対して、グローバルポリシーの影響を受ける Lync クライアントエクスペリエンスが選択されます。

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

次のコマンドは、Redmond サイト内のすべてのユーザーに対して Skype for Business クライアントエクスペリエンスを選択します。

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

組織内の特定のユーザーに対してクライアントエクスペリエンスを構成する場合は、**新しい**ユーザーポリシーを作成して、**グラント clientpolicy**を使用して特定のユーザーにポリシーを割り当てることができます。コマンドレット.

たとえば、次のコマンドは、Skype for Business クライアントエクスペリエンスを選択する新しいクライアントポリシー、SalesClientUI を作成します。

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

次のコマンドを実行すると、Sales 部門のすべてのメンバーにポリシー SalesClientUI が割り当てられます。

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーが Skype for business を初めて起動したときに、以前に説明したように、EnableSkypeUI パラメーターの値を $False に設定して、Lync クライアントエクスペリエンスを選択した場合でも、Skype for Business のユーザーインターフェイスが表示されます。. 起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。

ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。

1.  前に説明した`EnableSkypeUI`ように使用しているポリシーで、の値が $False に設定されていることを確認します。

2.  ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。
    
    **\_\\\\\\\\\] [現在のユーザーのウイルスのウイルス] Microsoft Office Lync キーで、新しいバイナリ値を作成します。\_ \[** ****
    
    The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.
    
    キーは、以下のようになります。
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>ようこそ画面のチュートリアルの表示を制御する

ユーザーが Skype for Business クライアントを開くと、既定の動作では [ようこそ] 画面が表示されます。これには、*ほとんどのユーザーからの質問に対する7つのヒント*が含まれています。 You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:

[ウイルス**の\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\] Lync キー] で、新しい DWORD (32 ビット) 値を作成します。 \[** **** The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.

キーは、以下のようになります。

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>クライアント チュートリアルをオフにする

ユーザーがチュートリアルにアクセスできないようにするには、以下のレジストリ値を指定して、クライアント チュートリアルをオフにします。

[ウイルス**の\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\] Lync キー] で、新しい DWORD (32 ビット) 値を作成します。 \[** **** The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.

    "TutorialFeatureEnabled"=dword:00000000

You can turn the tutorial back on by setting the **Value data** to **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>既定のクライアントエクスペリエンス

組織に Skype for Business Server 2015 と Lync Server の両方が展開されている場合、クライアントのエクスペリエンスはサーバーのバージョンと Skype の UI の設定によって異なります。 以下の表に、サーバー バージョンと UI 設定に基づく最初のクライアント エクスペリエンスを示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>サーバー バージョン</p></th>
<th><p>EnableSkypeUI 設定</p></th>
<th><p>クライアント エクスペリエンス</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>既定</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</p></td>
<td><p>既定</p></td>
<td><p>ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</p></td>
<td><p>False</p></td>
<td><p>ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (パッチなし)</p></td>
<td><p>既定</p></td>
<td><p>ユーザーが Lync クライアントエクスペリエンスに切り替えるように求められた (ユーザーは後で Skype for Business に切り替えることができない)</p></td>
</tr>
</tbody>
</table>


次の表は、管理者が Skype UI エクスペリエンスの初期設定を変更したときのクライアントエクスペリエンスを示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>サーバー バージョン</p></th>
<th><p>Skype UI の設定</p></th>
<th><p>クライアント UI = Lync</p></th>
<th><p>クライアント UI = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype for Business に切り替えるように求められたユーザー</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>Lync UI への切り替えを求められたユーザー</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</p></td>
<td><p>True</p></td>
<td><p>Skype for Business に切り替えるように求められたユーザー</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>Lync UI への切り替えを求められたユーザー</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (パッチなし)</p></td>
<td><p>既定</p></td>
<td><p>Lync モード (Skype for Business に切り替えることはできません)</p></td>
<td><p>Lync UI (Skype for Business に切り替えることはできません)</p></td>
</tr>
</tbody>
</table>


Skype for Business クライアントの構成を管理するために必要な更新プログラムのバージョンは次のとおりです。

  - Lync Server 2010-Lync Server 2010 用の2015年2月の累積更新プログラム (4.0.7577.710)。 詳細については、「 [Lync Server 2010 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=532771)」を参照してください。

  - Lync Server 2013-Lync Server 2013 用に2014年12月の累積更新プログラム (5.0.8308.857)。 詳細については、「 [Lync Server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=532772)」を参照してください。

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューターのレジストリを変更するグループ ポリシー オブジェクトを作成する

ユーザーが初めて Skype for Business クライアントを起動したときに、Lync クライアント エクスペリエンスを表示するためのレジストリの更新は、1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。

以下の手順では、ユーザーが初めて Skype for Business を起動したときに、Lync クライアント エクスペリエンスが表示されるようにレジストリを変更する方法について説明します。 この手順を使って、前述のように [ようこそ] 画面のチュートリアルを無効にするために、レジストリを更新することもできます。

**GPO を作成するには**

1.  **グループ ポリシー管理コンソール**を起動します。
    
    グループ ポリシー管理コンソールの使い方については、「[グループ ポリシー管理コンソール](http://go.microsoft.com/fwlink/?linkid=532759)」を参照してください。

2.  [ **グループ ポリシー オブジェクト**] ノードを右クリックして、メニューから [ **新規作成**] を選びます。

3.  [**新しい GPO**] ダイアログで、GPO の名前 (「**MakeLyncDefaultUI**」など) を入力し、[**OK**] をクリックします。

4.  作成した新しい GPO を右クリックして、メニューから [**編集**] を選びます。

5.  [ **グループ ポリシー管理エディター**] で、[ **ユーザーの構成**]、[ **ユーザー設定**]、[ **Windows 設定**] の順に展開して、[ **レジストリ**] ノードを選びます。

6.  [ **Registry** ] ノードを右クリックし、[**新しい** \> **レジストリ項目**] を選びます。

7.  [**新しいレジストリのプロパティ**] ダイアログで、次の項目を更新します。
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>フィールド</th>
    <th>選択または入力する値</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>アクション</strong></p></td>
    <td><p><strong>作成</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ハイブ</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>キーのパス</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>値の名前</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>値の種類</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>値のデータ</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  [ **OK**] をクリックして変更を保存し、GPO を閉じます。

次に、ポリシーを割り当てる OU などのユーザー グループに、作成した GPO を接続する必要があります。

**GPO を使ってポリシーを割り当てるには**

1.  [グループ ポリシー管理コンソール] で、ポリシーを割り当てる OU を右クリックして、[ **既存の GPO にリンクする**] を選びます。

2.  [ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。

3.  ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。
    
    **gpupdate /target:user**
    
    GPO の適用中、"ポリシーを更新しています..." というメッセージが表示されます。 処理が完了すると、"ユーザー ポリシーの更新が正常に完了しました" というメッセージが表示されます。

4.  コマンド プロンプトに、以下のコマンドを入力します。
    
    **gpresult /r**
    
    "割り当て済みのグループ ポリシー オブジェクト" と表示され、その下に作成済みの GPO の名前が表示されます。

You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. レジストリエディターを開き、[ ** \[\_HKEY CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\] ** ] キーに移動します。 If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 で Skype for Business クライアントを構成する
description: Lync Server 2013 で Skype for Business クライアントを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f75ae0fa61d9048991934a0ecce7a886079961
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542973"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a>Skype for Business でクライアント環境を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-09-17_

**概要:** このトピックでは、Lync Server 2013 環境で Skype for Business クライアントユーザーのクライアント環境を構成する方法について説明します。 クライアント環境を構成するには、2013年 12 2014 月の累積的な更新プログラム (5.0.8308.857) 以降がインストールされている Lync Server を実行している必要があります。 Lync Server 2013 の更新については、「 [Lync server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=532651)」を参照してください。

Skype for Business では、Skype コンシューマー製品の使用状況に基づいて新しいユーザー環境が提供されます。 Lync のすべての機能に加えて、Skype for Business には、シンプルなコントロールと使い慣れたアイコンを備えた新しい機能が用意されています。 新しいクライアント環境の詳細については、「 [Lync が Skype For business で提供されるようになりました--新機能」を参照](https://go.microsoft.com/fwlink/?linkid=529022)してください。

Lync Server 2013 では、新しい Skype for Business クライアントの利便性と Lync クライアントの機能がサポートされています。 管理者は、ユーザーに対して推奨されるクライアント環境を選択できます。 たとえば、組織内のユーザーが新しい Skype for Business の経験で完全にトレーニングされるまで、Lync クライアント環境を展開することができます。 または、すべてのユーザーが Skype for Business Server 2015 にまだアップグレードされていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーが同じクライアントの機能を使用できるようにする必要があります。

<div>


> [!IMPORTANT]  
> 組織で Skype for Business Server 2015 と Lync Server 2013 の両方が展開されている場合、サーバーバージョンと UI 設定に応じて、既定のクライアント環境が異なります。 ユーザーが Skype for Business を初めて起動すると、Lync ユーザーインターフェイスが選択されている場合でも、Skype for business のユーザーインターフェイスは常に表示されます。 数分後、ユーザーに Lync モードに切り替えるかどうかを確認するメッセージが表示されます。 詳細については、このトピックで後述する「 <STRONG>最初の起動クライアントの動作</STRONG> 」を参照してください。



</div>

<div>


> [!NOTE]  
> Lync 2013 クライアントの機能は、Skype for Business 2016 クライアントバージョンのオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成しようとする前に、クライアントバージョンをチェックして、番号16で始まらないことを確認してください。例: x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>クライアント エクスペリエンスの構成

EnableSkypeUI パラメーターを指定したコマンドレットを使用すると **、組織** 内のユーザーに表示されるクライアントの操作を指定できます。 次のコマンドは、グローバルポリシーの影響を受ける組織内のすべてのユーザーに対して Skype for Business クライアントの機能を選択します (サイトまたはユーザー固有のポリシーはグローバルポリシーよりも優先されることに注意してください)。

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

次のコマンドは、グローバルポリシーの影響を受ける組織内のすべてのユーザーに対して Lync クライアント環境を選択します。

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

次のコマンドは、Redmond サイト内のすべてのユーザーに対して Skype for Business クライアント環境を選択します。

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

組織内の特定のユーザーに対してクライアント環境を構成する場合は、 **新しい-CsClientPolicy** コマンドレットを使用して新しいユーザーポリシーを作成し、そのポリシーを特定のユーザーに割り当てるには、 **Grant-csclientpolicy** コマンドレットを使用します。

たとえば、次のコマンドを実行すると、Skype for Business クライアントの動作を選択する新しいクライアントポリシーである SalesClientUI が作成されます。

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

次のコマンドは、policy (SalesClientUI) を Sales department のすべてのメンバーに割り当てます。

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>最初に起動するクライアントの動作

既定では、ユーザーが Skype for business を初めて起動したときに、以前に説明したように、EnableSkypeUI パラメーターの値を $False に設定して、Lync クライアント環境を選択した場合でも、Skype for business のユーザーインターフェイスが表示されます。 数分後、ユーザーは Lync モードに切り替えるかどうかを確認するメッセージが表示されます。

ユーザーが Skype for Business クライアントを初めて起動したときに、Lync ユーザーインターフェイスを表示する場合は、更新された後に初めてクライアントを起動する前に、次の手順を実行します。

1.  前述のように使用しているポリシーで、の値 `EnableSkypeUI` が $False に設定されていることを確認します。

2.  ユーザーのコンピューターのシステムレジストリを更新します。 この操作は、ユーザーが Skype for Business クライアントを初めて起動する前に行う必要があります。これは、一度だけ実行する必要があります。 ドメインに参加しているコンピューターのレジストリを更新するグループポリシーオブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。
    
    [ ** \[ 現在の \_ ユーザーソフトウェアの HKEY] \_ \\ \\ Microsoft \\ Office \\ \] Lync**キーで、新しい**バイナリ**値を作成します。
    
    **値の名前**は、 **Enableskypeui**で、**値のデータ**は**00 00 00 00**に設定する必要があります。
    
    キーは次のようになります。
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザーインターフェイスが表示されるようになります。

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>ようこそ画面のチュートリアルの表示を制御する

ユーザーが Skype for Business クライアントを開くと、既定の動作として、ようこそ画面が表示さ*れます。* ようこそ画面の表示をオフにしても、ユーザーがクライアントコンピューターに次のレジストリ値を追加して、チュートリアルにアクセスできるようにすることができます。

[ ** \[ 現在の \_ ユーザーソフトウェアの HKEY] \_ \\ \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **キーで、新しい**DWORD (32 ビット) の値**を作成します。 **値の名前**は**IsBasicTutorialSeenByUser**にする必要があり、**値のデータ**は**1**に設定する必要があります。

キーは次のようになります。

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>クライアントチュートリアルをオフにする

ユーザーがチュートリアルにアクセスできないようにするには、次のレジストリ値を使用してクライアントチュートリアルをオフにします。

[ ** \[ 現在の \_ ユーザーソフトウェアの HKEY] \_ \\ \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **キーで、新しい**DWORD (32 ビット) の値**を作成します。 **値の名前**は**TutorialFeatureEnabled**で、値の**データ**は**0**に設定する必要があります。

    "TutorialFeatureEnabled"=dword:00000000

[ **値のデータ** ] を **1**に設定することによって、チュートリアルをオンに戻すことができます。

</div>

</div>

<div>

## <a name="default-client-experiences"></a>既定のクライアントエクスペリエンス

組織で Skype for Business Server 2015 と Lync Server の両方が展開されている場合は、サーバーのバージョンと Skype UI の設定に応じて、クライアントの操作が異なります。 次の表に、サーバーバージョンと UI 設定に基づく最初のクライアント環境を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>サーバーのバージョン</p></th>
<th><p>EnableSkypeUI 設定</p></th>
<th><p>クライアント環境</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>既定値</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>正</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>ユーザーが Lync モードに切り替えることを求められた (UI 設定を $true に変更した場合、ユーザーは後で Skype for business に切り替えることができます)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</p></td>
<td><p>既定値</p></td>
<td><p>ユーザーが Lync モードに切り替えることを求められた (UI 設定を $true に変更した場合、ユーザーは後で Skype for business に切り替えることができます)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</p></td>
<td><p>正</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</p></td>
<td><p>False</p></td>
<td><p>ユーザーが Lync モードに切り替えることを求められた (UI 設定を $true に変更した場合、ユーザーは後で Skype for business に切り替えることができます)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (パッチなし)</p></td>
<td><p>既定値</p></td>
<td><p>ユーザーが Lync クライアント環境に切り替えることを求められた (ユーザーは後で Skype for Business に切り替えることができない)</p></td>
</tr>
</tbody>
</table>


次の表は、管理者が Skype UI 環境の初期設定を変更した場合のクライアントの動作を示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>サーバーのバージョン</p></th>
<th><p>Skype UI 設定</p></th>
<th><p>クライアント UI = Lync</p></th>
<th><p>クライアント UI = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>正</p></td>
<td><p>ユーザーが Skype for Business への切り替えを要求した</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>ユーザーが Lync UI への切り替えを要求した</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</p></td>
<td><p>正</p></td>
<td><p>ユーザーが Skype for Business への切り替えを要求した</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>ユーザーが Lync UI への切り替えを要求した</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 または Lync Server 2013 (パッチなし)</p></td>
<td><p>既定値</p></td>
<td><p>Lync モード (Skype for Business に切り替えることはできません)</p></td>
<td><p>Lync UI (Skype for Business に切り替えることはできません)</p></td>
</tr>
</tbody>
</table>


Skype for Business クライアントの構成を管理するために必要なパッチのバージョンは次のとおりです。

  - Lync Server 2010-Lync Server 2010 の累積的な更新プログラム (4.0.7577.710) (2 月 2015) 詳細については、「 [Lync Server 2010 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=532771)」を参照してください。

  - Lync Server 2013-Lync Server 2013 の累積的な更新プログラム (5.0.8308.857) (12 月 2014) 詳細については、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=532772)」を参照してください。

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューターのレジストリを変更するグループポリシーオブジェクトを作成する

ユーザーが初めて Skype for Business クライアントを起動したときに Lync クライアントの機能を表示するレジストリを更新するには、一度だけ実行する必要があります。 グループポリシーオブジェクト (GPO) を使用してレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO が適用されると、新しい値が存在しない場合、GPO によって作成され、値のデータが0に設定されます。

次の手順では、ユーザーが Skype for Business を初めて起動したときに Lync クライアントの機能が表示されるように、レジストリを変更する方法について説明します。 この手順を使用してレジストリを更新し、前に説明したようにようこそ画面のチュートリアルを無効にすることもできます。

**GPO を作成するには**

1.  **グループポリシー管理コンソール**を起動します。
    
    グループポリシー管理コンソールの使用方法については、「 [グループポリシー管理コンソール](https://go.microsoft.com/fwlink/?linkid=532759)」を参照してください。

2.  [ **グループポリシーオブジェクト** ] ノードを右クリックし、メニューの [ **新規** ] を選択します。

3.  [ **新しい gpo** ] ダイアログボックスで、「 **MakeLyncDefaultUI**」のように、gpo の名前を入力し、[ **OK**] をクリックします。

4.  作成したばかりの新しい GPO を右クリックして、メニューから [ **編集** ] を選択します。

5.  **グループポリシー管理エディター**で、[**ユーザーの構成**]、[**環境設定**]、[ **Windows の設定**] の順に展開し、[**レジストリ**] ノードを選択します。

6.  **レジストリ**ノードを右クリックし、[**新しい** \> **レジストリ項目**] を選択します。

7.  [ **新しいレジストリのプロパティ** ] ダイアログで、次の内容を更新します。
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Field</th>
    <th>選択または入力する値</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>操作</strong></p></td>
    <td><p><strong>Create</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ハイブ</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>キーパス</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>値の名前</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>値の型</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value data</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  [ **OK]** をクリックして変更を保存し、GPO を閉じます。

次に、ポリシーを割り当てるユーザーのグループ (OU など) に、作成した GPO をリンクする必要があります。

**GPO を使用してポリシーを割り当てるには**

1.  グループポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、[ **既存の GPO にリンクする**] を選択します。

2.  [ **Gpo の選択** ] ダイアログで、作成した gpo を選択し、[ **OK]** を選択します。

3.  ターゲットユーザーのコンピューターで、コマンドプロンプトを開き、次のコマンドを入力します。
    
    **gpupdate/target: user**
    
    "ポリシーの更新" というメッセージが表示されます。GPO が適用されている間に表示されます。 完了すると、"ユーザーポリシーの更新が正常に完了しました" というメッセージが表示されます。

4.  コマンド プロンプトで、以下のコマンドを入力します。
    
    **gpresult/r**
    
    [割り当てられたグループポリシーオブジェクト] と共に、作成した GPO の名前が表示されます。

レジストリを調べることによって、ユーザーのコンピューターのレジストリが GPO によって正常に更新されたことを確認することもできます。 レジストリエディターを開いて、[ ** \[ HKEY \_ CURRENT \_ USER \\ Software \\ ] \\ Microsoft \\ Office \] Lync**キーに移動します。 GPO によってレジストリが正常に更新された場合は、値が0の EnableSkypeUI という値が表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>


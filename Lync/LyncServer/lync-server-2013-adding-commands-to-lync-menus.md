---
title: 'Lync Server 2013: Lync メニューへのコマンドの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96a0df07a44392857f4384a1285245229874cdaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Lync Server 2013 での Lync メニューへのコマンドの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-04-11_

カスタムコマンドを Lync 2013 メニューに追加して、現在のユーザーの SIP URI (Uniform Resource Identifier) と選択した連絡先を、カスタムコマンドを開始するアプリケーションに渡すことができます。

追加するカスタム コマンドは、次の 1 つ以上のメニューに表示されます。

  - Lync のメイン ウィンドウのメニュー バー上にある、[ツール] メニュー

  - 連絡先リストの連絡先に対するショートカット メニュー

  - [会話] ウィンドウの [その他のオプション] メニュー

  - [会話] ウィンドウの参加者リストに表示された人に対するショートカット メニュー

  - 連絡先カードの [オプション] メニュー

2 種類のアプリケーション用のカスタム コマンドを定義することができ、そのアプリケーションは次のいずれかを行います。

  - 現在のユーザーのみに適用され、ローカル コンピューター上で起動するアプリケーション。

  - オンライン コラボレーション プログラムなどの別のユーザーが関与するアプリケーションであり、各ユーザーのコンピューター上で起動される必要があるアプリケーション。

カスタム コマンドは、次の方法で呼び出すことができます。

  - 1 人以上のユーザーを選択し、カスタム コマンドを選択します。

  - 2 パーティまたはマルチパーティの通話を開始し、カスタム コマンドを選択します。

<div>

## <a name="to-add-a-custom-command"></a>カスタム コマンドを追加するには

メニューにコマンドを追加するには、次の表のレジストリ設定を使用します。 これらのエントリは、次のいずれかの場所にあるレジストリに格納されます。

  - 32ビット OS の場合\_:\_HKEY\\ローカル\\コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ

  - 64ビット OS の場合\_:\_HKEY\\ローカル\\コンピューター\\ソフトウェア\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ

### <a name="custom-command-registry-entries"></a>カスタム コマンドのレジストリ エントリ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>種類</th>
<th>データ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>REG_SZ</p></td>
<td><p>メニューに表示されるアプリケーション名。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 実行可能 (既定値)</p>
<div>

> [!NOTE]  
> ApplicationInstallPath が必要。


</div>
<p>1 = プロトコル</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>実行可能ファイルの完全なパス。</p>
<div>

> [!NOTE]  
> ApplicationType が 0 (実行可能) の場合は指定が必要。


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>起動する完全なパスと、既定のパラメーターの <em>%user-id%</em> および <em>%contact-id%</em> を含むパラメーター。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</p>
<p>1 = 2 者間セッション (既定値)。 Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにデスクトップ通知を送信します。 相手のユーザーが通知をクリックすると、アプリケーションがそのコンピューター上で起動します。</p>
<p>2 = 複数ユーザー間セッション。 Lync 2013 は、アプリケーションをローカルで起動してから、デスクトップ通知を他のユーザーに送信します。 他のユーザーが通知をクリックすると、指定されたアプリケーションがコンピューター上で起動します。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>このコマンドが表示されるメニューの一覧は、セミコロンで区切られています。 有効な値は次のとおりです。</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>Conversationwindowactions [</p>
<p>Conversationwindowrightclick [</p>
<p>ContactCardMenu</p>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


たとえば、次のレジストリ エディター (.REG) ファイルは、[Contoso Sales Contact Manager] メニュー項目を [会話] ウィンドウの [操作] メニューに追加した結果を示しています。

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>カスタム コマンドにアクセスするには

カスタムコマンドにアクセスするには、定義した ExtensibleMenu の値に応じて、次のいずれかの操作を行います。

  - **Mainwindowactions**   Lync のメインウィンドウで、[**ツール**] をクリックし、カスタムコマンドをクリックします。

  - **Mainwindowrightclick**   Lync のメインウィンドウで、連絡先を右クリックし、カスタムコマンドをクリックします。

  - **Conversationwindowactions [**   [会話] ウィンドウで、[**その他のオプション**] アイコンをクリックし、カスタムコマンドをクリックします。

  - **Conversationwindowrightclick [**   [会話] ウィンドウで、連絡先の名前を右クリックし、カスタムコマンドをクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


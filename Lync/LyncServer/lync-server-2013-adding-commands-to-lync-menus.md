---
title: 'Lync Server 2013: Lync のメニューにコマンドを追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Lync Server 2013 での Lync メニューへのコマンドの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-04-11_

Lync 2013 メニューにカスタムコマンドを追加し、現在のユーザーの SIP Uniform リソース識別子 (URI) を、カスタムコマンドの開始時に選択した連絡先に渡すことができます。

追加するカスタムコマンドは、次の1つ以上のメニューに表示されます。

  - Lync メインウィンドウのメニューバーの [ツール] メニュー

  - 連絡先リストの連絡先のショートカットメニュー

  - [会話] ウィンドウの [その他のオプション] メニュー

  - [会話] ウィンドウの参加者リストに一覧表示されたユーザーのショートカットメニュー

  - 連絡先カードの [オプション] メニュー

2種類のアプリケーション (次のいずれかのアプリケーション) のカスタムコマンドを定義できます。

  - 現在のユーザーにのみ適用され、ローカルコンピューターで開始されます。

  - オンラインコラボレーションプログラムなどの追加のユーザーを参加させると、各ユーザーのコンピューターで開始する必要があります。

カスタムコマンドは、次の方法で呼び出すことができます。

  - 1人以上のユーザーを選択し、[ユーザー設定] コマンドを選択します。

  - 2パーティまたはマルチパーティの会話を開始し、[ユーザー設定] コマンドを選択します。

<div>

## <a name="to-add-a-custom-command"></a>カスタムコマンドを追加するには

次の表のレジストリ設定を使用して、メニューにコマンドを追加します。 これらのエントリは、レジストリの次のいずれかの場所に配置されます。

  - 32ビット OS の場合\_:\_HKEY\\ローカル\\コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ

  - 64ビット OS の場合\_:\_HKEY\\LOCAL\\MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ

### <a name="custom-command-registry-entries"></a>カスタムコマンドレジストリエントリ

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
<td><p>メニューに表示されるアプリケーションの名前。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 実行可能ファイル (既定)</p>
<div>

> [!NOTE]  
> ApplicationInstallPath が必要です。


</div>
<p>1 = プロトコル</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>実行可能ファイルの完全パス。</p>
<div>

> [!NOTE]  
> ApplicationType が 0 (実行可能ファイル) の場合は指定する必要があります。


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>既定のパラメーター <em>%、ユーザー id</em> %、<em>連絡先 id</em>% など、すべてのパラメーターと共に開始する完全パス。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ローカルセッション。 アプリケーションがローカルコンピューターで開始されます。</p>
<p>1 = 2 パーティセッション (既定)。 Lync 2013 では、アプリケーションをローカルで開始した後、他のユーザーにデスクトップ通知が送信されます。 他のユーザーが通知をクリックして、コンピューター上でアプリケーションを起動します。</p>
<p>2 = マルチパーティセッション。 Lync 2013 は、アプリケーションをローカルで開始してから、デスクトップ通知を他のユーザーに送信します。 他のユーザーが通知をクリックして、指定されたアプリケーションを自分のコンピューターで起動します。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>このコマンドが表示されるメニューの一覧。セミコロンで区切ります。 値の例は次のとおりです。</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick 上</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>連絡先カードメニュー</p>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick と ConversationWindowActions の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


たとえば、次のレジストリエディター (.REG) ファイルには、[会話] ウィンドウの [アクション] メニューに Contoso の営業連絡先マネージャーのメニュー項目を追加した結果が表示されます。

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

## <a name="to-access-a-custom-command"></a>カスタムコマンドにアクセスするには

追加したカスタムコマンドにアクセスするには、定義した ExtensibleMenu 値に応じて、次のいずれかの操作を行います。

  - **[メイン**   ウィンドウ] Lync メインウィンドウで [**ツール**] をクリックし、[ユーザー設定] コマンドをクリックします。

  - **[Mainwindowrightclick**   メインウィンドウで、連絡先を右クリックし、[ユーザー設定] をクリックします。

  - **ConversationWindowActions**   会話ウィンドウで、[**その他のオプション**] アイコンをクリックし、ユーザー設定のコマンドをクリックします。

  - **ConversationWindowRightClick**   会話ウィンドウで、連絡先の名前を右クリックし、[ユーザー設定] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


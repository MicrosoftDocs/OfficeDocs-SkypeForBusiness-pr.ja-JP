---
title: Lync メニューへのコマンドの追加
TOCTitle: Lync メニューへのコマンドの追加
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412788(v=OCS.15)
ms:contentKeyID: 52056665
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync メニューへのコマンドの追加

 

_**トピックの最終更新日:** 2016-04-11_

Lync 2013 のメニューにカスタム コマンドを追加し、現在のユーザーおよび選択した連絡先の SIP URI (Uniform Resource Identifier) を、カスタム コマンドが起動するアプリケーションに渡すことができます。

追加するカスタム コマンドは、次の 1 つ以上のメニューに表示されます。

  - Lync のメイン ウィンドウのメニュー バー上にある、\[ツール\] メニュー

  - 連絡先リストの連絡先に対するショートカット メニュー

  - \[会話\] ウィンドウの \[その他のオプション\] メニュー

  - \[会話\] ウィンドウの参加者リストに表示された人に対するショートカット メニュー

  - 連絡先カードの \[オプション\] メニュー

2 種類のアプリケーション用のカスタム コマンドを定義することができ、そのアプリケーションは次のいずれかを行います。

  - 現在のユーザーのみに適用され、ローカル コンピューター上で起動するアプリケーション。

  - オンライン コラボレーション プログラムなどの別のユーザーが関与するアプリケーションであり、各ユーザーのコンピューター上で起動される必要があるアプリケーション。

カスタム コマンドは、次の方法で呼び出すことができます。

  - 1 人以上のユーザーを選択し、カスタム コマンドを選択します。

  - 2 パーティまたはマルチパーティの通話を開始し、カスタム コマンドを選択します。

## カスタム コマンドを追加するには

次の表のレジストリ設定を使用して、メニューにコマンドを追加します。これらのエントリは、レジストリ内の次の場所にあります。

HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\CustomCommands

### カスタム コマンドのレジストリ エントリ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>タイプ</th>
<th>データ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>メニューに表示されるアプリケーション名。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 実行可能 (既定値)</p>

> [!NOTE]
> ApplicationInstallPath が必要。

</div>
<p>1 = プロトコル</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>実行可能ファイルの完全なパス。</p>

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
<p>1 = 2 者間セッション (既定値)。Lync 2013 は、アプリケーションをローカルで起動し、デスクトップ通知を他のユーザーに送信します。相手のユーザーが通知をクリックすると、アプリケーションがそのコンピューター上で起動します。</p>
<p>2 = 複数ユーザー間セッション。Lync 2013 は、アプリケーションをローカルで起動し、デスクトップ通知を他のユーザーに送信します。相手のユーザーが通知をクリックすると、指定されたアプリケーションがそのコンピューター上で起動します。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>(セミコロンで区切られた) このコマンドが表示されるメニューの一覧。有効な値は次のとおりです。</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


たとえば、次のレジストリ エディター (.REG) ファイルは、\[Contoso Sales Contact Manager\] メニュー項目を \[会話\] ウィンドウの \[操作\] メニューに追加した結果を示しています。

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\CustomCommands\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

## カスタム コマンドにアクセスするには

追加済みのカスタム コマンドにアクセスするには、定義する ExtensibleMenu の値に応じて、次のいずれかの操作を行います。

  - **MainWindowActions**   Lync のメイン ウィンドウで、\[**ツール**\] をクリックし、カスタム コマンドをクリックします。

  - **MainWindowRightClick**   Lync のメイン ウィンドウで、連絡先を右クリックし、カスタム コマンドをクリックします。

  - **ConversationWindowActions**   \[会話\] ウィンドウで、\[**その他のオプション**\] アイコンをクリックし、カスタム コマンドをクリックします。

  - **ConversationWindowRightClick**   \[会話\] ウィンドウで、連絡先名を右クリックし、カスタム コマンドをクリックします。

  - **ContactCardMenu**   ユーザーの連絡先カードで、\[オプション\] アイコンをクリックし、カスタム コマンドをクリックします。


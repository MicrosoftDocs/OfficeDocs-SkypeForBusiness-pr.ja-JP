---
title: サードパーティ製コラボレーション アプリケーションと Lync との統合
TOCTitle: サードパーティ製コラボレーション アプリケーションと Lync との統合
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398068(v=OCS.15)
ms:contentKeyID: 52056524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# サードパーティ製コラボレーション アプリケーションと Lync との統合

 

_**トピックの最終更新日:** 2015-03-09_

サードパーティのオンライン コラボレーション アプリケーションに関する情報をレジストリに追加することで、Lync 2013 をそのオンライン コラボレーション アプリケーションと統合できます。Lync 2013 を使用して、社内サーバー、インターネットベースのサービス、またはその両方でホストされるデータ会議セッションを開始できます。コラボレーションまたはデータ会議のセッションは、連絡先リストまたは既存のインスタント メッセージング、音声、またはビデオのセッションから開始できます。Lync 2013 は、アプリケーションを開始するための手段としてのみ動作します。オンライン コラボレーション セッションが開始された後も、既存の Lync 2013 の会話はアクティブなままです。

次のセクションでは、Lync 2013 をインターネットベースおよびサーバーベースのコラボレーション アプリケーションと統合する方法について説明します。

## インターネットベースのコラボレーション アプリケーションと Lync 2013 の統合

一般的に、サードパーティ製コラボレーション アプリケーションの統合手順は次のようになります。

1.  アプリケーションに関する情報がレジストリに追加されます。

2.  開催者が Lync 2013 にサインインし、データ共有およびコラボレーションの連絡先を選択します。または、開催者が既に会話に参加しており、データ会議の追加を決定する場合もあります。

3.  Lync 2013 はレジストリを読み込み、コラボレーション アプリケーションを起動して、カスタム SIP メッセージ (appINVITE) を選択した参加者に送信します。

4.  参加者が招待を承諾すると、コラボレーション アプリケーションが各自のコンピューター上で起動します。Lync 2013 は、レジストリを使用してどのコラボレーション アプリケーションを使用するかを決定し、appINVITE メッセージに含まれるパラメーターを使用してそのアプリケーションを起動します。

次の表に、インターネットベースのコラボレーション アプリケーションを Lync 2013 と統合する際に必要なレジストリ エントリを示します。これらのエントリは、次の場所のレジストリ内にあります。

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### インターネットベースのコラボレーション アプリケーションのレジストリ エントリ

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
<td><p>名前</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lync 2013 メニューのアプリケーション名。</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>16 ピクセル x 16 ピクセルのアイコン (BMP または PNG) へのパス。</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>オンライン コラボレーション アプリケーションを起動するための参加者のパス。</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>オンライン コラボレーション アプリケーションを起動するための開催者のパス。 このパスには、Parameters サブキーに定義されている、1 つ以上のカスタム パラメーターが含まれる場合があります。 たとえば、次のような場合です。<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</p>
<p>1 = 2 者間セッション (既定値)。Lync 2013 はアプリケーションをローカルで起動し、他のユーザーにシステム通知を送信します。相手のユーザーは通知をクリックし、指定されたアプリケーションを自分のコンピューター上で起動します。</p>
<p>2 = 複数ユーザー間セッション。Lync 2013 は、アプリケーションをローカルで起動し、システム通知を他のユーザーに送信します。この際、相手のユーザーに対して、指定されたアプリケーションを自分のコンピューター上で起動するように求めるメッセージが表示されます。</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>(セミコロンで区切られた) このコマンドが表示されるメニューの一覧。有効な値は次のとおりです。</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


次の表は、パラメーターのレジストリ エントリを示します。これらのエントリは、HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters にあります。

### インターネットベースのコラボレーション アプリケーションのレジストリ エントリ

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
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>OriginatorPath レジストリ キーにユーザー固有の値を追加するため、トークン化された形式 (<code>%Parm1%</code>) で使用される。</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Param1 を参照。</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Param1 を参照。</p></td>
</tr>
</tbody>
</table>


次の例のレジストリ設定では、ADatum Collaboration Client を Lync 2013 と統合します。

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

## サーバーベースのコラボレーション アプリケーションと Lync 2013 の統合

サーバーベースのコラボレーション アプリケーションを Lync 2013 内から起動するコマンドを追加するための設定は、前のセクションで説明した「インターネットベースのコラボレーション アプリケーションと Lync 2013 の統合」の設定と似ています。ただし、OriginatorPath は必要ではなく、いくつかの値が変更されます。レジストリ エントリは次の場所にあります。

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### サーバーベースのコラボレーション アプリケーションのレジストリ エントリ

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
<td><p>名前</p></td>
<td><p>REG_SZ</p></td>
<td><p>メニューに表示されるアプリケーション名。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>値 = 1 アプリケーションの種類をプロトコルに設定する。その他の値は、この場合には適用されません。値が指定されないと、ApplicationType は 0 (実行可能) に設定されます。</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>コラボレーション アプリケーションの起動に使用するプロトコル。Live Meeting 2007 では、Path の値が <code>meet:%conf-uri%</code> に設定されます。</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</p>
<p>1 = 2 者間セッション (既定値)。Lync 2013 はアプリケーションをローカルで起動し、他のユーザーにシステム通知を送信します。相手のユーザーは通知をクリックし、指定されたアプリケーションを自分のコンピューター上で起動します。</p>
<p>2 = 複数ユーザー間セッション。Lync 2013 は、アプリケーションをローカルで起動し、システム通知を他のユーザーに送信します。この際、相手のユーザーに対して、指定されたアプリケーションを自分のコンピューター上で起動するように求めるメッセージが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = サーバーの種類。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>(セミコロンで区切られた) このコマンドが表示されるメニューの一覧。有効な値は次のとおりです。</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


次の例では、Lync 2013 内から ADatum コラボレーション クライアントを起動するためのコマンドを追加します。

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"


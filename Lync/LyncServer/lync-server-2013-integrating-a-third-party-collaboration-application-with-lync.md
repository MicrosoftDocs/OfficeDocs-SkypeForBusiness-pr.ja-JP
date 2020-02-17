---
title: サードパーティ製のコラボレーションアプリケーションと Lync との統合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 075c8289a55683b18b0a006319b426c94796f9cd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>サードパーティ製コラボレーションアプリケーションと Lync Server 2013 の統合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

アプリケーションに関する情報をレジストリに追加することによって、Lync 2013 をサードパーティ製のオンライングループ作業アプリケーションと統合することができます。 Lync 2013 を使用すると、社内サーバー、インターネットベースのサービス、またはその両方でホストされているデータ会議セッションを開始できます。 コラボレーションまたはデータ会議のセッションは、連絡先リストまたは既存のインスタント メッセージング、音声、またはビデオのセッションから開始できます。 Lync 2013 は、アプリケーションを起動するための手段としてのみ機能します。 既存の Lync 2013 会話は、オンライングループ作業セッションが開始された後もアクティブなままとなります。

次のセクションでは、Lync 2013 をインターネットベースおよびサーバーベースのコラボレーションアプリケーションと統合する方法について説明します。

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>インターネットベースのコラボレーションアプリケーションと Lync 2013 の統合

一般的に、サードパーティ製コラボレーション アプリケーションの統合手順は次のようになります。

1.  アプリケーションに関する情報がレジストリに追加されます。

2.  開催者は Lync 2013 にサインインし、データ共有と共同作業のための連絡先を選択します。 または、開催者が既に会話に参加しており、データ会議の追加を決定する場合もあります。

3.  Lync 2013 は、レジストリを読み取り、グループ作業アプリケーションを起動し、カスタム SIP メッセージ (appINVITE) を選択された参加者に送信します。

4.  参加者が招待を承諾すると、コラボレーション アプリケーションが各自のコンピューター上で起動します。 Lync 2013 は、レジストリを使用して、どのグループ作業アプリケーションを使用するかを決定し、appINVITE メッセージに含まれるパラメーターを使用してそのアプリケーションを開始します。

次の表では、インターネットベースのコラボレーションアプリケーションを Lync 2013 に統合するために必要なレジストリエントリについて説明します。 これらのエントリは、レジストリの次の場所に配置されます。

  - HKEY\_ローカル\_コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーター

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>インターネットベースのコラボレーション アプリケーションのレジストリ エントリ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>型</th>
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
<td><p>原点のパス</p></td>
<td><p>REG_SZ</p></td>
<td><p>オンライングループ作業アプリケーションを開始するための開催者のパス。 このパスには、Parameters サブキーで定義されている1つ以上のカスタムパラメータを含めることができます。 たとえば、<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code> などです。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</p>
<p>1 = 2 者間セッション (既定値)。 Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信します。 相手のユーザーは通知をクリックし、指定されたアプリケーションを自分のコンピューター上で起動します。</p>
<p>2 = 複数ユーザー間セッション。 Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信して、自分のコンピューターで指定されたアプリケーションを起動するように指示します。</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>(セミコロンで区切られた) このコマンドが表示されるメニューの一覧。有効な値は次のとおりです。</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>Conversationwindowactions [</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>Conversationwindowrightclick [</p></li>
</ul>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


次の表は、パラメーターのレジストリ エントリを示します。 これらのエントリは、HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーターに配置されます。

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>インターネットベースのコラボレーション アプリケーションのレジストリ エントリ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>型</th>
<th>データ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>トークン化された<code>%Parm1%</code>形式 () で使用され、ユーザー固有の値を原点の atorpath レジストリキーに追加します。</p></td>
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


次のレジストリ設定の例では、ADatum コラボレーションクライアントと Lync 2013 を統合しています。

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

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>サーバーベースのコラボレーションアプリケーションと Lync 2013 の統合

Lync 2013 のサーバーベースのコラボレーションアプリケーションを起動するためのコマンドを追加するための設定は、前のセクションで説明したものと似ています。これは、インターネットベースのコラボレーションアプリケーションと Lync 2013 との統合です。 ただし、OriginatorPath は必要ではなく、いくつかの値が変更されます。 レジストリエントリは次の場所に配置されます。

  - HKEY\_ローカル\_コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーター

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>サーバーベースのコラボレーション アプリケーションのレジストリ エントリ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>型</th>
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
<td><p>値は 1 です。 アプリケーションの種類を protocol に設定します。 その他の値は、この場合には適用されません。 存在しない場合、ApplicationType は 0 (実行可能) に設定されます。</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>コラボレーション アプリケーションの起動に使用するプロトコル。 Live Meeting 2007 の場合、Path の値はに<code>meet:%conf-uri%</code>設定されます。</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</p>
<p>1 = 2 者間セッション (既定値)。 Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信します。 相手のユーザーは通知をクリックし、指定されたアプリケーションを自分のコンピューター上で起動します。</p>
<p>2 = 複数ユーザー間セッション。 Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信して、コンピューターで指定されたアプリケーションを起動するように指示します。</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = サーバーの種類。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>このコマンドが表示されるメニューの一覧は、セミコロンで区切られています。 有効な値は次のとおりです。</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>Conversationwindowactions [</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>Conversationwindowrightclick [</p></li>
</ul>
<p>ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</p></td>
</tr>
</tbody>
</table>


次の例では、Lync 2013 内から ADatum コラボレーションクライアントを開始するコマンドを追加します。

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

</div>

</div>

<span> </span>

</div>

</div>

</div>


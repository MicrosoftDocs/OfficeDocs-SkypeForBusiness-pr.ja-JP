---
title: 'Lync Server 2013: アドレス帳サービスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a5f7a6a30e510bdcdb57d9f8a2f5a15fe8a7f37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521194"
---
# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳サービスの管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

Lync Server Enterprise Edition または Standard Edition サーバーの展開の一環として、アドレス帳サービスは既定でインストールされます。 アドレス帳サービスによって使用されるデータベース (RTCab) は、SQL Server 上に作成されます (Enterprise Edition の場合は、バックエンドの SQL Server、SQL Server の場合は、SQL Server の場合は、SQL Server が併置されています)。

<div>


> [!NOTE]  
> <STRONG>Adsi edit</STRONG>を使用して Active Directory ドメインサービスオブジェクトの属性を編集する方法については、「 <A href="https://go.microsoft.com/fwlink/?linkid=330427">adsi edit</A>」を参照してください。 特にアドレス帳サービス用のリソースキットのツールの詳細については、「 <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 リソースキットツール</A>」を参照してください。



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>アドレス帳サーバーの電話番号正規化

Lync Server には、標準化された RFC 3966/e.164 電話番号が必要です。 構造化されていない、または一貫性のない形式の電話番号を使用する場合、Lync Server はアドレス帳サーバーに依存して、正規化ルールに渡される前に電話番号の事前処理を行います。 アドレス帳から電話番号を使用し、正規化ルールを適用すると、Lync Phone Edition や Lync Mobile などのクライアントは、これらの正規化された数値を使用できます。

以前のバージョンで使用されていた正規化ルールは、いくつかの調整を行わなければ適切に動作しない場合があります。空白文字や不要な文字は正規化ルールの前に削除されるため、特にダッシュや削除された文字を正規表現で検索している場合、正規化ルールがエラーになることがあります。こういった不要な文字を検索していないことと、ルールの想定の場所に文字が存在しない場合にルールが問題なくエラーになって続行するよう、正規化ルールを確認する必要があります。

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>ユーザー レプリケーターとアドレス帳サーバー

アドレス帳サーバーは、ユーザー レプリケーターが提供するデータを使用して、グローバル アドレス一覧 (GAL) から最初に取得する情報を更新します。 ユーザーレプリケーターは、各ユーザー、連絡先、およびグループの Active Directory ドメインサービスの属性をデータベースの AbUserEntry テーブルに書き込み、アドレス帳サーバーは、データベースのユーザーデータをアドレス帳サーバーのファイルストア内のファイルに、アドレス帳データベースの RTCab に同期します。 AbUserEntry テーブルのスキーマは、**UserGuid** および **UserData** の 2 つの列を使用します。 **Userguid** はインデックス列で、Active Directory オブジェクトの16バイトの GUID を含みます。 **UserData** は、その連絡先に対して前述した Active Directory ドメインサービスのすべての属性を含む image 列です。

ユーザーレプリケーターは、AbUserEntry テーブルと同じ SQL Server ベースのインスタンスにある構成テーブルを読み取ることによって、どの Active Directory 属性を書き込むかを決定します。 AbAttribute テーブルには、**ID**、**名前**、**フラグ**、**有効** の 4 つの列があります。 このテーブルはデータベースのセットアップ中に作成されます。 AbAttribute テーブルが空の場合、ユーザー レプリケーターはその AbUserEntry テーブル処理ロジックをスキップします。 アドレス帳サーバーの属性は動的で、AbAttribute テーブルから取得され、アドレス帳サーバーがアクティブ化される際、アドレス帳サーバーによって最初に書き込まれます。

アドレス帳サーバーのアクティブ化は、AbAttribute テーブルに、次の表に示す値を設定します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>名前</th>
<th>フラグ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-d</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>pbm-2</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>1/3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>タイトル</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10  </p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>#</p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12 </p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13 </p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>メール</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>部門</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>説明</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>年</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>1280</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


**ID** 列の数字は一意である必要があり、再利用は一切できません。 また、ID の値を 256 未満に保つことで、アドレス帳サーバーにより書き込まれる出力ファイルの領域を確保します。 しかし、最大 ID 値は 65535 です。 **Name**列は、ユーザーレプリケーターが連絡先ごとに AbUserEntry テーブルに格納する Active Directory 属性の名前に対応しています。 **フラグ**列の値は、属性の種類の定義に使用されます。 次の種類のアドレス帳サーバー属性はユーザー レプリケーターにより認識され、**フラグ**列の値の低バイト数で示されます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>文字列属性です。 ユーザー レプリケーターは、AbUserEntry テーブルに格納する前に、この型を UTF-8 文字列に変換します。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>バイナリ属性です。 ユーザー レプリケーターは、これを変換することなく BLOB に格納します</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>文字列属性ですが、属性値が tel: から始まる場合にのみ含まれ &quot; &quot; ます。 これは、主に複数値の文字列属性 (具体的には <strong>proxyAddresses</strong>です。 この場合、アドレス帳サーバーは、tel: から始まる <strong>proxyAddresses</strong> エントリのみに注目し &quot; &quot; ます。 そのため、領域を節約するために、ユーザーレプリケーターには、tel: から始まるエントリのみが格納され &quot; &quot; ます。</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>ブール値の文字列属性です。TRUE の場合、ユーザー レプリケーターはこの連絡先を AbUserEntry テーブルに含めません。 FALSE の場合、ユーザー レプリケーターはこの連絡先の属性を AbUserEntry テーブルに含めますが、このフラグを持つ特定の属性は含めません。 これは、主に <strong>msExchHideFromAddressLists</strong> 属性用である、もう 1 つの特例の型です。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>文字列属性。ただし、属性値が smtp で始まる場合にのみ含まれます。この &quot; &quot; 記号が含まれてい &quot; @ &quot; ます。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>文字列属性。ただし、属性値が &quot; tel: &quot; または smtp: で始まる場合にのみ含まれ、 &quot; &quot; 記号を含み &quot; @ &quot; ます。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>設定されている場合、これは各連絡先で複数回出現可能な複数値の属性です。</p></td>
</tr>
<tr class="even">
<td><p>解像度</p></td>
<td><p>設定されている場合、これは連絡先の電子メール ユーザー アカウント名の属性を示します。 アドレス帳サーバーはこのフラグを使用して、電話正規化イベント ログのエントリに表示する属性値を特定します。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>設定されている場合、これは連絡先の必須属性を示します。 アドレス帳サーバーは、Active Directory にこの属性の値がある場合のみ、ユーザーを AbUserEntry テーブルに含めます。 必須属性が複数ある場合、ユーザーを AbUserEntry テーブルに含めるには、その中の 1 つのみに値があることが必要です。</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>設定されている場合、アドレス帳サーバーはこの属性の値を常に正規化します。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>設定されている場合、アドレス帳サーバーは <strong>UseNormalizationRules</strong> CMS 設定が FALSE の場合は <strong>proxyAddresses</strong> からの正規化された番号を使用し、それ以外の場合はフラグ ビットが 0x1000 のときと同じように動作します。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>設定されている場合、アドレス帳サーバーは、指定された属性にこの値を持つオブジェクトを AbUserEntry テーブルに含めません。 たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> 属性がこのフラグ ビット セットを持つ場合、この属性を持つ連絡先はデータベースに書き込まれません。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>設定されている場合、アドレス帳サーバーは、指定された属性にこの値を持たないオブジェクトを AbUserEntry テーブルに含めません。 0x4000 と 0x8000 の両方のフラグ ビットがオブジェクトに対して設定されている場合は、0x4000 に設定されたフラグ ビット値を持つ属性が優先され、オブジェクトは AbUserEntry テーブルから除外されます。</p></td>
</tr>
<tr class="even">
<td><p>「その他」</p></td>
<td><p>設定されている場合、これはグループ オブジェクトを表します。 ユーザー レプリケーターはこのフラグ ビットを使用して、その存在がグループを示す<strong>groupType</strong> 属性を持つ連絡先を含めます (例: 配布リストまたはセキュリティ グループ)。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>設定されている場合、ユーザー レプリケーターはこのフラグ ビットを使用して、デバイス固有のアドレス帳サーバー ファイル (つまり、.dabs の拡張子を持つファイル) にこの属性を含めます。</p></td>
</tr>
</tbody>
</table>


以前のバージョンの Lync Server では、Active Directory への変更を適用する際に、管理者は、 **Update-csaddressbook** Windows PowerShell コマンドレット**を実行して、** lync Server ユーザーデータベースおよび rtcab データベースへの変更を直ちに保持する必要があります。 Lync Server 2013 の Lync Server ユーザーレプリケーターは、Active Directory から変更を取得し、構成された間隔に基づいて Lync Server ユーザーデータベースを更新します。 Lync Server ユーザーレプリケーターでは、管理者が Update-csaddressbook を実行しなくても、変更内容が RTCab データベースに迅速に伝達されます。 アドレス帳 Web クエリが有効になっている場合、変更は Lync クライアントによって検索結果に反映されます。 アドレス帳ファイルのダウンロードが有効になっている場合にのみ、管理者は Update-csaddressbook を実行する必要があります。

<div>


> [!NOTE]  
> 既定では、Lync Server ユーザーレプリケーターは5分ごとに自動的に実行されます。 この間隔は、ReplicationCycleInterval を使用して構成でき &lt; &gt; ます。



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>アドレス帳のフィルター処理

アドレス帳サーバーファイルで設定されたユーザーは、AbAttribute テーブルにリストされている特定の Active Directory ドメインサービス属性に基づいて制御できます。 そのようなフィルター処理に使用される属性の 1 つは、**msExchangeHideFromAddressBook** 属性です。 これは、Exchange スキーマによって追加されるユーザー属性です。 この属性の値が TRUE に設定されている場合、Exchange Server はこの属性を使用し、Outlook のグローバル アドレス一覧 (GAL) で連絡先を非表示にします。 同様に、この属性の値が TRUE の場合、ユーザー レプリケーターはそのユーザーを AbUserEntry テーブルに含めず、このユーザーはアドレス帳サーバー ファイルに存在しなくなります。

一部のフラグ ビットを使用して、アドレス帳サーバー属性に対して使用するフィルターを定義できます。 たとえば、特定のフラグ ビットがあることにより、ある属性を include 属性か exclude 属性として指定できます。 ユーザー レプリケーターは、exclude 属性を含む連絡先を除外したり、include 属性を含まない連絡先を除外したりします。

<div>


> [!WARNING]  
> アドレス帳のフィルター処理の詳細については、「 <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync server 2013 のアドレス帳サーバーのコマンドレット</A>」および「 <A href="https://go.microsoft.com/fwlink/?linkid=330430">lync 2013 アドレス帳のフィルター処理</A>」を参照してください。



</div>

現在は 3 種類のフィルターがあります。 次の表にこれら 3 つのフィルターの一覧を示します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>設定されている場合、これは連絡先の必須属性を示します。 ユーザー レプリケーターはこのフラグ ビットを使用し、必須属性を少なくとも 1 つ含んでいない連絡先を除外します。 OuPathId は必須属性で、必ず設定されます。 そのため、その他の必須属性が少なくとも 1 つ設定される必要があります。 それ以外の場合、(つまり、必須属性 OuPathId の値を持つ) 連絡先は、データベースにまだ書き込まれません。 たとえば、<strong>telephoneNumber</strong> と <strong>homePhone</strong> が必須の属性として定義されている場合、これらの属性のうち少なくとも 1 つを持つ連絡先のみがデータベースに書き込まれます。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>設定されている場合、exclude 属性を示します。 ユーザー レプリケーターはこのフラグ ビットを使用し、この属性を含む連絡先を除外します。 たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> が exclude 属性として定義されている場合、この属性を持つ連絡先はデータベースに書き込まれません。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>設定されている場合、これは include 属性を示します。 ユーザー レプリケーターはこのフラグ ビットを使用し、この属性を含まない連絡先を除外します。 たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> が include 属性として定義されている場合、この属性を持つ連絡先のみがデータベースに書き込まれます。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 0x4000 (exclude 属性) と 0x8000 (include 属性) の両方のフラグ ビットが設定されている場合、0x4000 ビットが 0x8000 ビットより優先され、連絡先は除外されます。



</div>

アドレス帳をフィルターして特定のユーザーのみを含めることができますが、エントリを制限すると、他のユーザーがフィルターされたユーザーへ連絡したり、プレゼンス状態を参照したりできる範囲が制限されます。ユーザーは、ユーザーの完全なサインイン名を入力することで、アドレス帳にないユーザーに対する検索、インスタント メッセージの手動送信、手動での通話の開始をいつでも実行できます。また、ユーザーの連絡先情報は、Outlook でも検索できます。

アドレス帳ファイルに連絡先レコードを完全に格納すると、セッション開始プロトコル (SIP) 用に構成されていないユーザーとの間で Lync Server を使用して電子メール、電話、またはエンタープライズの音声通話 (サーバーでエンタープライズ Voip が有効になっている場合) を開始することができます。 次の必須属性 ( **mailNickname**、 **telephoneNumber**、 **homePhone**、および**mobile**) の**Flags**列で0X800 ビットをクリアすることによって、アドレス帳にフィルターを適用して、SIP が有効なユーザーのみを含めることができます。 **MsRTCSIP-PrimaryUserAddress**属性の**Flags**列に 0x8000 (include 属性) を設定して、SIP が有効なユーザーのみを含めるようにアドレス帳にフィルターを適用することもできます。 これにより、アドレス帳ファイルからサービスアカウントを除外することもできます。

AbAttribute テーブルを変更した後、コマンドレット **Update-CsUserDatabase** のコマンドを実行し、AbUserEntry テーブルのデータを更新できます。 UR のレプリケーションが完了した後、コマンドレット **UpdateCsAddressBook** のコマンドを手動で実行し、アドレス帳サーバー ファイル ストアのファイルを更新できます。

<div>


> [!NOTE]  
> アドレス帳サーバーが配置されているフロントエンドサーバーは、管理上構成することはできません。 展開時に1つが選択されます (通常は最初のフロントエンドサーバーが展開されます)。 障害が発生した場合、アドレス帳サービスは別のフロントエンドサーバーに移動し、管理上の注意を必要としません。



</div>

<div>


> [!IMPORTANT]  
> 複数フォレスト展開または親子展開 (インフラストラクチャの統合など) からインフラストラクチャを統合または変更している場合は、一部のユーザーについてアドレス帳サービスのダウンロードとアドレス帳 Web クエリが失敗することがあります。 複数のドメインやフォレストがある展開内では、問題の発生しているユーザー オブジェクトに属性 <STRONG>MsRTCSIP-OriginatorSid</STRONG> が追加されます。 問題を解決するには、これらのオブジェクトの <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性を NULL に設定する必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


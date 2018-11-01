---
title: アドレス帳サービスの管理
TOCTitle: アドレス帳サービスの管理
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48272673
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳サービスの管理

 

_**トピックの最終更新日:** 2016-12-08_

アドレス帳サービスは、Lync ServerEnterprise Edition または Standard Edition サーバーの展開の一環として、既定でインストールされます。アドレス帳サービスで使用するデータベース (RTCab) は SQL Server (Enterprise Edition の場合はバックエンドの SQL Server、Standard Edition サーバーの場合は併置されている SQL Server) 上に作成されます。

> [!NOTE]
> <strong>ADSI エディター</strong> を使用した Active Directory ドメイン サービスのオブジェクト属性の編集について詳しくは、「<a href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI エディター</a>」をご覧ください。アドレス帳サービス専用のリソース キット ツールについて詳しくは、「<a href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 リソース キット ツール (Microsoft Lync Server 2013 Resource Kit Tools)</a>」をご覧ください。


## アドレス帳サーバーの電話番号正規化

Lync Server では、標準の RFC 3966/E.164 電話番号が必要です。体系に沿っていない形式や一貫性のない形式の電話番号を使用するには、Lync Server では、アドレス帳サーバーを利用して電話番号を前処理してから正規化ルールに渡します。アドレス帳から電話番号が使用され、正規化ルールが適用されると、クライアント (Lync Phone Edition や Lync Mobile など) で、これらの正規化された番号を使用できます。

以前のバージョンで使用されていた正規化ルールは、いくつかの調整を行わなければ適切に動作しない場合があります。空白文字や不要な文字は正規化ルールの前に削除されるため、特にダッシュや削除された文字を正規表現で検索している場合、正規化ルールがエラーになることがあります。こういった不要な文字を検索していないことと、ルールの想定の場所に文字が存在しない場合にルールが問題なくエラーになって続行するよう、正規化ルールを確認する必要があります。

## ユーザー レプリケーターとアドレス帳サーバー

アドレス帳サーバーは、ユーザー レプリケーターが提供するデータを使用して、グローバル アドレス一覧 (GAL) から最初に取得する情報を更新します。ユーザー レプリケーターは、各ユーザー、連絡先、およびグループの Active Directory ドメイン サービス 属性をデータベース内の AbUserEntry テーブルに書き込み、アドレス帳サーバーはデータベースのユーザー データを、アドレス帳サーバーのファイル ストア内のファイルと、アドレス帳データベース RTCab に同期します。AbUserEntry テーブルのスキーマは、**UserGuid** および **UserData** の 2 つの列を使用します。**UserGuid** はインデックス列で、Active Directory オブジェクトの 16 バイトの GUID を格納します。**UserData** はイメージ列で、その連絡先の前述の Active Directory ドメイン サービス 属性をすべて格納します。

ユーザー レプリケーターは、AbUserEntry テーブルと同じ SQL Server ベースのインスタンス内にある構成テーブルを読み取って、どの Active Directory 属性を書き込むかを決定します。AbAttribute テーブルには、**ID**、**名前**、**フラグ**、**有効** の 4 つの列があります。このテーブルはデータベースのセットアップ中に作成されます。AbAttribute テーブルが空の場合、ユーザー レプリケーターはその AbUserEntry テーブル処理ロジックをスキップします。アドレス帳サーバーの属性は動的で、AbAttribute テーブルから取得され、アドレス帳サーバーがアクティブ化される際、アドレス帳サーバーによって最初に書き込まれます。

アドレス帳サーバーのアクティブ化によって、次の表に示す値が AbAttribute テーブルに書き込まれます。


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
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Title</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Mail</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Department</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17</p></td>
<td><p>Description</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
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


**ID** 列の数字は一意である必要があり、再利用は一切できません。また、ID の値を 256 未満に保つことで、アドレス帳サーバーにより書き込まれる出力ファイルの領域を確保します。しかし、最大 ID 値は 65535 です。**名前** 列は、ユーザー レプリケーターによって連絡先ごとの AbUserEntry テーブル内に配置される Active Directory 属性名に対応しています。**フラグ**列の値は、属性の種類の定義に使用されます。次の種類のアドレス帳サーバー属性はユーザー レプリケーターにより認識され、**フラグ**列の値の低バイト数で示されます。


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
<td><p>文字列属性です。ユーザー レプリケーターは、AbUserEntry テーブルに格納する前に、この型を UTF-8 文字列に変換します。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>バイナリ属性です。ユーザー レプリケーターは、これを変換することなく BLOB に格納します</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>文字列属性です。ただし、属性値が &quot;tel:&quot; で始まる場合のみ含まれます。これは主に複数値の文字列属性、特に <strong>proxyAddresses</strong> 用です。この場合、アドレス帳サーバーは &quot;tel:&quot; で始まる <strong>proxyAddresses</strong> エントリのみに関係します。したがって、領域を確保するため、ユーザー レプリケーターは &quot;tel:&quot; で始まるエントリのみを格納します。</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>ブール値の文字列属性です。TRUE の場合、ユーザー レプリケーターはこの連絡先を AbUserEntry テーブルに含めません。FALSE の場合、ユーザー レプリケーターはこの連絡先の属性を AbUserEntry テーブルに含めますが、このフラグを持つ特定の属性は含めません。これは、主に <strong>msExchHideFromAddressLists</strong> 属性用である、もう 1 つの特例の型です。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>文字列属性です。ただし、属性値が &quot;smtp:&quot; で始まる場合のみ含まれます。これには、&quot;@&quot; 記号が含まれます。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>文字列属性です。ただし、属性値が &quot;tel:&quot; または &quot;smtp:&quot; で始まる場合のみ含まれます。これには、&quot;@&quot; 記号が含まれます。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>設定されている場合、これは各連絡先で複数回出現可能な複数値の属性です。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>設定されている場合、これは連絡先の電子メール ユーザー アカウント名の属性を示します。アドレス帳サーバーはこのフラグを使用して、電話正規化イベント ログのエントリに表示する属性値を特定します。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>設定されている場合、これは連絡先の必須属性を示します。アドレス帳サーバーは、Active Directory にこの属性の値がある場合のみ、ユーザーを AbUserEntry テーブルに含めます。必須属性が複数ある場合、ユーザーを AbUserEntry テーブルに含めるには、その中の 1 つのみに値がある必要があります。</p></td>
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
<td><p>設定されている場合、アドレス帳サーバーは、指定された属性にこの値を持つオブジェクトを AbUserEntry テーブルに含めません。たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> 属性がこのフラグ ビット セットを持つ場合、この属性を持つ連絡先はデータベースに書き込まれません。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>設定されている場合、アドレス帳サーバーは、指定された属性にこの値を持たないオブジェクトを AbUserEntry テーブルに含めません。0x4000 と 0x8000 の両方のフラグ ビットがオブジェクトに対して設定されている場合は、0x4000 に設定されたフラグ ビット値を持つ属性が優先され、オブジェクトは AbUserEntry テーブルから除外されます。</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>設定されている場合、これはグループ オブジェクトを表します。ユーザー レプリケーターはこのフラグ ビットを使用して、その存在がグループを示す<strong>groupType</strong> 属性を持つ連絡先を含めます (例: 配布リストまたはセキュリティ グループ)。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>設定されている場合、ユーザー レプリケーターはこのフラグ ビットを使用して、デバイス固有のアドレス帳サーバー ファイル (つまり, .dabs の拡張子を持つファイル) にこの属性を含めます。</p></td>
</tr>
</tbody>
</table>


以前のバージョンの Lync Server では、変更を Active Directory に適用するときは、**Update -CSUserDatabase** および **Update –CSAddressBook**Windows PowerShell コマンドレットを実行して、変更を Lync Server ユーザー データベースおよび RTCab データベースに直ちに保存する必要がありました。Lync Server 2013 では、Lync Server ユーザー レプリケーターが Active Directory から変更を取得し、設定されている間隔に基づいて Lync Server ユーザー データベースを更新します。また、Lync Server ユーザー レプリケーターは変更を RTCab データベースにすぐに反映するので、管理者が Update-CSAddressBook を実行する必要はありません。アドレス帳 Web クエリが有効になっている場合は、Lync クライアントによって検索結果に変更が反映されます。管理者は、アドレス帳ファイル ダウンロードが有効になっている場合に Update -CSAddressBook を実行することだけが必要です。

> [!NOTE]
> 既定では、Lync Server ユーザー レプリケーターは 5 分ごとに自動的に実行します。この間隔は、Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt; を使用して構成できます。


## アドレス帳のフィルター処理

アドレス帳サーバー ファイルに追加されるユーザーは、AbAttribute テーブルの一覧にある特定の Active Directory ドメイン サービス 属性に基づいて制御できます。そのようなフィルター処理に使用される属性の 1 つは、**msExchangeHideFromAddressBook** 属性です。これは、Exchange スキーマによって追加されるユーザー属性です。この属性の値が TRUE に設定されている場合、Exchange Server はこの属性を使用し、Outlook のグローバル アドレス一覧 (GAL) で連絡先を非表示にします。同様に、この属性の値が TRUE の場合、ユーザー レプリケーターはそのユーザーを AbUserEntry テーブルに含めず、このユーザーはアドレス帳サーバー ファイルに存在しなくなります。

一部のフラグ ビットを使用して、アドレス帳サーバー属性に対して使用するフィルターを定義できます。たとえば、特定のフラグ ビットがあることにより、ある属性を include 属性か exclude 属性として指定できます。ユーザー レプリケーターは、exclude 属性を含む連絡先を除外したり、include 属性を含まない連絡先を除外したりします。


> [!WARNING]
> アドレス帳のフィルター処理について詳しくは、「<A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">アドレス帳サーバーのコマンドレット</A>」および「<A href="http://go.microsoft.com/fwlink/?linkid=330430">Lync 2013 のアドレス帳のフィルター処理 (Filter Lync 2013 address book)</A>」をご覧ください。



現在は 3 種類のフィルターがあります。次の表にこれら 3 つのフィルターの一覧を示します。


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
<td><p>設定されている場合、これは連絡先の必須属性を示します。ユーザー レプリケーターはこのフラグ ビットを使用し、必須属性を少なくとも 1 つ含んでいない連絡先を除外します。OuPathId は必須属性で、必ず設定されます。そのため、その他の必須属性が少なくとも 1 つ設定される必要があります。それ以外の場合、(つまり、必須属性 OuPathId の値を持つ) 連絡先は、データベースにまだ書き込まれません。たとえば、<strong>telephoneNumber</strong> と <strong>homePhone</strong> が必須の属性として定義されている場合、これらの属性のうち少なくとも 1 つを持つ連絡先のみがデータベースに書き込まれます。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>設定されている場合、exclude 属性を示します。ユーザー レプリケーターはこのフラグ ビットを使用し、この属性を含む連絡先を除外します。たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> が exclude 属性として定義されている場合、この属性を持つ連絡先はデータベースに書き込まれません。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>設定されている場合、これは include 属性を示します。ユーザー レプリケーターはこのフラグ ビットを使用し、この属性を含まない連絡先を除外します。たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> が include 属性として定義されている場合、この属性を持つ連絡先のみがデータベースに書き込まれます。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 0x4000 (exclude 属性) と 0x8000 (include 属性) の両方のフラグ ビットが設定されている場合、0x4000 ビットが 0x8000 ビットより優先され、連絡先は除外されます。


アドレス帳をフィルターして特定のユーザーのみを含めることができますが、エントリを制限すると、他のユーザーがフィルターされたユーザーへ連絡したり、プレゼンス状態を参照したりできる範囲が制限されます。ユーザーは、ユーザーの完全なサインイン名を入力することで、アドレス帳にないユーザーに対する検索、インスタント メッセージの手動送信、手動での通話の開始をいつでも実行できます。また、ユーザーの連絡先情報は、Outlook でも検索できます。

アドレス帳ファイルにすべての連絡先レコードがあれば、Lync Server による電子メール、電話、セッション開始プロトコル (SIP) が構成されていないユーザーとのエンタープライズ VoIP 通話 (サーバーでエンタープライズ VoIP が有効化されている場合) ができますが、組織によっては SIP 対応のユーザーのみをアドレス帳サーバーのエントリに含める必要がある場合があります。次の必須属性 (**mailNickname**、**telephoneNumber**、**homePhone**、**mobile**) の**フラグ**列の 0x800 ビットをクリアしてアドレス帳をフィルターし、SIP 対応ユーザーのみを含めることもできます。また、**msRTCSIP-PrimaryUserAddress** 属性の**フラグ**列に 0x8000 (include 属性) を設定して、アドレス帳をフィルターし、SIP 対応のユーザーのみを含めることもできます。これは、アドレス帳ファイルからサービス アカウントを除外する際にも便利です。

AbAttribute テーブルを変更した後、コマンドレット **Update-CsUserDatabase** のコマンドを実行し、AbUserEntry テーブルのデータを更新できます。UR のレプリケーションが完了した後、コマンドレット **UpdateCsAddressBook** のコマンドを手動で実行し、アドレス帳サーバー ファイル ストアのファイルを更新できます。

> [!NOTE]
> アドレス帳サーバーが配置されているフロント エンド サーバーは、管理上構成できません。展開の間に選択すれます。通常は、展開される最初のフロント エンド サーバーです。障害時、アドレス帳サービスは別のフロント エンド サーバーに移動し、管理上の配慮は必要ありません。



> [!IMPORTANT]
> 複数フォレスト展開または親子展開からのインフラストラクチャ統合やその他の変更を行った場合 (Lync Server への移動前のインフラストラクチャ統合など)、一部のユーザーに対するアドレス帳サービス ダウンロードやアドレス帳 Web クエリにおいてエラーが見つかる場合があります。複数のドメインやフォレストがある展開内では、問題の発生しているユーザー オブジェクトに属性 <STRONG>MsRTCSIP-OriginatorSid</STRONG> が追加されます。問題を解決するには、これらのオブジェクトの <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性を NULL に設定する必要があります。



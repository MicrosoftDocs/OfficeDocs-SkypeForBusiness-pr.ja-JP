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
ms.openlocfilehash: 5d12b904cbb679b66579c7c669ba46e0d732034b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳サービスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

Lync Server Enterprise Edition または Standard Edition サーバーの展開の一部として、アドレス帳サービスは既定でインストールされています。 アドレス帳サービス– RTCab によって使用されたデータベースは、SQL Server (Enterprise Edition) に作成されます。これは、sql server (標準エディションサーバーの場合は、sql Server の場合は併置されます) のバックエンド SQL Server です。

<div>


> [!NOTE]  
> <STRONG>Adsi エディター</STRONG>を使用して Active Directory ドメインサービスオブジェクトの属性を編集する方法について詳しくは、「 <A href="http://go.microsoft.com/fwlink/?linkid=330427">adsi edit</A>」をご覧ください。 アドレス帳サービス専用のリソースキットに含まれるツールの詳細については、「 <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 リソースキットツール</A>」を参照してください。



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>アドレス帳のサーバー電話番号の正規化

Lync Server では、標準化された RFC 3966/E.i 電話番号が必要です。 非構造化または一貫性のない電話番号を使用するために、Lync Server はアドレス帳サーバーに依存して、正規化ルールに渡される前に電話番号の前処理を行います。 アドレス帳から電話番号を使用し、正規化ルールが適用されている場合、Lync Phone Edition や Lync Mobile などのクライアントでは、これらの正規化された数値を使用できます。

以前のバージョンで使用されていた正規化ルールは、一部の調整なしで適切に動作しないことがあります。 正規表現の規則を適用する前に空白文字と必須でない文字は削除されているため、regex 式が、削除されたダッシュや他の文字を探している場合は、正規化ルールが失敗する可能性があります。 正規化ルールを確認して、必須以外の文字を探していないことを確認するか、またはルールが適切に処理されないようにして、その文字が存在しないという問題が発生した場合は、そのルールが適切でないことを確認する必要があります。

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>ユーザーレプリケーターおよびアドレス帳サーバー

アドレス帳サーバーは、ユーザーレプリケーターによって提供されたデータを使用して、最初にグローバルアドレス一覧 (GAL) から取得した情報を更新します。 ユーザーレプリケーターは、各ユーザー、連絡先、グループの Active Directory ドメインサービスの属性をデータベースの AbUserEntry テーブルに書き込みます。アドレス帳サーバーは、データベースのユーザーデータをアドレス帳サーバーファイルストア内のファイルに同期し、アドレス帳データベースの RTCab に入ります。 AbUserEntry テーブルのスキーマでは、 **Userguid**と**UserData**の2つの列を使用します。 **Userguid**はインデックス列で、Active Directory オブジェクトの16バイトの GUID が含まれています。 **UserData**は、前に説明した、その連絡先の Active Directory ドメインサービスのすべての属性を含む image 列です。

ユーザーレプリケーターは、AbUserEntry テーブルと同じ SQL Server ベースのインスタンスにある構成テーブルを読み取ることによって、どの Active Directory 属性を作成するかを決定します。 AbAttribute テーブルには、 **ID**、 **Name**、 **Flags**、および**Enable**という3つの列が含まれています。 データベースのセットアップ中にテーブルが作成されます。 AbAttribute テーブルが空の場合、ユーザーレプリケーターは AbUserEntry テーブル処理ロジックをスキップします。 アドレス帳のサーバー属性は動的であり、AbAttribute テーブルから取得されます。これは、アドレス帳サーバーがアクティブ化されたときに、最初にアドレス帳サーバーによって作成されます。

アドレス帳サーバーのアクティブ化によって、次の表に示す値を含む AbAttribute テーブルが設定されます。


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
<td><p>一定</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>両面</p></td>
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
<td><p>タイトル</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>貴社</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>Physicaldeliveryのお Ename</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>個</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>ファイブ</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>常用</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>折り</p></td>
<td><p>モバイル</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>以内</p></td>
<td><p>その他の電話</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>14</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>添付</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>マート</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>各部</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>18</p></td>
<td><p>説明</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>才</p></td>
<td><p>上司</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>#</p></td>
<td><p>た proxyaddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>超える</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>Id</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


**ID**列の数値は一意である必要があり、再利用することは避けてください。 また、256の ID 値を保持すると、アドレス帳サーバーによって書き込まれた出力ファイル内のスペースが節約されます。 ただし、ID の最大値は65535です。 **Name**列は、ユーザーレプリケーターが各連絡先の AbUserEntry テーブルに配置する Active Directory 属性名に対応しています。 **Flags**列の値は、属性の型を定義するために使われます。 次の種類のアドレス帳サーバー属性は、 **Flags**列の値の下位バイトで示されるユーザーレプリケーターによって認識されます。


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
<td><p>100</p></td>
<td><p>文字列属性。 ユーザーレプリケーターは、AbUserEntry テーブルに保存する前に、この型を UTF-8 に変換します。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>バイナリ属性。 ユーザーレプリケーターは、変換せずに blob にこれを格納します。</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>文字列属性。ただし、属性値が tel: &quot;&quot;で始まる場合にのみ含まれます。 これは主に、複数値を持つ文字列属性 (具体的には<strong>proxyAddresses</strong>です。 この場合、アドレス帳サーバーは、tel: &quot;&quot;で始まる<strong>proxyAddresses</strong>エントリのみに注目します。 したがって、スペース節約のために、ユーザーレプリケーターには tel: &quot;&quot;で始まるエントリのみが格納されます。</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>ブール文字列属性。 TRUE の場合、ユーザーレプリケーターは AbUserEntry テーブルにこの連絡先を含めません。 FALSE の場合、ユーザーレプリケーターによってこの連絡先の属性が AbUserEntry テーブルに含まれますが、このフラグの特定の属性は含まれません。 これは、主に<strong>msExchHideFromAddressLists</strong>属性用の別の特殊なケースの型です。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>文字列属性。ただし、属性値が&quot;smtp&quot;で始まり、 &quot; @ &quot;記号が含まれている場合にのみ含まれます。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>文字列属性。ただし、属性値が tel: &quot;&quot;または&quot;smtp:&quot;のいずれかで始まり、その&quot; @ &quot;記号が含まれている場合にのみ含まれます。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>設定されている場合、これは複数値の属性であり、連絡先ごとに複数回表示することができます。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>設定すると、連絡先のメールユーザーアカウント名の属性が識別されます。 アドレス帳サーバーは、このフラグを使って、電話の正規化イベントログエントリに表示する属性値を特定します。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>設定すると、連絡先に必須の属性が指定します。 アドレス帳サーバーには、Active Directory にこの属性の値がある場合にのみ、AbUserEntry テーブルにユーザーが含まれています。 必要な属性が複数ある場合は、そのうちの1つだけが、AbUserEntry テーブルにユーザーを含めるための値を持つ必要があります。</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>設定されている場合、アドレス帳サーバーはこの属性の値を常に標準化します。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>設定されている場合、 <strong>UseNormalizationRules</strong> CMS 設定が FALSE の場合、アドレス帳サーバーは<strong>proxyAddresses</strong>の正規化された数値を使用します。それ以外の場合は、フラグビットが0x1000 の場合と同じように動作します。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>設定されている場合、アドレス帳サーバーには、指定した属性に対してこの値を持つ AbUserEntry テーブル内のオブジェクトは含まれません。 たとえば、 <strong>msrtcsip-userenabled true-PrimaryUserAddress</strong>属性にこのフラグビットが設定されている場合、この属性を持つ連絡先はデータベースに書き込まれません。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>設定されている場合、アドレス帳サーバーには、指定した属性に対してこの値を持たない AbUserEntry テーブル内のオブジェクトは含まれません。 オブジェクトに0x4000 と0x8000 の両方のフラグビットが設定されている場合は、フラグビット値が0x4000 に設定された属性が優先され、オブジェクトは AbUserEntry テーブルから除外されます。</p></td>
</tr>
<tr class="even">
<td><p>○</p></td>
<td><p>設定すると、グループオブジェクトを表します。 ユーザーレプリケーターは、このフラグビットを使用して、 <strong>groupType</strong>属性が設定された連絡先を含めます (たとえば、配布リストまたはセキュリティグループの場合)。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>設定されている場合、ユーザーレプリケーターはこのフラグビットを使って、デバイス固有のアドレス帳サーバーファイル (つまり、dabs 拡張子を持つファイル) にこの属性を含めます。</p></td>
</tr>
</tbody>
</table>


以前のバージョンの Lync Server で、Active Directory に変更を適用する場合、管理者は、Lync Server ユーザーデータベースと RTCab データベースへの変更をすぐに保持するために、 **CSAddressBook** Windows PowerShell コマンドレット**を実行する**必要があります。 Lync server 2013 では、Lync Server ユーザーレプリケーターは Active Directory から変更を受け取り、構成された間隔に基づいて Lync Server ユーザーデータベースを更新します。 Lync Server ユーザーレプリケーターでは、管理者が更新プログラムを実行しなくても、変更内容が RTCab データベースにすばやく反映されます CSAddressBook。 アドレス帳 Web クエリが有効になっている場合、変更は Lync クライアントの検索結果に反映されます。 CSAddressBook を実行するには、アドレス帳ファイルのダウンロードが有効になっている必要があります。

<div>


> [!NOTE]  
> Lync Server ユーザーレプリケーターは、既定では、5分ごとに自動的に実行されます。 この間隔は、ReplicationCycleInterval &lt; &gt;を使用して設定できます。



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>アドレス帳をフィルター処理する

アドレス帳のサーバーファイルに設定されているユーザーは、AbAttribute テーブルに記載されている特定の Active Directory ドメインサービスの属性に基づいて制御できます。 フィルター処理に使う属性は、 **msExchangeHideFromAddressBook**属性の1つです。 これは、Exchange スキーマによって追加されたユーザー属性です。 この属性の値が TRUE の場合、Exchange Server はこの属性を使って、連絡先を Outlook のグローバルアドレス一覧 (GAL) から非表示にします。 同様に、この属性の値が TRUE の場合、ユーザーレプリケーターは AbUserEntry テーブルにそのユーザーを含めません。このユーザーはアドレス帳のサーバーファイルには含まれません。

一部のフラグビットを使って、アドレス帳のサーバー属性で使用するフィルターを定義できます。 たとえば、特定のフラグビットが存在する場合、属性は include 属性または exclude 属性として識別できます。 ユーザーレプリケーターフィルター除外属性が含まれている連絡先には、include 属性を含まない連絡先が含まれています。

<div>


> [!WARNING]  
> アドレス帳のフィルター処理の詳細については、「 <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Lync server 2013 のアドレス帳サーバーコマンドレット</A>」および「 <A href="http://go.microsoft.com/fwlink/?linkid=330430">lync 2013 のアドレス帳をフィルター</A>処理する」を参照してください。



</div>

現在、3種類のフィルターがあります。 次の表は、これらのフィルターの一覧です。


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
<td><p>設定すると、連絡先に必須の属性が指定します。 ユーザーレプリケーターでは、少なくとも1つの必須属性が含まれていない連絡先を除外するために、このフラグビットを使用しています。 OuPathId は必須の属性であり、常に設定されています。 そのため、必要な他の属性の少なくとも1つを設定する必要があります。 それ以外の場合は、(つまり、必須属性 OuPathId の値を持つ) 連絡先はデータベースに書き込まれません。 たとえば、 <strong>telephoneNumber</strong>と<strong>homePhone</strong>が必須属性として定義されている場合、これらの属性の少なくとも1つが含まれている連絡先のみがデータベースに書き込まれます。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>設定すると、exclude 属性が識別されます。 ユーザーレプリケーターはこのフラグビットを使って、この属性を含む連絡先をフィルター処理します。 たとえば、 <strong>msrtcsip-userenabled true-PrimaryUserAddress</strong>が exclude 属性として定義されている場合、この属性を持つ連絡先はデータベースに書き込まれません。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>設定すると、include 属性が識別されます。 ユーザーレプリケーターはこのフラグビットを使って、この属性が含まれていない連絡先を除外します。 たとえば、 <strong>msrtcsip-userenabled true-PrimaryUserAddress</strong>が include 属性として定義されている場合、この属性を持つ連絡先のみがデータベースに書き込まれます。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 0x4000 (exclude 属性) と 0x8000 (include 属性) の両方のフラグビットが設定されている場合、0x4000 ビットは0x8000 ビットよりも優先され、その連絡先は除外されます。



</div>

アドレス帳をフィルター処理して特定のユーザーのみを含めることはできますが、エントリを制限しても、他のユーザーがフィルター処理されたユーザーに連絡したり、プレゼンス状態を表示したりすることを制限することはできません。 ユーザーは、ユーザーの完全なサインイン名を入力して、いつでもインスタントメッセージを検索したり、手動でインスタントメッセージを送信したり、アドレス帳に登録されていないユーザーに対して手動で通話を開始したりできます。 また、ユーザーの連絡先情報も Outlook にあります。

アドレス帳のファイルに完全な連絡先レコードを作成しているときに、Lync Server を使用して、セッションの開始を許可するように構成されていないユーザーとメール、電話、またはエンタープライズの音声通話を開始することができます (つまり、サーバー上のエンタープライズボイスが有効になっている場合)。Protocol (SIP) では、組織によっては、SIP 対応ユーザーのみをアドレス帳サーバーエントリに含めることを希望しています。 アドレス帳にフィルターを適用して、SIP 対応ユーザーのみを含めることができます。これには、 **mailNickname**、 **telephoneNumber**、 **homePhone**、および**mobile**の各必須属性の**Flags**列にある [0x800] ビットをオフにします。 また、 **msrtcsip-userenabled true-PrimaryUserAddress**属性の**Flags**列に 0x8000 (include 属性) を設定することによって、SIP 対応ユーザーのみを含めるようにアドレス帳をフィルター処理することもできます。 これにより、アドレス帳ファイルからサービスアカウントを除外することもできます。

AbAttribute テーブルを変更したら、[コマンドレットの**更新**] を実行して、AbUserEntry テーブルのデータを更新できます。 UR レプリケーションが完了したら、コマンドレット**UpdateCsAddressBook**コマンドを手動で実行することで、アドレス帳のサーバーファイルストア内のファイルを更新できます。

<div>


> [!NOTE]  
> アドレス帳サーバーが配置されているフロントエンドサーバーは、管理上では構成できません。 1つは展開中に選択されます。通常は、最初のフロントエンドサーバーが展開されます。 障害が発生した場合、アドレス帳サービスは別のフロントエンドサーバーに移動し、管理の注意は必要ありません。



</div>

<div>


> [!IMPORTANT]  
> マルチフォレスト展開または親/子展開 (インフラストラクチャの統合など) からインフラストラクチャを統合または変更した場合に、一部のユーザーのアドレス帳サービスのダウンロードとアドレス帳 Web クエリが失敗することがあります。 複数のドメインまたはフォレストが含まれている展開では、この問題が発生しているユーザーオブジェクトに<STRONG>msrtcsip-userenabled true</STRONG>という属性が設定されます。 問題を解決するには、これらのオブジェクトで<STRONG>msrtcsip-userenabled true-Atorsid</STRONG>属性を NULL に設定する必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


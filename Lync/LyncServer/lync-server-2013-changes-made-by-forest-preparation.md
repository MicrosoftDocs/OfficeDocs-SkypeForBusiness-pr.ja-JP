---
title: 'Lync Server 2013: フォレストの準備によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013 でのフォレストの準備によって行われた変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順によって作成されるユニバーサルサービスと管理グループについて説明します。

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory のグローバル設定とオブジェクト

すべての新しい Lync Server 2013 の展開の場合と同様に、構成コンテナーにグローバル設定を保存する場合、フォレストの準備では既存のサービスコンテナーが使用され、Configuration\\Services オブジェクトの下に**RTC サービス**オブジェクトが追加されます。 RTC Service オブジェクトの下で、フォレストの準備によって型が Msrtcsip-userenabled true-GlobalContainer の**グローバル設定**オブジェクトが追加されます。 グローバル設定オブジェクトには、Lync Server の展開に適用されるすべての設定が含まれます。 システムコンテナーにグローバル設定を保存する場合、フォレストの準備では、ルートドメインシステムコンテナーの下に Microsoft コンテナー、System\\microsoft オブジェクトの下に RTC サービスオブジェクトが使用されます。

フォレストの準備では、この手順を実行するルートドメイン用の新しい**msrtcsip-userenabled true**オブジェクトも追加されます。

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory ユニバーサルサービスと管理グループ

フォレストの準備によって、指定したドメインに基づいてユニバーサルグループが作成され、これらのグループにアクセス制御エントリ (Ace) が追加されます。 この手順では、指定したドメインのユーザーコンテナーでユニバーサルグループを作成します。

ユニバーサルグループを使用すると、管理者はグローバル設定とサービスにアクセスして管理することができます。 フォレストの準備によって、次の種類のユニバーサルグループが追加されます。

  - **管理グループ**   これらのグループは、Lync Server ネットワークの管理者ロールを定義します。

  - **インフラストラクチャグループ**   これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 これらは、管理グループのコンポーネントとして機能します。 これらのグループを変更したり、これらのグループにユーザーを直接追加したりすることはできません。

  - **サービスグループ**   これらのグループは、さまざまな Lync Server サービスへのアクセスに必要なサービスアカウントです。

次の表では、管理グループについて説明します。

### <a name="administrative-groups-created-during-forest-preparation"></a>フォレストの準備中に作成された管理グループ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>管理グループ</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーとプールの設定を管理することをメンバーに許可します。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>メンバーがユーザー設定を管理し、あるサーバーまたはプール間でユーザーを移動できるようにします。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>サーバー、プール、ユーザー設定の読み取りをメンバーに許可します。</p></td>
</tr>
</tbody>
</table>


次の表では、インフラストラクチャグループについて説明します。

### <a name="infrastructure-groups-created-during-forest-preparation"></a>フォレストの準備中に作成されたインフラストラクチャグループ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>インフラストラクチャグループ</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Lync Server のグローバル設定オブジェクトへの書き込みアクセス権を付与します。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Lync Server のグローバル設定オブジェクトへの読み取り専用アクセスを許可します。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lync Server のユーザー設定に対する読み取り専用アクセス権を付与します。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lync Server の設定に対する読み取り専用アクセス権を付与します。 このグループは、個々のサーバーに固有の設定のみに、プールレベルの設定にアクセスすることはできません。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>インストール時に、Lync Server 構成への読み取り専用アクセスを許可し、survivable branch アプライアンスのローカル管理者グループに配置されます。</p></td>
</tr>
</tbody>
</table>


次の表では、サービスグループについて説明します。

### <a name="service-groups-created-during-forest-preparation"></a>フォレストの準備中に作成されたサービスグループ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>サービスグループ</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>フロントエンドサーバーおよび Standard Edition サーバーの実行に使用するサービスアカウントが含まれています。 このグループでは、Lync Server のグローバル設定と Active Directory ユーザーオブジェクトへのサーバーの読み取り/書き込みアクセスが許可されています。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>A/V 会議サーバー、Web サービス、仲介サーバー、アーカイブサーバー、監視サーバーの実行に使用されるサービスアカウントが含まれています。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Lync Server Edge サーバーを実行するために使用されるサービスアカウントが含まれています。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Lync Server 全体管理ストアのレプリケーションに参加できるサーバーが含まれています。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Lync Server の設定への読み取り専用アクセス権を付与しますが、survivable branch Server と survivable branch appliance の展開のインストールの構成を許可します。</p></td>
</tr>
</tbody>
</table>


次に示すように、フォレストの準備によって、適切なインフラストラクチャグループにサービスグループと管理グループが追加されます。

  - RTCUniversalServerAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加されます。

  - RTCUniversalUserAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。

  - RTCHSUniversalServices、RTCComponentUniversalServices、RTCUniversalReadOnlyAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。

フォレストの準備では、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

RBAC の役割と、それぞれに対して許可されるタスクの詳細については、計画ドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

フォレストの準備では、プライベート Ace とパブリック Ace の両方が作成されます。 Lync Server によって使用されるグローバル設定コンテナーにプライベート Ace を作成します。 このコンテナーは、Lync Server によってのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーのいずれかにあります。 次の表に、フォレストの準備によって作成されたパブリック Ace を示します。

### <a name="public-aces-created-by-forest-preparation"></a>フォレストの準備によって作成されたパブリック Ace

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AS</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ルートドメインシステムコンテナーを読み取ります (継承されません)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>構成の DisplaySpecifiers 子コンテナーを読み取ります (継承されません)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>継承されない Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与しません。 継承された Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与します。



</div>

構成コンテナーでは、構成の名前付けコンテキストの下で、フォレストの準備で次のタスクを実行します。

  - ユーザー、連絡先、InetOrgPersons の言語表示指定子 (例: CN = ユーザー表示、CN = 409、CN = DisplaySpecifiers 子) の adminContextMenu**プロパティ**と adminPropertyPages 属性のエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を追加します。

  - ユーザークラスと連絡先クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCPropertySet**オブジェクトを追加します。

  - ユーザー、連絡先、OU、および DomainDNS クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCUserSearchPropertySet**オブジェクトを追加します。

  - 各言語の組織単位 (OU) 表示指定子の**extraColumns**属性の下に**Msrtcsip-userenabled true-primaryuseraddress**を追加します (例: Cn = organizationalUnit-display、CN = 409、cn = displayspecifiers 子)。既定の表示の**extraColumns**属性の値をコピーします (例: CN = default-DISPLAY、Cn = 409、cn = displayspecifiers 子)。

  - ユーザー、連絡先、および InetOrgPerson オブジェクトの各言語表示指定子の**Attributedisplaynames**属性の**Msrtcsip-userenabled true-primaryuseraddress**、 **Msrtcsip-userenabled true-PrimaryHomeServer**、および**msrtcsip-userenabled true-userenabled**フィルター属性を追加します (たとえば、英語: CN = ユーザー表示、cn = 409、cn = display指定子)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


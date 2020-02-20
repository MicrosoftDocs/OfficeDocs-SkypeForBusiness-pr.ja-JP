---
title: 'Lync Server 2013: フォレストの準備によって加えられた変更'
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
ms.openlocfilehash: 709263aeffe1a8681275d943da702242944868b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013 でのフォレストの準備によって加えられた変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory のグローバル設定とオブジェクト

構成コンテナーにグローバル設定を格納する場合 (すべての新しい Lync Server 2013 展開の場合と同様)、フォレストの準備では、既存のサービスコンテナーを使用し、構成\\サービスオブジェクトの下に**RTC Service**オブジェクトを追加します。 フォレストの準備では、msRTCSIP-GlobalContainer 型の **Global Settings** オブジェクトが RTC サービス オブジェクトに追加されます。 グローバル設定オブジェクトには、Lync Server の展開に適用されるすべての設定が含まれています。 システムコンテナーにグローバル設定を格納すると、フォレストの準備では、ルートドメインシステムコンテナーの下の Microsoft コンテナーと、System\\microsoft オブジェクトの下にある RTC サービスオブジェクトが使用されます。

またフォレストの準備では、この手順が実行されるルート ドメインの新しい **msRTCSIP-Domain** オブジェクトが追加されます。

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory のユニバーサル サービス グループとユニバーサル管理グループ

フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (ACE) を追加します。このステップにより、指定したドメインのユーザー コンテナーにユニバーサル グループが作成されます。

ユニバーサル グループを使用すると、管理者はグローバル設定およびサービスにアクセスしてそれらを管理できます。フォレストの準備により、次の種類のユニバーサル グループが追加されます。

  - **管理グループ**   これらのグループは、Lync Server ネットワークの管理者の役割を定義します。

  - **インフラストラクチャグループ**   これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。 これらは、管理グループのコンポーネントとして機能します。 これらのグループを変更したり、ユーザーを直接追加したりすることはできません。

  - **サービスグループ**   これらのグループは、さまざまな Lync Server サービスにアクセスするために必要なサービスアカウントです。

次の表では、管理グループについて説明します。

### <a name="administrative-groups-created-during-forest-preparation"></a>フォレストの準備時に作成される管理グループ

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
<td><p>このグループのメンバーは、すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーおよびプールの設定を管理できます。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>このグループのメンバーは、ユーザー設定を管理したり、あるサーバーまたはプールから、別のサーバーまたはプールにユーザーを移動したりできます。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>このグループのメンバーは、サーバー、プール、およびユーザーの設定を読み取ることができます。</p></td>
</tr>
</tbody>
</table>


次の表では、インフラストラクチャ グループについて説明します。

### <a name="infrastructure-groups-created-during-forest-preparation"></a>フォレストの準備時に作成されるインフラストラクチャ グループ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>インフラストラクチャ グループ</th>
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
<td><p>Lync Server のグローバル設定オブジェクトへの読み取り専用アクセス権を付与します。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lync Server ユーザー設定への読み取り専用アクセスを許可します。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lync Server 設定への読み取り専用アクセス権を付与します。 このグループは、プール レベルの設定にはアクセスできず、個々のサーバーに固有の設定のみにアクセスできます。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Lync Server 構成への読み取り専用アクセスを許可し、インストール中に存続可能 branch アプライアンスのローカルの Administrators グループに配置されます。</p></td>
</tr>
</tbody>
</table>


次の表では、サービス グループについて説明します。

### <a name="service-groups-created-during-forest-preparation"></a>フォレストの準備時に作成されるサービス グループ

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>サービス グループ</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>フロントエンドサーバーおよび Standard Edition サーバーの実行に使用されるサービスアカウントが含まれています。 このグループでは、Lync Server のグローバル設定および Active Directory ユーザーオブジェクトへのサーバーの読み取り/書き込みアクセスが許可されます。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>音声ビデオ会議サーバー、Web サービス、仲介サーバー、アーカイブサーバー、および監視サーバーの実行に使用されるサービスアカウントが含まれています。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Lync Server エッジサーバーを実行するために使用されるサービスアカウントが含まれています。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Lync Server Central Management store のレプリケーションに参加できるサーバーが含まれています。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Lync Server 設定への読み取り専用アクセスが許可されますが、存続可能 branch server と存続可能 branch appliance の展開のインストールのための構成を許可します。</p></td>
</tr>
</tbody>
</table>


フォレストの準備では、次に示すサービス グループと管理グループをインフラストラクチャ グループに追加します。

  - RTCUniversalServerAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加します。

  - RTCUniversalUserAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。

  - RTCHSUniversalServices、RTCComponentUniversalServices、および RTCUniversalReadOnlyAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。

フォレストの準備によって、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。

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

RBAC の役割および各に対して許可されるタスクの詳細については、「計画」のドキュメントの「 [planning for roles based access control In Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) 」を参照してください。

フォレストの準備では、プライベート ACE とパブリック ACE の両方を作成します。 Lync Server によって使用されるグローバル設定コンテナーにプライベートの Ace を作成します。 このコンテナーは、Lync Server によってのみ使用され、グローバル設定を格納する場所に応じて、構成コンテナーまたはルートドメインのシステムコンテナーに格納されます。 フォレストの準備で作成するパブリック ACE の一覧を次の表に示します。

### <a name="public-aces-created-by-forest-preparation"></a>フォレストの準備で作成するパブリック ACE

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ルート ドメインのシステム コンテナーの読み取り (継承されない)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>構成の DisplaySpecifiers コンテナーの読み取り (継承されない)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>継承されていない Ace は、これらのコンテナーの下にある子オブジェクトへのアクセスを許可しません。 継承された Ace は、これらのコンテナーの下にある子オブジェクトへのアクセスを付与します。



</div>

フォレストの準備では、構成名前付けコンテキストの下の構成コンテナーで次のタスクを実行します。

  - **RTC property** ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を、ユーザー、連絡先、および InetOrgPersons の言語表示指定子の adminContextMenu および adminPropertyPages 属性に追加します (CN=user-Display、CN=409、CN=DisplaySpecifiers など)。

  - User クラスと Contact クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCPropertySet** オブジェクトを追加します。

  - User、Contact、OU、および DomainDNS クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCUserSearchPropertySet** オブジェクトを追加します。

  - 各言語の組織単位 (OU) の表示指定子の **extraColumns** 属性に **msRTCSIP-PrimaryUserAddress** を追加し (CN=organizationalUnit-Display、CN=409、CN=DisplaySpecifiers など)、既定の表示の **extraColumns** 属性の値をコピーします (CN=default-Display、CN=409、CN=DisplaySpecifiers など)。

  - **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer**、および **msRTCSIP-UserEnabled** フィルター属性を、Users、Contacts、および InetOrgPerson オブジェクトの各言語表示指定子の **attributeDisplayNames** 属性に追加します (たとえば英語では、CN=user-Display、CN=409、CN=DisplaySpecifiers など)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


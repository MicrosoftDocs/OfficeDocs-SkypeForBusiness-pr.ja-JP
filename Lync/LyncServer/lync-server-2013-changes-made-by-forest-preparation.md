---
title: Lync Server 2013 でのフォレストの準備による変更
TOCTitle: Lync Server 2013 でのフォレストの準備による変更
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48271670
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフォレストの準備による変更

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。

## Active Directory のグローバル設定とオブジェクト

(新しい Lync Server 2013 展開で常に行われるように) 構成コンテナー内にグローバル設定を格納する場合は、フォレストの準備で既存のサービス コンテナーが使用され、Configuration\\Services オブジェクトに **RTC Service** オブジェクトが追加されます。フォレストの準備では、msRTCSIP-GlobalContainer 型の **Global Settings** オブジェクトが RTC サービス オブジェクトに追加されます。グローバル設定オブジェクトには、Lync Server の展開に適用されるすべての設定が保持されます。グローバル設定をシステム コンテナーに保存する場合は、フォレストの準備で新しい ルート ドメインのシステム コンテナーの下の Microsoft コンテナーと、システム\\Microsoft オブジェクトの下の RTC サービス オブジェクトが使用されます。

またフォレストの準備では、この手順が実行されるルート ドメインの新しい **msRTCSIP-Domain** オブジェクトが追加されます。

## Active Directory のユニバーサル サービス グループとユニバーサル管理グループ

フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (ACE) を追加します。このステップにより、指定したドメインのユーザー コンテナーにユニバーサル グループが作成されます。

ユニバーサル グループを使用すると、管理者はグローバル設定およびサービスにアクセスしてそれらを管理できます。フォレストの準備により、次の種類のユニバーサル グループが追加されます。

  - **管理グループ** これらのグループは Lync Server ネットワークの管理者の役割を定義します。

  - **インフラストラクチャ グループ**Lync Server インフラストラクチャの特定の領域へのアクセスを許可するグループです。これらのグループは管理グループの構成要素として機能します。これらのグループを変更したり、ユーザーをこれらのグループに直接追加したりしないでください。

  - **サービス グループ** これらのグループは、さまざまな Lync Server サービスへのアクセスに必要なサービス アカウントです。

次の表では、管理グループについて説明します。

### フォレストの準備時に作成される管理グループ

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

### フォレストの準備時に作成されるインフラストラクチャ グループ

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
<td><p>Lync Server のグローバル設定オブジェクトへの書き込みアクセス権が付与されます。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Lync Server のグローバル設定オブジェクトへの読み取り専用アクセス権が付与されます。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lync Server のユーザー設定への読み取り専用アクセス権が付与されます。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lync Server の設定への読み取り専用アクセス権が付与されます。このグループは、プール レベルの設定にはアクセスできず、個々のサーバーに固有の設定のみにアクセスできます。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Lync Server の構成への読み取り専用アクセス権が付与され、インストール中に、存続可能ブランチ アプライアンスの Local Administrators グループに配置されます。</p></td>
</tr>
</tbody>
</table>


次の表では、サービス グループについて説明します。

### フォレストの準備時に作成されるサービス グループ

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
<td><p>フロント エンド サーバーと Standard Edition サーバーの実行に使用されるサービス アカウントが含まれます。このグループを使用すると、Lync Server のグローバル設定および Active Directory ユーザー オブジェクトに対するサーバーの読み取り/書き込みアクセスが許可されます。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>音声ビデオ会議サーバー、Web サービス、仲介サーバー、アーカイブ サーバー、および監視サーバーの実行に使用されるサービス アカウントが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Lync Server エッジ サーバーの実行に使用されるサービス アカウントが含まれます。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Lync Server中央管理ストアのレプリケーションに参加できるサーバーが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Lync Server の設定への読み取り専用アクセス権が付与されますが、存続可能ブランチ サーバーおよび存続可能ブランチ アプライアンス展開のインストールに関する構成は許可されます。</p></td>
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

RBAC の役割、および各役割で許可されるタスクの詳細については、「計画」のドキュメントの「[Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

フォレストの準備では、プライベート ACE とパブリック ACE の両方を作成します。プライベート ACE は、Lync Server で使用されるグローバル設定コンテナーに対して作成されます。このコンテナーは Lync Server のみで使用され、グローバル設定の格納場所によって、ルート ドメイン内の構成コンテナーまたはシステム コンテナーに配置されます。フォレストの準備で作成するパブリック ACE の一覧を次の表に示します。

### フォレストの準備で作成するパブリック ACE

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


> [!NOTE]
> <strong>*</strong> 継承されない ACE では、これらのコンテナーの下の子オブジェクトへのアクセスが許可されません。継承される ACE では、これらのコンテナーの下の子オブジェクトへのアクセスが許可されます。


フォレストの準備では、構成名前付けコンテキストの下の構成コンテナーで次のタスクを実行します。

  - **RTC property** ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を、ユーザー、連絡先、および InetOrgPersons の言語表示指定子の adminContextMenu および adminPropertyPages 属性に追加します (CN=user-Display、CN=409、CN=DisplaySpecifiers など)。

  - User クラスと Contact クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCPropertySet** オブジェクトを追加します。

  - User、Contact、OU、および DomainDNS クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCUserSearchPropertySet** オブジェクトを追加します。

  - 各言語の組織単位 (OU) の表示指定子の **extraColumns** 属性に **msRTCSIP-PrimaryUserAddress** を追加し (CN=organizationalUnit-Display、CN=409、CN=DisplaySpecifiers など)、既定の表示の **extraColumns** 属性の値をコピーします (CN=default-Display、CN=409、CN=DisplaySpecifiers など)。

  - **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer**、および **msRTCSIP-UserEnabled** フィルター属性を、Users、Contacts、および InetOrgPerson オブジェクトの各言語表示指定子の **attributeDisplayNames** 属性に追加します (たとえば英語では、CN=user-Display、CN=409、CN=DisplaySpecifiers など)。


---
title: 'Lync Server 2013: 役割ベースのアクセス制御の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88353019a266fbb094df8808faa4543e31bf562
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Lync Server 2013 での役割ベースのアクセス制御の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-01-27_

高水準のセキュリティを維持しながら管理タスクを委任できるようにするために、Lync Server 2013 は役割ベースのアクセス制御 (RBAC) を提供しています。 RBAC では、ユーザーを管理役割に割り当てることによって管理特権を付与します。 Lync Server 2013 には、組み込みの管理役割の豊富なセットが含まれており、新しい役割を作成し、新しい役割ごとにコマンドレットのカスタムリストを指定することもできます。 また、定義済み RBAC 役割およびカスタム RBAC 役割の許可されたタスクに、コマンドレットのスクリプトを追加することもできます。

<div>

## <a name="better-server-security-and-centralization"></a>優れたサーバー セキュリティと集中管理

RBAC を使用すると、アクセスと承認は、ユーザーの Lync Server の役割に正確に基づいています。 これにより、管理者およびユーザーに各自の業務に必要な権限のみを付与するセキュリティ プラクティス ("最小限の特権") を利用できます。

<div>


> [!IMPORTANT]  
> RBAC 制限は、Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用して、リモートで作業している管理者に対してのみ機能します。 Lync Server を実行しているサーバーのユーザーは、RBAC によって制限されていません。 そのため、RBAC 制限を保持するには、Lync Server の物理的なセキュリティが重要です。



</div>

</div>

<div>

## <a name="roles-and-scope"></a>役割とスコープ

RBAC において、ある役割** に属するユーザーは、特定のタイプの管理者または技術者用に定義された一連のコマンドレットを使用できます。スコープ** は、役割で定義されているコマンドレットで操作できる一連のオブジェクトです。スコープの影響を受けるオブジェクトは、ユーザー アカウント (組織単位でグループ化) またはサーバー (サイト単位でグループ化) のどちらかです。

次の表に、Lync Server で定義されている役割の一覧と、各タスクの種類について一般的な概要を示します。 4番目の列には、各 Lync Server の役割に類似した Microsoft Exchange サーバーの役割 (存在する場合) が表示されます。

### <a name="predefined-administrative-roles"></a>定義済みの管理役割

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role</th>
<th>実行可能なタスク</th>
<th>基礎となる Active Directory グループ</th>
<th>対応する Exchange Server の役割</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>すべての管理タスクの実行とすべての設定の変更ができます。これには、役割の作成や役割へのユーザーの割り当ても含まれます。 新しいサイト、プール、およびサービスを追加して展開を拡張できます。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Lync Server でユーザーを有効または無効にしたり、ユーザーを移動したり、既存のポリシーをユーザーに割り当てることができます。 ポリシーは変更できません。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mail Recipients</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>音声関連の設定やポリシーを作成、構成、および管理できます。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>サーバーやサービスを管理、監視、およびトラブルシューティングできます。 サーバーへの新しい接続を禁止したり、サービスを停止および開始したり、ソフトウェア更新プログラムを適用したりできます。 グローバル構成に影響する変更はできません。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Management</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>展開の状態を監視するためにユーザーやサーバーの情報を含む展開を表示できます。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>View-Only Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>ユーザーのプロパティやポリシーを含む展開を表示できます。 特定のトラブルシューティング タスクを実行できます。 ユーザーのプロパティやポリシー、サーバー構成、またはサービスは変更できません。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>問い合わせ</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>アーカイブ構成およびポリシーを変更できます。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Retention Management, Legal Hold</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>サイト内の応答グループ アプリケーションの構成を管理できます。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) を管理するための最低レベルの権限。E9-1-1 の場所とネットワーク識別子の作成、およびこれらの相互関連付けが含まれます。 この役割は必ずグローバル スコープに関連付けられます。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>特定の応答グループを管理できます。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>常設チャット機能および特定の常設チャット ルームを管理できます。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
</tbody>
</table>


Lync Server に出荷されたすべての定義済みの役割には、グローバルスコープがあります。 最小限の特権のプラクティスを実施するには、限定的なサーバーやユーザーのセットのみを管理するユーザーに対して、グローバル スコープを持つ役割を割り当てないようにする必要があります。 これを実現するには、既存の役割に基づいて、スコープが制限された役割を作成します。

<div>

## <a name="creating-a-scoped-role"></a>スコープ付き役割の作成

スコープを制限した役割 (スコープ付き役割) を作成する場合、スコープ、スコープ付き役割のベースとなる既存の役割、および役割を割り当てる Active Directory グループを指定します。 指定する Active Directory グループは事前に作成しておく必要があります。 次に、定義済みの管理役割のうちの 1 つの特権を持ち、スコープを制限した役割を作成するコマンドレットの例を示します。 という`Site01 Server Administrators`新しい役割が作成されます。 この役割には定義済みの CsServerAdministrator 役割の機能がありますが、Site01 サイトにあるサーバーのみが対象となります。 このコマンドレットが動作するには、Site01 サイトが既に定義されている必要`Site01 Server Administrators`があります。また、という名前のユニバーサルセキュリティグループが既に存在している必要があります。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

このコマンドレットを実行すると、 `Site01 Server Administrators`グループのメンバーであるすべてのユーザーは、Site01 のサーバーに対するサーバー管理者権限を持つことになります。 さらに、このユニバーサルセキュリティグループに後で追加されたユーザーも、この役割の権限を取得します。 役割自体と、それが割り当てられているユニバーサルセキュリティグループの両方が呼び出さ`Site01 Server Administrators`れることに注意してください。

次の例では、サーバー スコープではなくユーザー スコープを制限しています。 Sales 組織単位`Sales Users Administrator`のユーザーアカウントを管理するための役割を作成します。 このコマンドレットが動作するように、Salesユーザー管理者ユニバーサルセキュリティグループが既に作成されている必要があります。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>新規役割の作成

定義済みの役割に定義されていないコマンドレットのセットにアクセスする役割や、スクリプトまたはモジュールのセットにアクセスする役割を作成する場合も、定義済みの役割のいずれかをテンプレートとして使用します。役割で実行できるスクリプトおよびモジュールは、次の場所に保存しておく必要があります。

  - Lync\\モジュールパス (既定で C: Program Files\\Common Files\\Microsoft lync Server 2013\\モジュール Lync\\

  - ユーザースクリプト\\パス。既定では C: Program Files\\Common Files\\Microsoft Lync Server 2013\\adminscripts

新規役割を作成するには、**New-CsAdminRole** コマンドレットを使用します。 **新しい-CsAdminRole**を実行する前に、まず、この役割に関連付けられる基礎となるユニバーサルセキュリティグループを作成する必要があります。

新規役割を作成するコマンドレットの例を次に示します。 という名前`MyHelpDeskScriptRole`の新しい役割の種類を作成します。 新しい役割は、定義済みの CsHelpDesk 役割の機能を持っていますが、それに加えて "testscript" という名前のスクリプトで関数を実行することもできます。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

このコマンドレットが動作するためには、最初にユニバーサルセキュリティグループ Myhelpの Scriptrole を作成しておく必要があります。

このコマンドレットの実行後、ユーザーをこの役割に直接割り当てたり (この場合ユーザーのスコープはグローバルになります)、このドキュメントの「スコープ付き役割の作成」で説明したように、この役割に基づいてスコープ付き役割を作成したりできます。

</div>

<div>

## <a name="assigning-roles-to-users"></a>ユーザーへの役割の割り当て

各 Lync Server の役割は、基礎となる Active Directory ユニバーサルセキュリティグループに関連付けられています。 基礎となるグループに追加したユーザーには、その役割の機能が付与されます。

前のセクションの例では、新しい役割を作成し、既存のユニバーサルセキュリティグループを新しい役割に割り当てています。 既存の役割を 1 人以上のユーザーに割り当てるには、役割に関連付けられているグループにそれらのユーザーを追加します。 これらのグループには、個々のユーザーとユニバーサルセキュリティグループの両方を追加できます。

たとえば、 **Csadministrator**の役割は、Active Directory の**CS Administrators**ユニバーサルセキュリティグループに自動的に付与されます。 このユニバーサルセキュリティグループは、Lync Server の展開時に Active Directory 内に作成されます。 ユーザーまたはグループを **CS Administrators** グループに追加するだけでこの特権をユーザーまたはグループに付与できます。

各役割に対応する基礎となる Active Directory グループにユーザーを追加することで、複数の RBAC の役割をユーザーに付与できます。

役割を作成する場合、基礎となる Active Directory グループに後から追加されたユーザーにもその役割の機能が付与されることに注意してください。

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>役割の機能の変更

役割で実行できるコマンドレットおよびスクリプトのリストを変更できます。カスタムの役割では、実行できるコマンドレットとスクリプトの両方を変更できますが、定義済みの役割ではスクリプトのみを変更できます。入力する各コマンドレットで、コマンドレットまたはスクリプトを追加、削除したり、置き換えたりできます。

役割を変更するには、**Set-CsAdminRole** コマンドレットを使用します。 次のコマンドレットは、役割から1つのスクリプトを削除します。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>RBAC の計画

Lync Server 展開に対して何らかの管理者権限を与えられるユーザーごとに、実行する必要があるタスクを正確に検討し、その仕事に必要な最低限の特権と範囲を持つ役割に割り当てます。 必要に応じて **Set-CsAdminRole** コマンドレットを使用して、このユーザーのタスクに必要なコマンドレットのみを実行できる新しい役割を作成できます。

CsAdministrator の役割があるユーザーは、すべてのタイプの役割 (CsAdministrator に基づいた役割など) を作成し、その役割にユーザーを割り当てることができます。 CsAdministrator の役割は、信頼できる少数のユーザーに割り当てることをお勧めします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


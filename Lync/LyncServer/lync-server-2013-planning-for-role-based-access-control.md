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
ms.openlocfilehash: b89e4bdc075783d33bebcfb85398b1b627e1bf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Lync Server 2013 での役割ベースのアクセス制御の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-01-27_

セキュリティの高い標準を維持しながら、管理タスクの委任を可能にするために、Lync Server 2013 は役割ベースのアクセス制御 (RBAC) を提供しています。 RBAC では、管理者権限が付与され、管理者ロールにユーザーが割り当てられます。 Lync Server 2013 には、豊富な組み込みの管理者ロールが用意されています。また、新しいロールを作成して、新しい役割ごとにコマンドレットのカスタムリストを指定することもできます。 また、定義済み RBAC 役割およびカスタム RBAC 役割の許可されたタスクに、コマンドレットのスクリプトを追加することもできます。

<div>

## <a name="better-server-security-and-centralization"></a>サーバーのセキュリティと集中化の向上

RBAC では、アクセスと承認はユーザーの Lync Server の役割に基づいています。 これにより、"最低限の権限" というセキュリティ慣行を使用できるようになり、管理者とユーザーには、その職務に必要な権利のみが付与されます。

<div>


> [!IMPORTANT]  
> RBAC の制限は、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、リモートで作業している管理者に対してのみ機能します。 Lync Server を実行しているサーバーに座っているユーザーは、RBAC によって制限されません。 したがって、Lync Server の物理的なセキュリティは、RBAC の制限を維持することが重要です。



</div>

</div>

<div>

## <a name="roles-and-scope"></a>役割と範囲

RBAC では、特定の種類の管理者または技術者のために役立つように設計されたコマンドレットのリストを使用する*役割*が有効になります。 *スコープ*とは、役割で定義されているコマンドレットで操作できる一連のオブジェクトのことです。 範囲に影響を与えるオブジェクトは、ユーザーアカウント (組織単位でグループ化) または (サイトごとにグループ化された) いずれかにすることができます。

次の表に、Lync Server で定義されている役割と、各タスクの種類の概要を示します。 4番目の列には、各 Lync Server の役割に類似した Microsoft Exchange Server の役割 (存在する場合) が表示されます。

### <a name="predefined-administrative-roles"></a>定義済みの管理者ロール

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ロール</th>
<th>許可されたタスク</th>
<th>基になる Active Directory グループ</th>
<th>同等の交換</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>すべての管理タスクを実行し、ロールの作成やロールへのユーザーの割り当てなどのすべての設定を変更することができます。 新しいサイト、プール、およびサービスを追加して展開を展開できます。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>組織管理</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Lync Server のユーザーを有効または無効にしたり、ユーザーを移動したり、既存のポリシーをユーザーに割り当てることができます。 ポリシーを変更できません。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>メールの宛先</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>音声関連の設定とポリシーの作成、構成、管理を行うことができます。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>サーバーとサービスの管理、監視、トラブルシューティングを行うことができます。 サーバーへの新しい接続の禁止、サービスの停止と開始、ソフトウェアの更新プログラムの適用を行うことができます。 グローバル構成の影響を変更することはできません。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>サーバー管理</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>展開の正常性を監視するために、ユーザーやサーバーの情報などの展開を表示できます。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>表示のみの組織管理</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>ユーザーのプロパティやポリシーなどの展開を表示できます。 特定のトラブルシューティングタスクを実行できます。 ユーザーのプロパティやポリシー、サーバーの構成、またはサービスを変更することはできません。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>ヘルプデスク</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>アーカイブの構成とポリシーを変更できます。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>保持管理、法的保持</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>サイト内の応答グループアプリケーションの構成を管理できます。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>9-1-1 (E9) の管理を強化するための最小レベルの権限 (E9 の場所とネットワーク識別子の作成、および相互の関連付けを含む)。 この役割は、常にグローバルスコープに割り当てられます。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>特定の応答グループを管理できます。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>常設チャット機能と特定の常設チャットルームを管理できます。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>該当しない</p></td>
</tr>
</tbody>
</table>


Lync Server に組み込まれているすべての定義済みロールにはグローバルスコープがあります。 最低限の権限適用方法を実行するには、限定されたサーバーまたはユーザーのセットのみを管理する場合は、グローバル範囲の役割にユーザーを割り当てないでください。 これを実現するために、既存のロールに基づいているが、スコープが制限されているロールを作成できます。

<div>

## <a name="creating-a-scoped-role"></a>スコープ指定された役割の作成

制限されたスコープ (スコープ指定された役割) を持つ役割を作成する場合は、スコープを指定し、基になる既存の役割と、役割を割り当てられる Active Directory グループを指定します。 指定した Active Directory グループは、既に作成されている必要があります。 次のコマンドレットは、事前に定義されている管理者ロールの1つであるという権限を持ち、スコープが制限されている役割を作成する例です。 という`Site01 Server Administrators`新しい役割が作成されます。 この役割には、定義済みの CsServerAdministrator ロールの権限がありますが、Site01 サイトにあるサーバーに対してのみ機能します。 このコマンドレットが動作するためには、Site01 サイトが既に定義されており`Site01 Server Administrators` 、という名前のユニバーサルセキュリティグループが既に存在している必要があります。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

このコマンドレットを実行すると、 `Site01 Server Administrators`グループのメンバーになっているすべてのユーザーに、Site01 のサーバーのサーバー管理者権限が与えられます。 さらに、このユニバーサルセキュリティグループに後で追加されたすべてのユーザーも、この役割の権限を取得します。 役割自体と、それに割り当てられているユニバーサルセキュリティグループの両方が呼び出さ`Site01 Server Administrators`れます。

次の例では、サーバースコープの代わりにユーザーのスコープを制限しています。 営業組織単位`Sales Users Administrator`のユーザーアカウントを管理するための役割を作成します。 このコマンドレットが機能するためには、Salesて管理者のユニバーサルセキュリティグループが既に作成されている必要があります。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>新しい役割の作成

定義済みのロールのいずれにも含まれていない一連のコマンドレット、または一連のスクリプトまたはモジュールにアクセスできる役割を作成するには、あらかじめ定義されたいずれかのロールをテンプレートとして使用します。 ロールを実行できるスクリプトとモジュールは、次の場所に格納されている必要があることに注意してください。

  - Lync モジュールのパス (既定では\\C: Program files\\の共通ファイル\\Microsoft lync Server 2013\\モジュール\\Lync)

  - ユーザースクリプト\\パス (既定では C: Program Files\\Common files\\Microsoft Lync Server 2013\\adminscripts)

新しい役割を作成するには、**新しい-CsAdminRole**コマンドレットを使用します。 **新しい CsAdminRole**を実行する前に、この役割に関連付けられる、基になるユニバーサルセキュリティグループを作成する必要があります。

次のコマンドレットは、新しい役割の作成例として機能します。 これにより、という`MyHelpDeskScriptRole`新しい役割の種類が作成されます。 新しい役割には、定義済みの CsHelpDesk ロールの機能があり、"testscript" という名前のスクリプトでさらに関数を実行できます。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

このコマンドレットが動作するためには、まずユニバーサルセキュリティグループ Myhelpデスク Scriptrole を作成しておく必要があります。

このコマンドレットを実行した後、このロールにユーザーを直接割り当てる (その場合はグローバルスコープを持つ) か、このドキュメントの「スコープロールの作成」で説明したように、このロールに基づいてスコープ指定された役割を作成できます。

</div>

<div>

## <a name="assigning-roles-to-users"></a>ロールをユーザーに割り当てる

各 Lync Server の役割は、基になる Active Directory ユニバーサルセキュリティグループに関連付けられています。 基になるグループに追加したユーザーは、その役割の能力を獲得できます。

前のセクションの例では、新しい役割を作成し、既存のユニバーサルセキュリティグループを新しい役割に割り当てています。 既存の役割を1人または複数のユーザーに割り当てるには、その役割に関連付けられたグループにそれらのユーザーを追加します。 これらのグループには、個々のユーザーとユニバーサルセキュリティグループの両方を追加できます。

たとえば、 **Csadministrator**の役割は、Active Directory の**CS 管理者**のユニバーサルセキュリティグループに自動的に付与されます。 このユニバーサルセキュリティグループは、Lync Server を展開するときに Active Directory で作成されます。 ユーザーまたはグループにこの権限を付与するには、 **CS 管理者**グループに追加するだけです。

ユーザーには、各役割に対応する、基になる Active Directory グループに追加することで、複数の RBAC ロールを割り当てることができます。

ロールを作成すると、基になる Active Directory グループに後で追加されたユーザーにその役割の機能が与えられることに注意してください。

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>役割の権限を変更する

役割が実行できるコマンドレットとスクリプトの一覧は変更できます。 カスタムロールで実行できるコマンドレットとスクリプトの両方を変更することはできますが、定義済みのロールのスクリプトのみを変更できます。 入力する各コマンドレットでは、コマンドレットまたはスクリプトの追加、削除、置換を行うことができます。

役割を変更するには、 **Set-CsAdminRole**コマンドレットを使用します。 次のコマンドレットは、役割から1つのスクリプトを削除します。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>RBAC の計画

Lync Server の展開にどのような管理権限を付与するかについては、どのようなタスクを実行する必要があるかを正確に考慮し、その職務に必要な最低限の権限と範囲の役割を割り当てる必要があります。 必要に応じて、[ **Set-CsAdminRole** ] コマンドレットを使用して、このユーザーのタスクに必要なコマンドレットのみを含む新しい役割を作成することができます。

CsAdministrator ロールを持っているユーザーは、CsAdministrator に基づくロールを含むすべての種類の役割を作成し、ユーザーを割り当てることができます。 ベストプラクティスとして、CsAdministrator の役割を、非常に少数の信頼できるユーザーに割り当てることをお勧めします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


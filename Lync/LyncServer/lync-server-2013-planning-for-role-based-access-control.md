---
title: 'Lync Server 2013: 役割ベースのアクセス制御の計画'
TOCTitle: 役割ベースのアクセス制御 (RBAC) の計画
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48271877
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での役割ベースのアクセス制御の計画

 

_**トピックの最終更新日:** 2015-03-09_

高レベルのセキュリティを維持しながら管理タスクを委任できるようにするため、Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を提供しています。RBAC では、ユーザーを管理役割に割り当てることによって管理特権を付与します。Lync Server 2013 には、豊富な組み込み管理役割のセットが用意されているほか、新しい役割を作成して、新規の各役割に対してコマンドレットのカスタム リストを指定することもできます。また、定義済み RBAC 役割およびカスタム RBAC 役割の許可されたタスクに、コマンドレットのスクリプトを追加することもできます。

## 優れたサーバー セキュリティと集中管理

RBAC では、ユーザーの Lync Server の役割に厳密に基づいてアクセスが許可され、承認が行われます。これにより、管理者およびユーザーに各自の業務に必要な権限のみを付与するセキュリティ プラクティス ("最小限の特権") を利用できます。


> [!IMPORTANT]
> RBAC では、Lync Server コントロール パネルまたは Lync Server 管理シェルのどちらかを使用してリモートで作業する管理者の操作のみを制限します。Lync Server を実行しているサーバーを直接操作するユーザーは RBAC によって制限されません。そのため、RBAC による制限を有効なものにするには、Lync Server の物理的なセキュリティが重要です。



## 役割とスコープ

RBAC において、ある*役割*に属するユーザーは、特定のタイプの管理者または技術者用に定義された一連のコマンドレットを使用できます。*スコープ*は、役割で定義されているコマンドレットで操作できる一連のオブジェクトです。スコープの影響を受けるオブジェクトは、ユーザー アカウント (組織単位でグループ化) またはサーバー (サイト単位でグループ化) のどちらかです。

次の表に、Lync Server の定義済みの役割と、各役割で実行できるタスクのタイプの概要を示します。4 番目の列には、Lync Server の各役割に類似する Microsoft Exchange Server の役割を示します (存在する場合)。

### 定義済みの管理役割

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>[役割]</th>
<th>実行可能なタスク</th>
<th>基礎となる Active Directory グループ</th>
<th>対応する Exchange Server の役割</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>すべての管理タスクの実行とすべての設定の変更ができます。これには、役割の作成や役割へのユーザーの割り当ても含まれます。新しいサイト、プール、およびサービスを追加して展開を拡張できます。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organization Management</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Lync Server のユーザーの有効化と無効化、ユーザーの移動、およびユーザーへの既存のポリシーの割り当てを実行できます。ポリシーは変更できません。</p></td>
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
<td><p>サーバーやサービスを管理、監視、およびトラブルシューティングできます。サーバーへの新しい接続を禁止したり、サービスを停止および開始したり、ソフトウェア更新プログラムを適用したりできます。グローバル構成に影響する変更はできません。</p></td>
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
<td><p>ユーザーのプロパティやポリシーを含む展開を表示できます。特定のトラブルシューティング タスクを実行できます。ユーザーのプロパティやポリシー、サーバー構成、またはサービスは変更できません。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>HelpDesk</p></td>
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
<td><p>Enhanced 9-1-1 (E9-1-1) を管理するための最低レベルの権限。E9-1-1 の場所とネットワーク識別子の作成、およびこれらの相互関連付けが含まれます。この役割は必ずグローバル スコープに関連付けられます。</p></td>
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
<tr class="even">
<td><p>CsAdministrator</p></td>
<td><p>すべての管理タスクの実行とすべての設定の変更ができます。これには、役割の作成や役割へのユーザーの割り当ても含まれます。新しいサイト、プール、およびサービスを追加して展開を拡張できます。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Organization Management</p></td>
</tr>
<tr class="odd">
<td><p>CsUserAdministrator</p></td>
<td><p>Lync Server のユーザーの有効化と無効化、ユーザーの移動、およびユーザーへの既存のポリシーの割り当てを実行できます。ポリシーは変更できません。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mail Recipients</p></td>
</tr>
<tr class="even">
<td><p>CsVoiceAdministrator</p></td>
<td><p>音声関連の設定やポリシーを作成、構成、および管理できます。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>CsServerAdministrator</p></td>
<td><p>サーバーやサービスを管理、監視、およびトラブルシューティングできます。サーバーへの新しい接続を禁止したり、サービスを停止および開始したり、ソフトウェア更新プログラムを適用したりできます。グローバル構成に影響する変更はできません。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Management</p></td>
</tr>
<tr class="even">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>展開の状態を監視するためにユーザーやサーバーの情報を含む展開を表示できます。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>View-Only Organization Management</p></td>
</tr>
<tr class="odd">
<td><p>CsHelpDesk</p></td>
<td><p>ユーザーのプロパティやポリシーを含む展開を表示できます。特定のトラブルシューティング タスクを実行できます。ユーザーのプロパティやポリシー、サーバー構成、またはサービスは変更できません。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>HelpDesk</p></td>
</tr>
<tr class="even">
<td><p>CsArchivingAdministrator</p></td>
<td><p>アーカイブ構成およびポリシーを変更できます。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Retention Management, Legal Hold</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>サイト内の応答グループ アプリケーションの構成を管理できます。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>CsLocationAdministrator</p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) を管理するための最低レベルの権限。E9-1-1 の場所とネットワーク識別子の作成、およびこれらの相互関連付けが含まれます。この役割は必ずグローバル スコープに関連付けられます。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupManager</p></td>
<td><p>特定の応答グループを管理できます。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>常設チャット機能および特定の常設チャット ルームを管理できます。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>該当なし</p></td>
</tr>
</tbody>
</table>


Lync Server に付属するすべての定義済み役割のスコープはグローバルになっています。最小限の特権のプラクティスを実施するには、限定的なサーバーやユーザーのセットのみを管理するユーザーに対して、グローバル スコープを持つ役割を割り当てないようにする必要があります。これを実現するには、既存の役割に基づいて、スコープが制限された役割を作成します。

## スコープ付き役割の作成

スコープを制限した役割 (スコープ付き役割) を作成する場合、スコープ、スコープ付き役割のベースとなる既存の役割、および役割を割り当てる Active Directory グループを指定します。指定する Active Directory グループは事前に作成しておく必要があります。次に、定義済みの管理役割のうちの 1 つの特権を持ち、スコープを制限した役割を作成するコマンドレットの例を示します。このコマンドレットでは、`Site01 Server Administrators` という新しい役割が作成されます。この役割には定義済みの CsServerAdministrator 役割の機能がありますが、Site01 サイトにあるサーバーのみが対象となります。このコマンドレットが機能するには、Site01 サイトが定義されていて、`Site01 Server Administrators` という名前のユニバーサル セキュリティ グループが既に存在している必要があります。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

このコマンドレットを実行すると、`Site01 Server Administrators` グループのメンバーであるすべてのユーザーに Site01 のサーバーのサーバー管理者特権が付与されます。また、このユニバーサル セキュリティ グループに後で追加されるユーザーにもこの役割の特権が付与されます。役割自体も、役割が割り当てられているユニバーサル セキュリティ グループも `Site01 Server Administrators` という名前であることに注意してください。

次の例では、サーバー スコープではなくユーザー スコープを制限しています。この例では、Sales 組織単位のユーザー アカウントを管理する `Sales Users Administrator` という役割を作成しています。このコマンドレットが機能するには、SalesUsersAdministrator ユニバーサル セキュリティ グループが既に作成されている必要があります。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

## 新規役割の作成

定義済みの役割に定義されていないコマンドレットのセットにアクセスする役割や、スクリプトまたはモジュールのセットにアクセスする役割を作成する場合も、定義済みの役割のいずれかをテンプレートとして使用します。役割で実行できるスクリプトおよびモジュールは、次の場所に保存しておく必要があります。

  - Lync モジュール パス (既定で C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync)

  - ユーザー スクリプト パス (既定で C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts)

新規役割を作成するには、**New-CsAdminRole** コマンドレットを使用します。 **New-CsAdminRole** を実行する前に、この役割に関連付ける、基礎となるユニバーサル セキュリティ グループを作成しておく必要があります。

新規役割を作成するコマンドレットの例を次に示します。このコマンドレットでは、`MyHelpDeskScriptRole` という新しい役割が作成されます。新しい役割は、定義済みの CsHelpDesk 役割の機能を持っていますが、それに加えて "testscript" という名前のスクリプトで関数を実行することもできます。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

このコマンドレットが動作するためには、ユニバーサル セキュリティ グループ MyHelpDeskScriptRole を作成しておく必要があります。

このコマンドレットの実行後、ユーザーをこの役割に直接割り当てたり (この場合ユーザーのスコープはグローバルになります)、このドキュメントの「スコープ付き役割の作成」で説明したように、この役割に基づいてスコープ付き役割を作成したりできます。

## ユーザーへの役割の割り当て

各 Lync Server 役割は、基礎となる Active Directory ユニバーサル セキュリティ グループに関連付けられます。基礎となるグループに追加したユーザーには、その役割の機能が付与されます。

前のセクションの例では、新しい役割を作成し、その新規役割に既存のユニバーサル セキュリティ グループを割り当てました。既存の役割を 1 人以上のユーザーに割り当てるには、役割に関連付けられているグループにそれらのユーザーを追加します。これらのグループには、個別のユーザーおよびユニバーサル セキュリティ グループの両方を追加できます。

たとえば、**CsAdministrator** の役割は、Active Directory の **CS Administrators** ユニバーサル セキュリティ グループに自動的に付与されます。このユニバーサル セキュリティ グループは、Lync Server を展開するときに Active Directory で作成されます。ユーザーまたはグループを **CS Administrators** グループに追加するだけでこの特権をユーザーまたはグループに付与できます。

各役割に対応する基礎となる Active Directory グループにユーザーを追加することで、複数の RBAC の役割をユーザーに付与できます。

役割を作成する場合、基礎となる Active Directory グループに後から追加されたユーザーにもその役割の機能が付与されることに注意してください。

## 役割の機能の変更

役割で実行できるコマンドレットおよびスクリプトのリストを変更できます。カスタムの役割では、実行できるコマンドレットとスクリプトの両方を変更できますが、定義済みの役割ではスクリプトのみを変更できます。入力する各コマンドレットで、コマンドレットまたはスクリプトを追加、削除したり、置き換えたりできます。

役割を変更するには、**Set-CsAdminRole** コマンドレットを使用します。次のコマンドレットでは役割の機能からスクリプトを 1 つ削除しています。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

## RBAC の計画

Lync Server の展開で何らかの管理者権限が付与されるユーザーごとに、実行する必要のあるタスクを考慮して、その業務に必要な最低限の特権とスコープがある役割に割り当てます。必要に応じて **Set-CsAdminRole** コマンドレットを使用して、このユーザーのタスクに必要なコマンドレットのみを実行できる新しい役割を作成できます。

CsAdministrator の役割があるユーザーは、すべてのタイプの役割 (CsAdministrator に基づいた役割など) を作成し、その役割にユーザーを割り当てることができます。CsAdministrator の役割は、信頼できる少数のユーザーに割り当てることをお勧めします。


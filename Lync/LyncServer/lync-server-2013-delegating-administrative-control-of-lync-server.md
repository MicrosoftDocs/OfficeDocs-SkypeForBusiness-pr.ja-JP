---
title: 'Lync Server 2013: Lync Server の管理機能の委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2acecec7a4b6543bb5dd22720af7a3f9aab62137
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Lync Server 2013 の管理機能の委任

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

Lync Server 2013 では、新しいロールベースのアクセス制御 (RBAC) 機能を使用して、管理タスクがユーザーに委任されます。 Lync Server をインストールすると、複数の RBAC の役割が作成されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 たとえば、RBAC の役割 CsHelpDesk は、Active Directory ドメインサービスの Users コンテナーに含まれる CsHelpDesk グループに対応しています。 さらに、各 RBAC の役割は、Lync Server Windows PowerShell コマンドレットのセットと関連付けられています。 これらのコマンドレットは、特定の RBAC の役割が割り当てられたユーザーが実行できるタスクを表します。 たとえば、CsHelpDesk role には、Lock と UnlockCsClientPin コマンドレットが割り当てられています。 つまり、CsHelpDesk の役割が割り当てられているユーザーは、ユーザーの PIN 番号のロックとロック解除を行うことができます。 ただし、CsHelpDesk の役割には、CsVoicePolicy コマンドレットが割り当てられていません。 つまり、CsHelpDesk role を割り当てられているユーザーは、新しいボイスポリシーを作成することはできません。

<div>

## <a name="viewing-information-about-rbac-roles"></a>RBAC ロールに関する情報を表示する

次のコマンドを Lync Server 管理シェルから実行して、RBAC の役割に関する基本的な情報を取得できます。

    Get-CsAdminRole

RBAC の役割 (CsVoiceAdministrator など) の Id は、Active Directory ドメインサービスの Users コンテナーにあるセキュリティグループに直接マッピングされていることに注意してください。

ロールに割り当てられているコマンドレットの一覧を表示するには、次のようなコマンドを使用します。

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>RBAC の役割をユーザーに割り当てる

RBAC の役割をユーザーに割り当てるには、適切な Active Directory セキュリティグループにそのユーザーを追加する必要があります。 たとえば、CsLocationAdministrator の役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。 そのためには、次の手順を実行します。

**セキュリティグループにユーザーを割り当てるには**

1.  Active Directory グループのメンバーシップを変更する権限を持つアカウントを使用して、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。

2.  [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。

3.  Active Directory ユーザーとコンピューターで、ドメインの名前を展開し、[**ユーザー** ] コンテナーをクリックします。

4.  セキュリティグループ**Cslocationadministrator 者**を右クリックし、[**プロパティ**] をクリックします。

5.  [**プロパティ**] ダイアログボックスの [**メンバー** ] タブで、[**追加**] をクリックします。

6.  **[ユーザー、コンピューター、連絡先、またはグループの選択**] ダイアログボックスで、 **[選択するオブジェクト名を入力**してください] ボックスに、グループに追加するユーザー名またはユーザー名 ( **Ken Myer**など) を入力し、[ **OK]** をクリックします。

7.  [**プロパティ**] ダイアログボックスで、[ **OK]** をクリックします。

RBAC の役割が割り当てられていることを確認するには、ユーザーの "SamAccountName (Active Directory のログオン名)" というコマンドレットを渡して、 [Csadminadminroleassignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment)コマンドレットを使います。 たとえば、Lync Server 管理シェルで次のコマンドを実行します。

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


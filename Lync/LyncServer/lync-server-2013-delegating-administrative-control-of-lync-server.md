---
title: 'Lync Server 2013: Lync Server の管理制御の委任'
description: 'Lync Server 2013: Lync Server の管理制御を委任します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567493"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a>Lync Server 2013 の管理制御の委任

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

Lync Server 2013 では、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、管理タスクがユーザーに委任されます。 Lync Server をインストールすると、いくつかの RBAC の役割が作成されます。 これらの役割は、Active Directory ドメインサービスのユニバーサルセキュリティグループに対応します。 たとえば、RBAC 役割 CsHelpDesk は、Active Directory ドメインサービスの Users コンテナーにある CsHelpDesk グループに対応します。 さらに、各 RBAC の役割は、Lync Server Windows PowerShell コマンドレットのセットに関連付けられています。 これらのコマンドレットは、特定の RBAC の役割が割り当てられているユーザーが実行できるタスクを表します。 たとえば、CsHelpDesk 役割には Lock-CsClientPin コマンドレットと UnlockCsClientPin コマンドレットが割り当てられています。 これは、CsHelpDesk の役割が割り当てられているユーザーが、ユーザーの PIN 番号をロックおよびロック解除できることを意味します。 ただし、CsHelpDesk の役割には New-CsVoicePolicy コマンドレットが割り当てられていません。 これは、CsHelpDesk 役割が割り当てられているユーザーが新しい音声ポリシーを作成できないことを意味します。

<div>

## <a name="viewing-information-about-rbac-roles"></a>RBAC の役割に関する情報の表示

RBAC の役割に関する基本的な情報を取得するには、Lync Server 管理シェルから次のコマンドを実行します。

    Get-CsAdminRole

RBAC の役割 (CsVoiceAdministrator など) の Id は、Active Directory ドメインサービスのユーザーコンテナーにあるセキュリティグループに直接マッピングされていることに注意してください。

役割に割り当てられているコマンドレットのリストを表示するには、次のようなコマンドを使用してください。

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>ユーザーへの RBAC の役割の割り当て

RBAC の役割をユーザーに割り当てるには、そのユーザーを適切な Active Directory セキュリティグループに追加する必要があります。 たとえば、CsLocationAdministrator 役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。 ユーザーをセキュリティ グループに追加するには、次の手順を実行します。

**ユーザーをセキュリティ グループに割り当てるには**

1.  Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。

2.  [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックし、[**Active Directory ユーザーおよびコンピューター**] をクリックします。

3.  Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[**Users**] コンテナーをクリックします。

4.  セキュリティ グループの [**CsLocationAdministrator**] を右クリックし、[**プロパティ**] をクリックします。

5.  [**プロパティ**] ダイアログ ボックスの [**メンバー**] タブで、[**追加**] をクリックします。

6.  [**ユーザー、コンピューター、連絡先、またはグループの選択**] ダイアログ ボックスの [**選択するオブジェクト名を入力してください**] ボックスにグループに追加するユーザーの名前または表示名 (たとえば、**Ken Myer**) を入力して [**OK**] をクリックします。

7.  [**プロパティ**] ダイアログ ボックスで [**OK**] をクリックします。

RBAC の役割が割り当てられていることを確認するには、ユーザーの SamAccountName (Active Directory ログオン名) をコマンドレットに渡して、 [Get-help Adminroleassignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) コマンドレットを使用します。 たとえば、Lync Server 管理シェルで次のコマンドを実行します。

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


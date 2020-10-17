---
title: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている'
description: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545163"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-19_

ロックダウンされた Active Directory ドメインサービスでは、アクセス許可の継承が無効になっている特定の組織単位 (Ou) にユーザーとコンピューターのオブジェクトが配置されることが多く、セキュリティポリシーを適用するために、グループポリシーオブジェクト (Gpo) の使用を有効にするために役立ちます。

ドメインの準備とサーバーのアクティブ化 Lync Server 2013 によって必要とされるアクセス制御エントリ (Ace) を設定します。 アクセス許可の継承が無効になっている場合、Lync Server のセキュリティグループはこれらの Ace を継承できません。 これらのアクセス許可が継承されていない場合、Lync Server のセキュリティグループは設定にアクセスできず、次の2つの問題が発生します。

  - ユーザー、InetOrgPersons、および連絡先を管理し、サーバーを運用するには、Lync Server のセキュリティグループに、各ユーザーのプロパティセット、リアルタイム通信 (RTC)、RTC ユーザー検索、およびパブリック情報に関するドメインの準備手順によって設定された Ace が必要です。 アクセス許可の継承が無効になっている場合、これらの ACE がセキュリティ グループに継承されないので、サーバーまたはユーザーを管理することができません。

  - サーバーとプールを検出するために、Lync Server を実行しているサーバーは、Microsoft Container および Server オブジェクトを含む、コンピューターに関連するオブジェクトのアクティブ化によって設定された Ace に依存しています。 アクセス許可の継承が無効になると、セキュリティ グループ、サーバー、プールがこれらの ACE を継承しないため、ACE を利用できなくなります。

これらの問題に対処するために、Lync Server は **Grant-CsOuPermission** コマンドレットを提供します。 このコマンドレットでは、指定したコンテナーと組織単位、およびコンテナーまたは組織単位内のオブジェクトに対して、必要な Lync Server Ace を直接設定します。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>ドメインの準備手続き以後のユーザー、InetOrgPerson、および連絡先オブジェクトに対するアクセス許可の設定

ロックダウンされた Active Directory 環境では、アクセス許可の継承が無効になるため、ドメインの準備手続きの中で、ドメイン内のユーザー オブジェクトや InetOrgPerson オブジェクトを収容するコンテナーまたは組織単位に必要な ACE が設定されません。 このような状況では、アクセス許可の継承が無効になっているユーザー オブジェクトや InetOrgPerson オブジェクトを収容する各コンテナーまたは OU に対して **Grant-CsOuPermission** コマンドレットを実行する必要があります。 展開形態が中央フォレスト トポロジの場合は、連絡先オブジェクトを収容するコンテナーまたは OU に対しても、この手続きを実施する必要があります。 中央フォレストトポロジの詳細については、「サポート」のドキュメントの「supported [Active Directory トポロジ (Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) )」を参照してください。 ObjectType パラメーターは、オブジェクト タイプを指定します。 OU パラメーターは組織単位を指定します。

このコマンドレットは、指定したコンテナーまたは OU、およびそのコンテナー内のユーザー オブジェクトまたは InetOrgPerson オブジェクトで、必要な ACE を直接追加します。 このコマンドが実行される OU に、ユーザーオブジェクトまたは InetOrgPerson オブジェクトを持つ子 Ou がある場合、アクセス許可はそれらに適用されません。 各子 OU でコマンドを個別に実行する必要があります。 これは、Lync ホスティング展開の一般的なシナリオです。たとえば、親 OU = OCS テナント、DC = CONTOSO、DC = ローカルおよび子 OU = Tenant1、OU = OCS テナント、DC = CONTOSO、DC = ローカルです。

このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。 認証済みユーザーの Ace がロックダウンされた環境でも削除されている場合は、「 [認証済みユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md) されているか、または Enterprise Admins グループのメンバーであるアカウントを使用しています。

**ユーザー、InetOrgPerson、および連絡先オブジェクトに必要な ACE を設定するには**

1.  Domain Admins グループのメンバー アカウントか、それと同等のユーザー権限を持つアカウントを使用して、ドメインに参加しているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。
    
    次にその例を示します。
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  ログファイルで、 **\<Success\>** 各タスクの最後にある実行結果を検索して、アクセス許可が設定されていることを確認してから、[ログ] ウィンドウを閉じます。 次のコマンドで、アクセス許可が設定されたかどうかを調べることもできます。
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    次にその例を示します。
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>ドメイン準備手続き以後のコンピューター オブジェクトに対するアクセス許可の設定

ロックダウンされた Active Directory 環境ではアクセス許可の継承が無効になるため、ドメインの準備では、ドメイン内のコンピューター オブジェクトを収容するコンテナーまたは OU で必要な ACE が設定されません。 このような状況では、アクセス許可の継承が無効になっている、Lync Server を実行しているコンピューターがある各コンテナーまたは OU で **Grant-CsOuPermission** コマンドレットを実行する必要があります。 ObjectType パラメーターは、オブジェクト タイプを指定します。

この手続きを実行すると、必要な ACE が、指定したコンテナーに直接追加されます。

このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。 認証済みユーザーの Ace も削除されている場合は、「 [認証済みユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md) されているか、Enterprise Admins グループのメンバーであるアカウントを使用しています」の説明に従って、フォレストルートドメイン内の関連するコンテナーに対して、このアカウントに読み取りアクセス ace を付与する必要があります

**コンピューター オブジェクトに必要な ACE を設定するには**

1.  Domain Admins グループのメンバー アカウント、またはそれと同等のユーザー権限を持つアカウントを使用して、ドメインのコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。
    
    次にその例を示します。
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  ログファイル C: LogsOUPermissions.xml の例では \\ \\ 、 **\<Success\>** 各タスクの最後に実行結果を検索し、エラーがないことを確認してからログを閉じます。 次のコマンドレットを実行してアクセス許可をテストできます。
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    次にその例を示します。
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > ロックダウンされた Active Directory 環境で、フォレストのルートドメインでドメインの準備を実行する場合は、Lync Server に Active Directory スキーマおよび構成コンテナーへのアクセスが必要であることに注意してください。<BR>既定の認証済みユーザーのアクセス許可がスキーマまたは AD DS の構成コンテナーから削除された場合は、 &nbsp; スキーマ管理者グループ (スキーマコンテナーの場合) または Enterprise Admins グループ (構成コンテナーの場合) のメンバーのみが、指定したコンテナーにアクセスできます。 Setup.exe、Lync Server 管理シェルコマンドレット、および Lync Server コントロールパネルでは、これらのコンテナーにアクセスする必要があるため、インストールを実行しているユーザーがスキーマ管理者と Enterprise Admins グループのメンバーシップに相当するユーザー権限を持っていない限り、管理ツールのセットアップとインストールは失敗します。<BR>この状況に対処するには、RTCUniversalGlobalWriteGroup グループに、スキーマ コンテナーと構成コンテナーへの読み取りおよび書き込みアクセス権を与える必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


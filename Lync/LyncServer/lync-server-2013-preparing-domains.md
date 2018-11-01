---
title: 'Lync Server 2013: ドメインの準備'
TOCTitle: ドメインの準備
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48272851
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のドメインの準備

 

_**トピックの最終更新日:** 2012-10-29_

ドメインの準備は、Lync Server 2013 用の Active Directory ドメイン サービス を準備する際の最後のステップです。ドメインの準備のステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を付与するユニバーサル グループに対して、必要なアクセス制御エントリ (ACE) を追加します。ACE は、ドメイン ルートと 3 つの組み込みコンテナー (User、Computers、および Domain Controllers) に対して作成されます。

ドメインの準備は、Lync Server を展開しているドメイン内の任意のコンピューターで実行できます。Lync Server またはユーザーをホストするすべてのドメインを準備する必要があります。

組織において、アクセス許可の継承が無効になっているか、認証ユーザーのアクセス許可が無効になっている場合は、ドメインの準備で追加のステップを実行する必要があります。詳細については、「[Lync Server 2013 でのロックダウンされた Active Directory ドメイン サービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) ではなく、組織単位 (OU) を使用している場合は、Authenticated Users グループに OU の読み取りアクセス許可を付与する必要があります。 ドメインの準備には、コンテナーの読み取りアクセス許可が必要です。 Authenticated Users グループに OU の読み取りアクセス許可が付与されていない場合は、次のコード例に示すように、**Grant-CsOuPermission** コマンドレットを実行して各 OU の読み取りアクセス許可を付与します。

    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 

   &nbsp;

    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"

**Grant-CsOuPermission** コマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。


> [!TIP]
> ドメイン ルートと、Users、Computers、Domain Controllers の各コンテナーに作成された ACE の詳細については、「<A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 でのドメインの準備によって加えられる変更</A>」を参照してください。



## このセクション中

  - [Lync Server 2013 のドメイン準備手続き](lync-server-2013-running-domain-preparation.md)

  - [Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)


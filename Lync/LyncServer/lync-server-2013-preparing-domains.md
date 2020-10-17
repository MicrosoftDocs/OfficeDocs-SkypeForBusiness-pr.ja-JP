---
title: 'Lync Server 2013: ドメインの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a37c365732785198e45a546f2352c51ccb42f9dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506944"
---
# <a name="preparing-domains-for-lync-server-2013"></a>Lync Server 2013 のドメインの準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

「ドメインの準備」は、Lync Server 2013 用の Active Directory ドメインサービスを準備するための最後の手順です。 ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。 ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。

Lync Server を展開しているドメイン内の任意のコンピューターで、ドメインの準備を実行できます。 Lync Server またはユーザーをホストするすべてのドメインを準備する必要があります。

組織において、アクセス許可の継承が無効になっているか、認証ユーザーのアクセス許可が無効になっている場合は、ドメインの準備で追加のステップを実行する必要があります。 詳細については、「 [Lync Server 2013 のロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) ではなく、組織単位 (OU) を使用している場合は、Authenticated Users グループに OU の読み取りアクセス許可を付与する必要があります。 ドメインの準備には、コンテナーの読み取りアクセス許可が必要です。 Authenticated Users グループに OU の読み取りアクセス許可が付与されていない場合は、次のコード例に示すように、**Grant-CsOuPermission** コマンドレットを実行して各 OU の読み取りアクセス許可を付与します。

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

**Grant-CsOuPermission**コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

<div class="">


> [!TIP]  
> ドメインルートと、Users、Computers、Domain Controllers の各コンテナーに作成された Ace の詳細については、「 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 のドメインの準備で行われた変更</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のドメインの準備を実行する](lync-server-2013-running-domain-preparation.md)

  - [Lync Server 2013 のコマンドレットを使用してドメインの準備を元に戻す](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


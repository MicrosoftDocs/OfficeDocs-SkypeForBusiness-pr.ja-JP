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
ms.openlocfilehash: 20a6897ae45964f3f179e951916dfb6bf7180641
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Lync Server 2013 のドメインの準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

ドメインの準備は、Lync Server 2013 用の Active Directory ドメインサービスの準備での最終的な手順です。 ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。 ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。

ドメインの準備は、Lync Server を展開しているドメイン内の任意のコンピューターで実行できます。 Lync サーバーまたはユーザーをホストするすべてのドメインを準備する必要があります。

権限の継承が無効になっているか、認証されたユーザー権限が組織で無効になっている場合は、ドメインの準備中に追加の手順を実行する必要があります。 詳細については、「 [Lync Server 2013 のロックダウン Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

組織で、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) ではなく組織単位 (OU) を使用している場合は、認証されたユーザーグループの Ou への読み取りアクセス許可を付与する必要があります。 ドメインの準備には、コンテナーへの読み取りアクセス権が必要です。 認証されたユーザーグループが OU への読み取りアクセス権を持っていない場合は、次のコード例に示すように**Grant Grant Oupermission**コマンドレットを実行して、各 ou の読み取りアクセス許可を付与します。

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

**Grant-CsOuPermission**コマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

<div class="">


> [!TIP]  
> ドメインルートで作成された Ace と、[ユーザー]、[コンピューター]、[ドメインコントローラー] の各コンテナーについて詳しくは、「 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 でのドメインの準備によって行われた変更</A>」をご覧ください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 のドメイン準備手続き](lync-server-2013-running-domain-preparation.md)

  - [Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


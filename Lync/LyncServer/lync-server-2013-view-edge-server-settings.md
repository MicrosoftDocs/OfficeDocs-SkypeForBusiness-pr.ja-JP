---
title: 'Lync Server 2013: エッジサーバーの設定の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e978e28ea2c9d64a842c40237f1e5943c30d0a41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Lync Server 2013 でのエッジサーバーの設定の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-20_

一般的なエッジサーバー構成は、構成管理データベース内のデータに対して確認する必要があります。これは、定義された変更管理手順に従ってすべての変更が記録されていることを保証するためです。

その他のチェックには、以下のセクションで説明するものが含まれます。

<div>

## <a name="verify-the-allow-and-block-lists"></a>許可/禁止リストを確認する

リストされている名前空間が有効かどうかを確認するには、フェデレーションドメインの SIP URI "Allow" および "Block" リストを確認します。

許可またはブロックされたリストを表示するには、Windows PowerShell を使用します。 許可されたドメインの一覧でドメインを確認するには、次の Windows PowerShell コマンドを実行します。

`Get-CsAllowedDomain`

このコマンドは、許可されたドメインリストのドメインについて、次のような情報を返します。

Identity: contoso.com

ドメイン: contoso.com

ProxyFqdn

Comment

MarkForMonitoring: False

Comment

禁止ドメインリストのドメインを確認するには、次のコマンドを使用します。

`Get-CsBlockedDomain`

その後、ブロックされた各ドメインについて、次のような情報を受信することになります。

Identity: tailspintoys.com

ドメイン: tailspintoys.com

また、Windows PowerShell では、許可されたドメインリストのドメインに接続できることを確認することもできます。 たとえば、次のコマンドは、エッジサーバー (TargetFqdn) とフェデレーションドメイン contoso.com の間の接続を確認します。

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

次のコマンドを実行すると、エッジサーバーと、許可されたドメインの一覧にあるすべてのドメインとの間の接続が確認されます。

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>複数のエッジサーバーが同一であることを確認する

複数のエッジサーバーが負荷分散アレイに展開されている場合は、アレイ内のすべてのエッジサーバーが同じ方法で構成されていることを確認することをお勧めします。

エッジサーバーの設定は、[コンピューターの管理] スナップインの [Lync Server 2013] 拡張機能の詳細ウィンドウで確認できます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-csblockeddomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


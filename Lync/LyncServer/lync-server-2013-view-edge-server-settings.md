---
title: 'Lync Server 2013: エッジサーバーの設定を表示する'
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
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Lync Server 2013 でエッジサーバーの設定を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-20_

一般的なエッジサーバー構成は、構成管理データベースのデータに対して検証する必要があります。これにより、すべての変更が、定義された変更管理手順に従って文書化されていることを保証できます。

追加のチェックには、次のセクションで説明されているようなものが含まれる場合があります。

<div>

## <a name="verify-the-allow-and-block-lists"></a>許可/禁止リストを確認する

リストされた名前空間が有効であるかどうかを判断するには、フェデレーションドメインの SIP URI "Allow" および "Block" リストを確認します。

Windows PowerShell を使用して、許可リストとブロックリストを表示できます。 [許可ドメイン] リストのドメインを確認するには、次の Windows PowerShell コマンドを実行します。

`Get-CsAllowedDomain`

このコマンドは、許可ドメインリストのドメインについて、次のような情報を返します。

Id: contoso.com

Domain: contoso.com

ProxyFqdn:

注釈

マークフォーム Onitor: False

注釈

ブロックドメインリストのドメインを確認するには、次のコマンドを使用します。

`Get-CsBlockedDomain`

次に、ブロックした各ドメインについて、次のような情報を受け取ります。

Id: tailspintoys.com

Domain: tailspintoys.com

Windows PowerShell でも、許可ドメインリストのドメインに接続できるかどうかを確認することができます。 たとえば、次のコマンドは、Edge サーバー (TargetFqdn) とフェデレーションドメイン contoso.com の間の接続を確認します。

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

このコマンドを実行すると、エッジサーバーと、許可ドメインの一覧で見つかったすべてのドメインの間の接続が確認されます。

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>複数のエッジサーバーが同じであることを確認する

負荷分散アレイに複数のエッジサーバーが展開されている場合は、配列内のすべてのエッジサーバーが同じ方法で構成されていることを確認することをお勧めします。

[コンピューターの管理] スナップイン用の Lync Server 2013 拡張機能の詳細ウィンドウで、エッジサーバーの設定を表示できます。

</div>

<div>

## <a name="see-also"></a>関連項目


[購入-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[テスト-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


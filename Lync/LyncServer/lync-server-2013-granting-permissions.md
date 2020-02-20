---
title: 'Lync Server 2013: アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc725122005793790344544575fa4456d742c88d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Lync Server 2013 でのアクセス許可の付与

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-15_

セットアップの場合は、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループに対するアクセス許可を付与して、その OU の RTCUniversalServerAdmins グループのメンバーが、指定したドメインに Lync Server 2013 をインストールできるようにすることができます。 OU に対するアクセス許可を付与する場合は、次のアクセス許可が付与されます。

  - 読み取り

  - 書き込み

  - ReadSPN

  - WriteSPN

管理のために、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーでなくても Ou にアクセスできるように、指定された Ou にアクセス許可を追加できます。 指定した OU に追加されるアクセス許可は、[有効にする] **-CsAdDomain**コマンドレットがコンピューターとユーザーの ou コンテナーに追加するアクセス許可と同じです。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのセットアップのアクセス許可の付与](lync-server-2013-granting-setup-permissions.md)

  - [Lync Server 2013 での組織単位アクセス許可の付与](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


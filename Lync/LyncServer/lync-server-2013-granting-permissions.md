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
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Lync Server 2013 でのアクセス許可の付与

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-15_

セットアップの場合、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループにアクセス許可を付与し、その OU の RTCUniversalServerAdmins グループのメンバーが、指定したドメインに Lync Server 2013 をインストールできるようにすることができます。 OU にアクセス許可を付与すると、次のアクセス許可が付与されます。

  - モード

  - 書き込み

  - ReadSPN

  - WriteSPN

管理者は、特定の Ou にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーではなくても Ou にアクセスできるようにすることができます。 指定した OU に追加されたアクセス許可は、[ユーザーの**有効化**] と同じアクセス許可であり、[コンピューター] と [ユーザー] のコンテナーに追加します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのセットアップ アクセス許可の付与](lync-server-2013-granting-setup-permissions.md)

  - [Lync Server 2013 での組織単位アクセス許可の付与](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


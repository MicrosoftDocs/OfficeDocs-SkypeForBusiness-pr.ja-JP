---
title: 'Lync Server 2013: 新しい-アドレス帳管理用の Set-cswebserviceconfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fa02c95a3b6bf149c5b3eb5e893ad62dc45dbb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Set-cswebserviceconfiguration Lync Server 2013 でのアドレス帳管理のための新しい手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが New-CsWebServiceConfiguration コマンドレットをローカルで実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

コマンドレット New-CsWebServiceConfiguration は、組織内の Web サービスの新しい構成を定義します。 Web サービス構成のスコープは、サイトまたはサービスのレベルのみです。 グローバル レベルで新しい Web サービス構成を作成することはできません。 アドレス帳で特に注目すべきなのは EnableGroupExansion 属性です。 これが True に設定されていると、Web サービスがグループ拡張の要求に応答できます。

次にその例を示します。

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a>関連項目


[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


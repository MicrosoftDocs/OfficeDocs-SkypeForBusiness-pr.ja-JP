---
title: 'Lync Server 2013: 新しい-アドレス帳管理のための CsWebServiceConfiguration'
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
ms.openlocfilehash: 434c9a7c4ded9516cd930bbaa9bba72873b15a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理のための CsWebServiceConfiguration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、CsWebServiceConfiguration コマンドレットをローカルで実行することを許可されています。 RTCUniversalServerAdmins このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

CsWebServiceConfiguration コマンドレットの新規作成では、組織内の Web サービスの新しい構成が定義されます。 Web サービス構成のスコープは、サイトまたはサービスレベルでのみ利用できます。 グローバルレベルで新しい Web サービス構成を作成することはできません。 特にアドレス帳に関連するものは EnableGroupExansion 属性です。 True に設定されている場合、Web サービスはグループ展開の要求に応答できます。

次に例を示します。

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a>関連項目


[New-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


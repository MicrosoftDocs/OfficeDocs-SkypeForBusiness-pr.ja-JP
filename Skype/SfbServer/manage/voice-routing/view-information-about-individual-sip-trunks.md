---
title: デバイス内の個々の SIP トランクに関する情報を表示Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: このSkype for Business Server、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。つまり、ゲートウェイとトランクは同じではなく、管理者は Get-CsTrunk コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。
ms.openlocfilehash: 1fd465bcbf547471f9ca5ead562d8b77976be79621bd4246be85341126577936
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351457"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>デバイス内の個々の SIP トランクに関する情報を表示Skype for Business Server

このSkype for Business Server、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。つまり、ゲートウェイとトランクは同じではなく、管理者は[Get-CsTrunk](/powershell/module/skype/Get-CsTrunk)コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。

このGet-CsTrunkは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。

**すべての SIP トランクの情報を表示するには**

次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。

`Get-CsTrunk`

**特定の SIP トランクの情報を表示するには**

このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**プールに割り当てられているすべての SIP トランクに関する情報の表示**

この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
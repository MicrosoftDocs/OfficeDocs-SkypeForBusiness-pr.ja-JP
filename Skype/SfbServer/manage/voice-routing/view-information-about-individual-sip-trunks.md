---
title: Skype for Business Server - 個々の SIP トランクに関する情報を表示する
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
description: このSkype for Business Server、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。 ゲートウェイとトランクは同じではなく、管理者は Get-CsTrunk コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。
ms.openlocfilehash: 7fe18b07215749e829cfdbd0de08b21c7d6495f0
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58232672"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype for Business Server - 個々の SIP トランクに関する情報を表示する

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

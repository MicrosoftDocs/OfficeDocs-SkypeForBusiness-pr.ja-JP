---
title: Skype for Business Server - 個々の SIP トランクに関する情報を表示する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: このSkype for Business Server、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。 ゲートウェイとトランクは同じではなく、管理者は Get-CsTrunk コマンドレットを使用して個々の SIP トランクに関する情報を表示する必要があります。
ms.openlocfilehash: 98e189def7be1a5f2f913083ba4a38d21da86856
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835245"
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

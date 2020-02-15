---
title: Skype for Business Server での個々の SIP トランクに関する情報の表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server では、複数のトランクを1つの PSTN ゲートウェイに割り当てることができます。これは、ゲートウェイとトランクが1つだけではなく、管理者は、個々の SIP トランクに関する情報を表示するために、Get-help コマンドレットを使用する必要があることを意味します。
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048180"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Skype for Business Server での個々の SIP トランクに関する情報の表示

Skype for Business Server では、複数のトランクを1つの PSTN ゲートウェイに割り当てることができます。これは、ゲートウェイとトランクが同一ではなく、管理者が個々の SIP トランクに関する情報を表示するには、[コマンドレット](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)を使用する必要があることを意味します。

Get-help コマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

**すべての SIP トランクに関する情報を表示するには**

次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。

`Get-CsTrunk`

**特定の SIP トランクに関する情報を表示するには**

このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**プールに割り当てられているすべての SIP トランクに関する情報の表示**

この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`

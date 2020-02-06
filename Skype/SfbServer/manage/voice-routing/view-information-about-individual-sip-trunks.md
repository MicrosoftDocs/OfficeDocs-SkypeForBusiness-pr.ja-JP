---
title: Skype for Business Server の各 SIP trunks に関する情報を表示する
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
description: Skype for Business Server では、単一の PSTN ゲートウェイに複数の trunks を割り当てることができます。つまり、ゲートウェイと trunks は1つではなく、管理者は、個々の SIP トランクに関する情報を表示するために、Get-CsTrunk コマンドレットを使用する必要があります。
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816926"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Skype for Business Server の各 SIP trunks に関する情報を表示する

Skype for Business Server では、単一の PSTN ゲートウェイに複数の trunks を割り当てることができます。これは、ゲートウェイと trunks が1つではなく、管理者が、個々の SIP トランクに関する情報を表示するために、 [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk)コマンドレットを使用する必要があることを意味します。

Get-CsTrunk コマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

**すべての SIP トランクに関する情報の表示**

次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。

`Get-CsTrunk`

**特定の SIP トランクに関する情報の表示**

このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**プールに割り当てられているすべての SIP Trunks の情報を表示する**

この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`

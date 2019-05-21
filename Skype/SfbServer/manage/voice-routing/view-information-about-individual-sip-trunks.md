---
title: Skype for Business Server の各 SIP trunks に関する情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server では、単一の PSTN ゲートウェイに複数の trunks を割り当てることができます。つまり、ゲートウェイと trunks は1つではなく、管理者は、個々の SIP トランクに関する情報を表示するために、Get-CsTrunk コマンドレットを使用する必要があります。
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274878"
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

---
title: ビジネス サーバーの Skype での個々 の SIP トランクに関する情報を表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの Skype で複数トランクを 1 つの PSTN ゲートウェイを割り当てることができます。つまり、ゲートウェイおよびトランクは、特定の 1 つだけ、管理者は個々 の SIP トランクに関する情報を表示するのには、Get CsTrunk コマンドレットを使用する必要があります。
ms.openlocfilehash: bf9229dba17b7b2e49eb9a05d9469f42c0b9b998
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930821"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>ビジネス サーバーの Skype での個々 の SIP トランクに関する情報を表示

ビジネス サーバーの Skype で複数トランクを 1 つの PSTN ゲートウェイを割り当てることができます。つまり、ゲートウェイまたはトランクは、1 つだけ、ではないことと、管理者が個々 の SIP トランクに関する情報を表示するのには[Get CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk)コマンドレットを使用する必要があります。

ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、Get CsTrunk コマンドレットを実行できます。

**すべての SIP トランクに関する情報の表示**

次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。

`Get-CsTrunk`

**特定の SIP トランクに関する情報の表示**

このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**プールに割り当てられているすべての SIP トランクに関する情報を表示します。**

この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`

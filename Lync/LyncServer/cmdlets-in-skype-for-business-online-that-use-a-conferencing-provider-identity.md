---
title: 会議プロバイダー id を使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e36c04b2f5728ff624a280696bacf4eacb032967
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840093"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>会議プロバイダー id を使用する Skype for Business Online のコマンドレット

 


組織が契約しているすべての電話会議プロバイダーに関する情報を取得するには、パラメーターを指定せずに[CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))コマンドレットを呼び出すだけです。

    Get-CsAudioConferencingProvider

返されるデータを1つのプロバイダーに制限する場合は (この例では、プロバイダーの Contoso Audio サービス)、Identity パラメーターを使用します。

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

電話会議プロバイダー ID を受け入れる Skype for Business Online コマンドレットは1つしかありません。

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))


---
title: 電話会議プロバイダーの id を使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755129"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>電話会議プロバイダーの id を使用する Skype for Business Online のコマンドレット

 


組織で契約しているすべての電話会議プロバイダーに関する情報を戻すには、パラメーターを指定せずに[test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))コマンドレットを呼び出すだけで済みます。

    Get-CsAudioConferencingProvider

返されるデータを1つのプロバイダー (この例では、プロバイダー Contoso Audio サービス) に制限するには、Identity パラメーターを使用します。

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

電話会議プロバイダー ID を受け入れることができる Skype for Business Online コマンドレットは1つだけです。

  - [Test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))


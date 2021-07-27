---
title: ユーザーをクラウドに移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: ユーザーを移動してから、オンプレミスSkype for Business使用を停止します。
ms.openlocfilehash: bc98ebfcfb7ad4d4b2c64942b5f84500a98cdc84
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510718"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>オンプレミス環境を使用停止する前に必要なユーザーを移動する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

この記事では、オンプレミス環境を使用停止する前に、必要なユーザーを Microsoft クラウドに移動するSkype for Business説明します。 これは、オンプレミス環境を使用停止にするための次の手順 1 です。

- **手順 1.必要なすべてのユーザーをオンプレミスからオンラインに移動します。** (この記事)

- 手順 2。 [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- 手順 3. [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移行します](decommission-move-on-prem-endpoints.md)。 この手順を完了するまで、上記の手順 2 を実行するまで、既存のハイブリッド アプリケーション エンドポイントは検出できません。 同じメンテナンス ウィンドウで手順 2 と 3 の両方を実行する予定です。

- 手順 4. [オンプレミスの展開を削除Skype for Businessします](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>必要なすべてのユーザーをオンプレミスからクラウドに移動する

移行が完了した後も引き続き使用するユーザーは、まずオンプレミスからクラウドに移動する必要があります。 オンプレミスの管理ツールを使用してユーザーを移動します。 詳細については、「オンプレミスと [クラウドの間でユーザーを移動する」を参照してください](move-users-between-on-premises-and-cloud.md)。

オンプレミスのユーザーアカウントを持つユーザー Skype for Business Serverを使用Teams、これらのユーザーは、Teams の完全な機能を持Teams。 これらのユーザーは、オンラインまたはオンプレミスを問Skype for Businessを使用している他のユーザーと相互運用またはフェデレーションすることはできません。 また、これらのユーザーは、ユーザーのクライアントで PSTN 通話Teams受け取る必要もありません。 したがって、これらのユーザーをオンラインに移動する必要があります。 また、この手順では、グループで作成された連絡先や会議Skype for Business Serverに移行Teams。

オンプレミス展開にユーザーが残っている場合は、PowerShell ウィンドウで次のコマンドレットSkype for Business Server実行します。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

ユーザーが返された場合は、出力を確認して、アカウントをクラウドに移動する必要があるかどうかを確認し、そのようなユーザーについては、次の手順に従 [います](move-users-between-on-premises-and-cloud.md)。 不要になったユーザー アカウントの場合は、PowerShell コマンドレットでSkype for Business Server実行します。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> フィルターDisable-CsUserを実行すると、フィルター条件Skype for Businessを満たすすべてのユーザーのすべての属性が削除されます。 先に進む前に、これらのアカウントが今後必要でなくなったか確認してください。


これで、ハイブリッド構成を [無効にする準備ができました](cloud-consolidation-disabling-hybrid.md)。

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)

- [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する](decommission-move-on-prem-endpoints.md)

- [オンプレミスの Skype for Business の展開を削除する](decommission-remove-on-prem.md)





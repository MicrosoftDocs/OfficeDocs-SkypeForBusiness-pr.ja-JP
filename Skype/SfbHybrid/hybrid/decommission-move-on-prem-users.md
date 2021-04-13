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
description: Skype for Business オンプレミス環境を使用停止する前にユーザーを移動します。
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656673"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>オンプレミス環境を使用停止する前に必要なユーザーを移動する

この記事では、オンプレミスの Skype for Business 環境を使用停止する前に、必要なユーザーを Microsoft クラウドに移動する方法について説明します。 これは、オンプレミス環境を使用停止にするための次の手順 1 です。

- **手順 1.必要なすべてのユーザーをオンプレミスからオンラインに移動します。** (この記事)

- 手順 2. [ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。

- 手順 3. [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-endpoints.md)。

- 手順 4. [オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>必要なすべてのユーザーをオンプレミスからクラウドに移動する

移行が完了した後も引き続き使用するユーザーは、まずオンプレミスからクラウドに移動する必要があります。 オンプレミスの管理ツールを使用してユーザーを移動します。 詳細については、「オンプレミスと [クラウドの間でユーザーを移動する」を参照してください](move-users-between-on-premises-and-cloud.md)。

オンプレミスの Skype for Business Server アカウントを持つユーザーは Teams を使用することができますが、これらのユーザーには Teams の完全な機能はありません。 これらのユーザーは、Skype for Business を引き続き使用している他のユーザー (オンラインでもオンプレミスでも) を相互運用またはフェデレーションすることはできません。 また、これらのユーザーは Teams クライアントで PSTN 通話を受け取る必要もありません。 したがって、これらのユーザーをオンラインに移動する必要があります。 この手順では、Skype for Business Server で作成された連絡先や会議が Teams に移行されます。

オンプレミス展開にユーザーが残っている場合は、Skype for Business Server PowerShell ウィンドウで次のコマンドレットを実行します。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

ユーザーが返された場合は、出力を確認して、アカウントをクラウドに移動する必要があるかどうかを確認し、そのようなユーザーについては、次の手順に従 [います](move-users-between-on-premises-and-cloud.md)。 不要になったユーザー アカウントの場合は、次の Skype for Business Server PowerShell コマンドレットを実行します。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> このDisable-CsUserすると、フィルター条件を満たすすべてのユーザーのすべての Skype for Business 属性が削除されます。 先に進む前に、これらのアカウントが今後必要でなくなったか確認してください。


これで、ハイブリッド構成を [無効にする準備ができました](cloud-consolidation-disabling-hybrid.md)。

## <a name="see-also"></a>関連項目

- [オンプレミスの Skype for Business 環境を廃止する](decommission-on-prem-overview.md)

- [ハイブリッド構成を無効にする](cloud-consolidation-disabling-hybrid.md)

- [ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動する](decommission-move-on-prem-endpoints.md)

- [オンプレミスの Skype for Business の展開を削除する](decommission-remove-on-prem.md)





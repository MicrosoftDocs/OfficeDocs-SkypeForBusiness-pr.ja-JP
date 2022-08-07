---
title: Microsoft Teams 会議で電話番号をマスクする
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 会議で電話番号をマスクする方法について説明します
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270822"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Microsoft Teams 会議で電話番号をマスクする

プライバシーを強化するために、電話会議を使用して Teams 会議にダイヤルインする参加者の電話番号は、内部参加者に完全に表示されます。 番号は、組織外の参加者からマスクされます。 この設定は、すべての組織の既定値です。 マスクされた番号は、次の図に示すように表示されます。

![マスクされた電話番号の例。](media/hiddenPhoneNum.png)

特定の業界ユース ケースでは、管理者は、テナント内で開催される会議に電話会議参加者の電話番号を表示する方法を選択できます。 管理者は、次の 3 つのオプションから選択できます。

- 電話番号は外部参加者からのみマスクされます。 会議の開催者のテナントに属している参加者には、完全な電話番号が引き続き表示されます。
- 電話番号は、開催者を除く会議の全員からマスクされます。
- 電話番号のマスクが解除され、会議の全員に表示されます。

この設定は、電話番号が公開されている会議のすべてのサーフェイスに適用されます。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell を使用して電話番号マスクを設定する

公衆交換電話網 (PSTN) マスク設定を変更するには、[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを使用可能なオプションの 1 つに設定 **`MaskPstnNumbersType`** します。

外部参加者からのみ電話番号をマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

会議のすべての参加者 (開催者を除く) からの電話番号をマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

電話番号マスクを無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```

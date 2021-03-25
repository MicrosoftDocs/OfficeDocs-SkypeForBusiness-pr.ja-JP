---
title: Microsoft Teams 会議で電話番号をマスクする
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 会議で電話番号をマスクする方法について説明します
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117715"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Microsoft Teams 会議で電話番号をマスクする

プライバシーを高くするために、電話会議を使用して Teams 会議にダイヤルインする参加者の電話番号は、内部参加者に完全に表示されます。 番号は組織外の参加者からマスクされます。 この設定は、すべての組織の既定の設定です。 次の画像のように、マスクされた番号が表示されます。

![マスクされた電話番号の例](media/hiddenPhoneNum.png)

特定の業界の使用例では、管理者は、テナントで開催された会議で電話会議参加者の電話番号がどのように表示されるのか選択できます。 管理者は、次の 3 つのオプションから選択できます。

- 電話番号は、外部参加者からのみマスクされます。 会議開催者のテナントに属している参加者には、引き続き完全な電話番号が表示されます。
- 開催者を除く会議の全員から電話番号がマスクされます。
- 電話番号はマスク解除され、会議の全員に表示されます。

この設定は、電話番号が公開されている会議のすべてのサーフェスに適用されます。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell を使用して電話番号のマスキングを設定する

公衆交換電話網 (PSTN) のマスキング設定を変更するには **`MaskPstnNumbersType`** [、Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを使用可能なオプションの 1 つに設定します。

外部参加者からの電話番号のみをマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

会議のすべての参加者 (開催者を除く) から電話番号をマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

電話番号のマスキングを無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
---
title: 会議で電話番号をMicrosoft Teamsする
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
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 会議中に電話番号をマスクするMicrosoft Teamsする
ms.openlocfilehash: a40f1a7144298c6106183eb45fe80a8958227b1a
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055097"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>会議で電話番号をMicrosoft Teamsする

プライバシーを追加するために、電話会議を使用して Teams 会議にダイヤルインする参加者の電話番号は、内部参加者に完全に表示されます。 番号は、組織外の参加者からマスクされます。 この設定は、すべての組織の既定の設定です。 次の図に示すように、マスクされた番号が表示されます。

![マスクされた電話番号の例。](media/hiddenPhoneNum.png)

特定の業界の使用例では、管理者は、テナントで開催される会議で電話会議参加者の電話番号がどのように表示されるのか選択できます。 管理者は、次の 3 つのオプションから選択できます。

- 電話は、外部参加者からのみマスクされます。 会議開催者のテナントに属している参加者には、完全な電話番号が引き続き表示されます。
- 電話は、開催者を除く会議のすべてのユーザーからマスクされます。
- 電話はマスク解除され、会議のすべてのユーザーに表示されます。

この設定は、電話番号が公開されている会議のすべての画面に適用されます。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell を使用して電話番号のマスクを設定する

公衆交換電話網 (PSTN) のマスク設定を変更するには **`MaskPstnNumbersType`** [、Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを使用可能なオプションの 1 つに設定します。

外部参加者からの電話番号のみをマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

会議のすべての参加者 (開催者を除く) の電話番号をマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

電話番号のマスクを無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```

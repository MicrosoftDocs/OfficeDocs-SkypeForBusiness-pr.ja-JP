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
ms.openlocfilehash: cad28ad446c39a45b865fd24767347fdf11bb9c8
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801768"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Microsoft Teams 会議で電話番号をマスクする

プライバシーを強化するために、電話会議を使用して Teams 会議にダイヤルインする参加者の電話番号は、内部参加者に完全に表示されます。 番号は、組織外の参加者からマスクされます。 この設定は、すべての組織の既定値です。 マスクされた番号は、次の図に示すように表示されます。

![マスクされた電話番号の例。](media/hiddenPhoneNum.png)

特定の業界のユース ケースでは、管理者は、電話会議の参加者の電話番号をテナントで編成された会議に表示する方法を選択できます。 管理者は、次の 3 つのオプションから選択できます。

- 電話番号は外部参加者からのみマスクされます。 会議開催者のテナントに属している参加者には、引き続き完全な電話番号が表示されます。
- 電話番号は、開催者を除く会議のすべてのユーザーからマスクされます。
- 電話番号はマスク解除され、会議のすべてのユーザーに表示されます。

この設定は、電話番号が公開されている会議のすべてのサーフェスに適用されます。

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>Teams 管理センターを使用して電話番号マスクを設定する

Teams 管理センターで公衆交換電話網 (PSTN) マスク設定を変更するには、管理者として Teams 管理センターにログインし、左側のナビゲーション パネルで **[会議** > **会議ブリッジ** ] を選択し、[ **ブリッジ設定**] を選択します。 **マスクされた発信者 ID の表示** は、[Bridge settings]\(ブリッジ設定\) ウィンドウの下部にあるドロップダウンです。これにより、次の項目を選択できます。

- 組織外の参加者へ
- すべての会議参加者へ
- 無効

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Microsoft PowerShell を使用して電話番号マスクを設定する

PowerShell で PSTN マスク設定を変更するには、[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを使用可能なオプションのいずれかに設定 **`MaskPstnNumbersType`** します。

外部参加者からのみ電話番号をマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

会議のすべての参加者 (開催者を除く) の電話番号をマスクするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

電話番号マスクを無効にするには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```

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
ms.openlocfilehash: 5a59ef07873660e79d6c8bc69b7e92095a2fac1a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726796"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="759c1-103">Microsoft Teams 会議で電話番号をマスクする</span><span class="sxs-lookup"><span data-stu-id="759c1-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="759c1-104">プライバシーを高くするために、電話会議を使用して Teams 会議にダイヤルインする参加者の電話番号は、内部参加者に完全に表示されます。</span><span class="sxs-lookup"><span data-stu-id="759c1-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="759c1-105">番号は組織外の参加者からマスクされます。</span><span class="sxs-lookup"><span data-stu-id="759c1-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="759c1-106">この設定は、すべての組織の既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="759c1-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="759c1-107">次の画像のように、マスクされた番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="759c1-107">The masked number is displayed as shown in the following image:</span></span>

![マスクされた電話番号の例](media/hiddenPhoneNum.png)

<span data-ttu-id="759c1-109">特定の業界の使用例では、管理者は、テナントで開催された会議で電話会議参加者の電話番号の表示方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="759c1-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="759c1-110">管理者は、次の 3 つのオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="759c1-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="759c1-111">電話番号は、外部参加者からのみマスクされます。</span><span class="sxs-lookup"><span data-stu-id="759c1-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="759c1-112">会議開催者のテナントに属している参加者には、引き続き完全な電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="759c1-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="759c1-113">開催者を除く会議の参加者全員から電話番号がマスクされます。</span><span class="sxs-lookup"><span data-stu-id="759c1-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="759c1-114">電話番号はマスク解除され、会議の全員に表示されます。</span><span class="sxs-lookup"><span data-stu-id="759c1-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="759c1-115">この設定は、電話番号が公開されている会議のすべての画面に適用されます。</span><span class="sxs-lookup"><span data-stu-id="759c1-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="759c1-116">Microsoft PowerShell を使用して電話番号のマスキングを設定する</span><span class="sxs-lookup"><span data-stu-id="759c1-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="759c1-117">公衆交換電話網 (PSTN) のマスキング設定を変更するには **`MaskPstnNumbersType`** [、Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを使用可能なオプションの 1 つに設定します。</span><span class="sxs-lookup"><span data-stu-id="759c1-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="759c1-118">外部参加者からの電話番号のみをマスクするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="759c1-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="759c1-119">会議のすべての参加者 (開催者を除く) から電話番号をマスクするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="759c1-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="759c1-120">電話番号のマスキングを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="759c1-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```

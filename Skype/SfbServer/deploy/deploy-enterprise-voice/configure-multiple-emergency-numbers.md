---
title: Skype for Business で複数の緊急電話番号を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Skype for Business Server で複数の緊急電話番号を構成する方法については、このトピックを参照してください。
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111893"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="a6f02-103">Skype for Business で複数の緊急電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="a6f02-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="a6f02-104">Skype for Business Server で複数の緊急電話番号を構成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f02-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="a6f02-105">Skype for Business Server は、クライアントに対して複数の緊急電話番号をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6f02-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="a6f02-106">複数の緊急電話番号は、2016 年 6 月の累積的な更新プログラムで導入された新機能です。</span><span class="sxs-lookup"><span data-stu-id="a6f02-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="a6f02-107">複数の緊急電話番号をサポートする環境を構成する前に、「Skype for Business Server で複数の緊急電話番号を計画する [」を参照してください](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f02-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a6f02-108">2016 年 11 月の累積的な更新プログラムにまだアップグレードしていない場合は [、「Update to Skype for Business Server 2015」を参照](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)してください。</span><span class="sxs-lookup"><span data-stu-id="a6f02-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="a6f02-109">2016 年 11 月の累積的な更新プログラムでは、サポート緊急電話番号の数が 5 から 100 に増加します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="a6f02-110">複数の緊急電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="a6f02-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="a6f02-111">複数の緊急番号を構成するには、New-CsEmergencyNumber コマンドレットを使用し [、New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットと [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) コマンドレットを使用して EmergencyNumbers パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="a6f02-112">PSTN 使用法や必要な場所など、すべての場所ポリシー パラメーターの詳細については [、「Set-CsLocationPolicy」を参照してください](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a6f02-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="a6f02-113">次のコマンドは、次のコマンドレットを使用して、ダイヤル文字列 911 を持つ新しい緊急New-CsEmergencyします。</span><span class="sxs-lookup"><span data-stu-id="a6f02-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="a6f02-114">次のコマンドは、次のコマンドレットで EmergencyNumbers パラメーターを指定して、指定した場所ポリシーに番号Set-CsLocationPolicyします。</span><span class="sxs-lookup"><span data-stu-id="a6f02-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="a6f02-115">次の例では、緊急電話番号が 1 つのダイヤル マスク 112 で作成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f02-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="a6f02-116">次のコマンドは、複数のダイヤル マスクを持つ緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="a6f02-117">次の例では、複数の緊急電話番号を複数のダイヤル マスクに追加し、緊急電話番号を指定した場所ポリシーに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="a6f02-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="a6f02-118">次の例では、911 と 450 の両方を使用する医療プロバイダー用に複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="a6f02-119">次の例では、ロンドン市の複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="a6f02-120">次の例では、インドの複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="a6f02-121">次の例では、ダイヤル文字列 911 とダイヤル マスク 112 と 999 を含む既存のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6f02-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
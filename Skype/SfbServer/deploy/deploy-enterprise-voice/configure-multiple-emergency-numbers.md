---
title: Skype for Business で複数の緊急電話番号を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027798"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="a19fc-103">Skype for Business で複数の緊急電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="a19fc-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="a19fc-104">このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="a19fc-105">Skype for Business Server は、クライアントの複数の緊急電話番号をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="a19fc-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="a19fc-106">複数の緊急電話番号は、2016年6月の累積的な更新プログラムで導入された新機能です。</span><span class="sxs-lookup"><span data-stu-id="a19fc-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="a19fc-107">複数の緊急電話番号をサポートするように環境を構成する前に、 [Skype For Business Server の複数の緊急電話番号の計画](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="a19fc-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a19fc-108">2016年11月の累積的な更新プログラムにまだアップグレードしていない場合は、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a19fc-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="a19fc-109">2016年11月の累積的な更新プログラムでは、サポートの緊急電話番号の数は5から100に増加します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="a19fc-110">複数の緊急電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="a19fc-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="a19fc-111">複数の緊急電話番号を構成するには、New-csemergencynumber コマンドレットを使用して、EmergencyNumbers パラメーターを[新しい-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)および[Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットと共に指定します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="a19fc-112">PSTN 使用法や必要な場所など、すべての場所ポリシーパラメーターの詳細については、「 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a19fc-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="a19fc-113">次のコマンドは、CsEmergency コマンドレットを使用して、ダイヤル文字列911を使用して新しい緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="a19fc-114">次のコマンドは、EmergencyNumbers パラメーターを指定して、指定された場所のポリシーに番号を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a19fc-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="a19fc-115">次の例では、1つのダイヤルマスク112で緊急電話番号が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a19fc-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="a19fc-116">次のコマンドは、複数のダイヤルマスクを持つ緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="a19fc-117">次の例では、複数のダイヤルマスクを持つ複数の緊急電話番号を追加し、緊急電話番号を指定された場所のポリシーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a19fc-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="a19fc-118">次の例では、911と450の両方を使用する医療機関向けに複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="a19fc-119">次の例では、London の市に対して複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="a19fc-120">次の例では、インドの複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="a19fc-121">次の例では、ダイヤル文字列911とダイヤルマスク112および999を使用して既存のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="a19fc-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```

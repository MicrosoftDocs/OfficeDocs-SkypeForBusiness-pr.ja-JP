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
description: このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804107"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="2886a-103">Skype for Business で複数の緊急電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="2886a-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="2886a-104">このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2886a-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="2886a-105">Skype for Business Server では、クライアントで複数の緊急電話番号がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2886a-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="2886a-106">複数の緊急電話番号は、2016 年 6 月の累積的な更新プログラムで導入された新機能です。</span><span class="sxs-lookup"><span data-stu-id="2886a-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="2886a-107">複数の緊急電話番号をサポートする環境を構成する前に [、「Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)で複数の緊急電話番号を計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2886a-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2886a-108">If you have yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2886a-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="2886a-109">2016 年 11 月の累積的な更新プログラムでは、サポート緊急電話番号の数が 5 から 100 に増加しました。</span><span class="sxs-lookup"><span data-stu-id="2886a-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="2886a-110">複数の緊急電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="2886a-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="2886a-111">複数の緊急電話番号を構成するには、New-CsEmergencyNumber コマンドレットを使用し [、New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットと [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) コマンドレットを使用して EmergencyNumbers パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2886a-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="2886a-112">PSTN 使用法や必要な場所など、すべての場所ポリシー パラメーターの詳細については [、「Set-CsLocationPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2886a-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="2886a-113">次のコマンドは、次のコマンドレットを使用して、ダイヤル文字列 911 を持つ新しい緊急New-CsEmergencyします。</span><span class="sxs-lookup"><span data-stu-id="2886a-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="2886a-114">次のコマンドでは、次のコマンドレットで EmergencyNumbers パラメーターを指定して、番号を指定した場所のポリシーSet-CsLocationPolicyします。</span><span class="sxs-lookup"><span data-stu-id="2886a-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="2886a-115">次の例では、1 つのダイヤル マスク 112 で緊急電話番号が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2886a-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="2886a-116">次のコマンドは、複数のダイヤル マスクを持つ緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="2886a-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="2886a-117">次の例では、複数のダイヤル マスクを持つ複数の緊急電話番号を追加し、緊急電話番号を指定された場所のポリシーに関連付します。</span><span class="sxs-lookup"><span data-stu-id="2886a-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="2886a-118">次の例では、911 と 450 の両方を使用する医療プロバイダー用に複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="2886a-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="2886a-119">次の例では、ロンドン市の複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="2886a-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="2886a-120">次の例では、インドの複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="2886a-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="2886a-121">次の例では、ダイヤル文字列 911 とダイヤル マスク 112 および 999 の既存のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="2886a-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```

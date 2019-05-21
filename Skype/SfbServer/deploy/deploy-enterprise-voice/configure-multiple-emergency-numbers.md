---
title: Skype for Business の複数の緊急電話番号を設定する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Skype for Business Server で複数の緊急電話番号を設定する方法については、こちらのトピックを参照してください。
ms.openlocfilehash: 0a2387576418aa2631095c46e970fdfac234ca4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303377"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="052a6-103">Skype for Business の複数の緊急電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="052a6-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="052a6-104">Skype for Business Server で複数の緊急電話番号を設定する方法については、こちらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="052a6-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="052a6-105">Skype for Business Server で、クライアントの複数の緊急電話番号がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="052a6-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="052a6-106">複数の緊急電話番号は、2016年6月の累積更新プログラムで導入された新機能です。</span><span class="sxs-lookup"><span data-stu-id="052a6-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="052a6-107">複数の緊急電話番号をサポートするように環境を構成する前に、「 [Skype For Business Server で複数の緊急電話番号のプラン](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052a6-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="052a6-108">2016年11月の累積更新プログラムにアップグレードしていない場合は、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052a6-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="052a6-109">2016年11月の累積更新プログラムでは、サポート緊急電話番号の数が5から100に増えます。</span><span class="sxs-lookup"><span data-stu-id="052a6-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="052a6-110">複数の緊急電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="052a6-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="052a6-111">複数の緊急電話番号を構成するには、CsEmergencyNumber コマンドレットを使用します。次に、[新しい-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)と[Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットを使用して、EmergencyNumbers パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="052a6-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="052a6-112">PSTN の使用状況や必要な場所など、すべての場所ポリシーパラメーターの詳細については、「 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052a6-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="052a6-113">次のコマンドでは、New-CsEmergency コマンドレットを使用して、ダイヤル文字列 911 で新しい緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="052a6-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="052a6-114">次のコマンドでは、Set-CsLocationPolicy コマンドレットで EmergencyNumbers パラメータを指定して、番号を特定の場所のポリシーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="052a6-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="052a6-115">次の例では、1 つのダイヤル マスク 112 を持つ緊急電話番号が作成されます。</span><span class="sxs-lookup"><span data-stu-id="052a6-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="052a6-116">次のコマンドでは、複数のダイヤルマスクを持つ緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="052a6-116">The next command creates an emergency number with multiple dial masks:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="052a6-117">次の例では、複数のダイヤル マスクを持つ複数の緊急電話番号を追加し、緊急電話番号を特定の場所のポリシーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="052a6-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="052a6-118">次の例では、911 と 450 の両方を使用する医療機関向けに複数の緊急電話番号を構成します。 </span><span class="sxs-lookup"><span data-stu-id="052a6-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="052a6-119">次の例では、ロンドン シティー向けに複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="052a6-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="052a6-120">次の例では、インド向けに複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="052a6-120">The next example configures multiple emergency numbers for India:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="052a6-121">次の例では、ダイヤル文字列 911 およびダイヤル マスク 112 と 999 を持つ既存のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="052a6-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```



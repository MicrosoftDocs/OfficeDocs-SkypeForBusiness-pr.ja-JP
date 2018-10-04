---
title: ビジネス用の Skype で複数の緊急番号を構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Skype のビジネス サーバーの複数の緊急番号を構成する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 64f9368b5d6eaac1c2f872ebf48152514cc99b34
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372686"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="c8489-103">ビジネス用の Skype で複数の緊急番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="c8489-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="c8489-104">Skype のビジネス サーバーの複数の緊急番号を構成する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8489-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="c8489-105">Skype ビジネス サーバーがクライアントの複数の緊急番号をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c8489-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="c8489-106">複数の緊急番号は 2016年 6 月で導入された新しい機能を累積的な更新です。</span><span class="sxs-lookup"><span data-stu-id="c8489-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="c8489-107">複数の緊急番号をサポートするために、環境を構成する前に、 [Skype のビジネス サーバーで複数の緊急番号の計画](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8489-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c8489-108">かどうかにないまだアップグレード 2016年 11 月累積的な更新は、 [Skype のビジネス サーバー 2015 への更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8489-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="c8489-109">2016年 11 月の累積的な更新をサポート緊急時の番号の数は 5 から 100 に増加します。</span><span class="sxs-lookup"><span data-stu-id="c8489-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="c8489-110">複数の緊急電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="c8489-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="c8489-111">複数の緊急番号を構成するのには、新規 CsEmergencyNumber コマンドレットを使用して[新規 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)と[セット CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットの EmergencyNumbers パラメーターを指定するし。</span><span class="sxs-lookup"><span data-stu-id="c8489-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="c8489-112">すべての場所ポリシーのパラメーター、PSTN の使用法など、必要な場所の詳細については、[セット CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8489-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="c8489-113">次のコマンドでは、New-CsEmergency コマンドレットを使用して、ダイヤル文字列 911 で新しい緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8489-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="c8489-114">次のコマンドでは、Set-CsLocationPolicy コマンドレットで EmergencyNumbers パラメータを指定して、番号を特定の場所のポリシーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c8489-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="c8489-115">次の例では、1 つのダイヤル マスク 112 を持つ緊急電話番号が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c8489-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="c8489-116">次のコマンドは、複数のダイヤル マスクを使用した、緊急電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8489-116">The next command creates an emergency number with multiple dial masks:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="c8489-117">次の例では、複数のダイヤル マスクを持つ複数の緊急電話番号を追加し、緊急電話番号を特定の場所のポリシーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c8489-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="c8489-118">次の例では、911 と 450 の両方を使用する医療機関向けに複数の緊急電話番号を構成します。 </span><span class="sxs-lookup"><span data-stu-id="c8489-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="c8489-119">次の例では、ロンドン シティー向けに複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="c8489-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="c8489-120">次の例では、インド向けに複数の緊急電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="c8489-120">The next example configures multiple emergency numbers for India:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="c8489-121">次の例では、ダイヤル文字列 911 およびダイヤル マスク 112 と 999 を持つ既存のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8489-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```



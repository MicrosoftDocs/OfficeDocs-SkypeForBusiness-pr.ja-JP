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
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Skype for Business で複数の緊急電話番号を構成する

Skype for Business Server で複数の緊急電話番号を構成する方法については、このトピックを参照してください。

Skype for Business Server は、クライアントに対して複数の緊急電話番号をサポートしています。 複数の緊急電話番号は、2016 年 6 月の累積的な更新プログラムで導入された新機能です。 複数の緊急電話番号をサポートする環境を構成する前に、「Skype for Business Server で複数の緊急電話番号を計画する [」を参照してください](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 2016 年 11 月の累積的な更新プログラムにまだアップグレードしていない場合は [、「Update to Skype for Business Server 2015」を参照](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)してください。 2016 年 11 月の累積的な更新プログラムでは、サポート緊急電話番号の数が 5 から 100 に増加します。

## <a name="configure-multiple-emergency-numbers"></a>複数の緊急電話番号の構成

複数の緊急番号を構成するには、New-CsEmergencyNumber コマンドレットを使用し [、New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットと [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) コマンドレットを使用して EmergencyNumbers パラメーターを指定します。 PSTN 使用法や必要な場所など、すべての場所ポリシー パラメーターの詳細については [、「Set-CsLocationPolicy」を参照してください](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

次のコマンドは、次のコマンドレットを使用して、ダイヤル文字列 911 を持つ新しい緊急New-CsEmergencyします。

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

次のコマンドは、次のコマンドレットで EmergencyNumbers パラメーターを指定して、指定した場所ポリシーに番号Set-CsLocationPolicyします。

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

次の例では、緊急電話番号が 1 つのダイヤル マスク 112 で作成されます。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

次のコマンドは、複数のダイヤル マスクを持つ緊急電話番号を作成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

次の例では、複数の緊急電話番号を複数のダイヤル マスクに追加し、緊急電話番号を指定した場所ポリシーに関連付ける。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

次の例では、911 と 450 の両方を使用する医療プロバイダー用に複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

次の例では、ロンドン市の複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

次の例では、インドの複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

次の例では、ダイヤル文字列 911 とダイヤル マスク 112 と 999 を含む既存のエントリを削除します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```